---
layout: default
title: MapServer
parent: Pozi Server
grand_parent: Administrator Guide
---

# MapServer

## Installation

On the server on which Pozi Server is installed:

MapServer is installed with Pozi Server in the following default location:

```
C:\Program Files (x86)\Pozi\server\Vendor\GDAL\bin\ms\apps\mapserv.exe
```



## IIS Integration

MapServer IIS Integration using FastCGI.

The default 

Open a command prompt window (as a normal user, not an administrator), and copy and paste these commands into it.

```
mkdir C:\Program Files (x86)\Pozi\server\data\iis\Pozi\MapServer
mkdir C:\Program Files (x86)\Pozi\server\data\iis\logs
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
"%systemroot%\system32\inetsrv\appcmd" add app /site.name:"Default Web Site" /path:/Pozi /physicalPath:"C:\Program Files (x86)\Pozi\server\data\iis\Pozi"
"%systemroot%\system32\inetsrv\appcmd" add app /site.name:"Default Web Site" /path:/Pozi/MapServer /physicalPath:"C:\Program Files (x86)\Pozi\server\data\iis\Pozi\MapServer"
```



Go to `C:\Program Files (x86)\Pozi\server\data\iis\Pozi\MapServer`, and create a blank text file called `web.config`, paste into it the following text, then save it.

(If you're unable to create a blank document, right-click on the `C:\Program Files (x86)\Pozi\server\data\iis\Pozi` folder, Properties > Security > Edit > Add > add domain user > allow Modify and Write permissions.)

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

<img src="img/pozi-qgis-server-iis.png" alt="FastCGI Settings" style="zoom:60%;" />

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

![Grant read permission for Pozi Server data folder to IIS AppPool\PoziQgisServer](img/pozi-server-iis-apppool-poziqgisserver-permissions.png)

## Reference for Pozi Developers

Development notes that may contain useful additional information for Pozi developers.

* https://github.com/pozi/PoziServer/pull/40#issuecomment-972331899


## Configuring Clean Urls for QGIS Server FastCGI


`/Pozi/QgisServer/Next/VicMap`


```
"%systemroot%\system32\inetsrv\appcmd.exe" add apppool /name:"PoziQgisServer"
```
