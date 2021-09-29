---
layout: default
title: QGIS Server
parent: Pozi Server
grand_parent: Administrator Guide
---

# QGIS Server

## Installation

On the server on which Pozi Server is installed:

* if any previous version of QGIS Desktop has been installed using the stand-alone installer, uninstall it
* go to https://trac.osgeo.org/osgeo4w/
* click on link for OSGeo4W network installer
* download https://download.osgeo.org/osgeo4w/v2/osgeo4w-setup.exe
* right-click on osgeo4w-setup.exe, "Run as administrator"
* Advanced Install, accept defaults
* Install for all users, accept defaults
* Choose a download site, select top one, Next
* Select Packages
  * Desktop
    * qgis-ltr - click on the word 'Skip' to toggle through to the latest version (eg 3.16.8-3)
  * Libs
    * gdal-ecw
    * gdal-mss
  * Web
    * qgis-ltr-server
* Next, accept defaults, "Install these packages...", Next, "I agree...", Next



## IIS Integration

QGIS Server IIS Integration using FastCGI.

NOTE: You should install QGIS Server using the v2 installer available from the link below which installs 
64-bit QGIS Server defaulting to the path `C:\OSGeo4W`:

https://download.osgeo.org/osgeo4w/v2/osgeo4w-setup.exe

Make sure you run as Administrator so that you install for all users, and select Advanced so that you can
install QGIS Server.  Ensure that you install the `gdal-ecw` and `gdal-mss` plugins from the Libs section
so that you can read ECW images and can utilise the SQL Server Native Client driver.

NOTE: I am using the path C:\Pozi temporarily, and the configuration will eventually be deployed 
under `C:\Program Files (x86)\Pozi` but I am keeping it separated until it is ready.

Open a command prompt window (as a normal user, not an administrator), and copy and paste these commands into it.

```
mkdir C:\Pozi
mkdir C:\Pozi\wwwroot
mkdir C:\Pozi\QgisServer
mkdir C:\Pozi\QgisServer\wwwroot
mkdir C:\Pozi\QgisServer\logs
```



### Install IIS

In a new command prompt window, running as administrator:

```
dism /online /enable-feature /featurename:IIS-WebServerRole
dism /online /enable-feature /featurename:IIS-WebServer
dism /online /enable-feature /featurename:IIS-ApplicationDevelopment
dism /Online /Enable-Feature /FeatureName:IIS-CGI
```



### Configure IIS

```
"%systemroot%\system32\inetsrv\appcmd" add app /site.name:"Default Web Site" /path:/Pozi /physicalPath:"C:\Pozi\wwwroot"
"%systemroot%\system32\inetsrv\appcmd" add app /site.name:"Default Web Site" /path:/Pozi/QgisServer /physicalPath:"C:\Pozi\QgisServer\wwwroot"
```



Go to `C:\Pozi\QgisServer\wwwroot`, and create a blank text file called `web.config`, paste into it the following text, then save it.

(If you're unable to create a blank document, right-click on the `C:\Pozi\` folder, Properties > Security > Edit > Add > add domain user > allow Modify and Write permissions.)

```
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
    <system.webServer>
        <handlers>
            <add name="PoziQgisServerFastCgi" path="*" verb="*" type="" modules="FastCgiModule" scriptProcessor="C:\OSGeo4W\apps\qgis-ltr\bin\qgis_mapserv.fcgi.exe"
            resourceType="Unspecified" requireAccess="Script" allowPathInfo="false" preCondition=""  />
        </handlers>
        <caching enabled="true" enableKernelCache="true" />
    </system.webServer>
</configuration>
```



Back in the command prompt, run the following:

```
%windir%\system32\inetsrv\appcmd.exe unlock config -section:system.webServer/handlers
"%systemroot%\system32\inetsrv\appcmd" set config -section:system.webServer/fastCgi /+"[fullPath='C:\OSGeo4W\apps\qgis-ltr\bin\qgis_mapserv.fcgi.exe']" /commit:apphost
"%systemroot%\system32\inetsrv\appcmd" set config /section:isapiCgiRestriction /+"[path='C:\OSGeo4W\apps\qgis-ltr\bin\qgis_mapserv.fcgi.exe',description='PoziQgisServer',allowed='True']"
```



Windows > IIS > select server > Fast CGISettings > select item we just configured > Edit > Environment variables:

```
PATH = "C:\OSGeo4W\apps\qgis-ltr\bin;C:\OSGeo4W\apps\qt5\bin;C:\OSGeo4W\bin;C:\Windows\system32;C:\Windows;C:\Windows\system32\WBem"
O4W_QT_PREFIX = "C:\OSGeo4W\apps\Qt5"
O4W_QT_BINARIES = "C:\OSGeo4W\apps\Qt5\bin"
O4W_QT_PLUGINS = "C:\OSGeo4W\apps\Qt5\plugins"
O4W_QT_LIBRARIES = "C:\OSGeo4W\apps\Qt5\lib"
O4W_QT_TRANSLATIONS = "C:\OSGeo4W\apps\Qt5\translations"
O4W_QT_HEADERS = "C:\OSGeo4W\apps\Qt5\include"
QGIS_PREFIX_PATH = "C:\OSGeo4W\apps\qgis-ltr"
QT_PLUGIN_PATH = "C:\OSGeo4W\apps\qt5\plugins"
TEMP = "C:\Windows\Temp"
PYTHONHOME = "C:\OSGeo4W\apps\Python39"
QGIS_SERVER_LOG_FILE = "C:\Pozi\QgisServer\logs\qgis_server.log"
QGIS_SERVER_LOG_LEVEL = "0"
QGIS_PLUGINPATH = "C:\OSGeo4W\apps\qgis-ltr\plugins"
```

![PROJ_LIB environment variable](G:\My Drive\Notes\pozi-qgis-server-iis.png)



### Application Pool

- Create PoziQgisServer application pool

```
"%systemroot%\system32\inetsrv\appcmd.exe" add apppool /name:"PoziQgisServer"
"%systemroot%\system32\inetsrv\appcmd.exe" set config -section:system.applicationHost/applicationPools /+"[name='PoziQgisServer'].recycling.periodicRestart.schedule.[value='02:00:00']" /commit:apphost
```


Set the user for the PoziQgisServer application pool:

- IIS > select server > Sites > Default Web Site > Pozi > QgisServer > Advanced Settings > Application Pool > set to PoziQgisServer

Set permissions for ```IIS AppPool\PoziQgisServer``` :

- IIS > select server > Application Pools > PoziQgisServer > Advanced settings > Identity > Application Pool Identity > Custom account > enter details of the domain user that runs Pozi "service" account
