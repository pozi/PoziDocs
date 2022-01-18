---
layout: default
title: Installation
parent: Pozi Server
grand_parent: Administrator Guide
---

# Pozi Server Installation

## Prerequisites

* support account
* service account
* internet access (need to reach connect.pozi.com)

## Download and Install

1. download the [Pozi Connect Server installer](https://connect.pozi.com/installer/PoziConnectInstaller.exe)
2. install
3. mkdir "C:\Program Files (x86)\Pozi\userdata\local"
4. mklink /D "C:\Program Files (x86)\Pozi\userdata\local\sample" "C:\Program Files (x86)\Pozi\server\data\local\sample"

## Testing New Versions

### Install Test or Dev Release

Edit the `C:\Program Files (x86)\Pozi\updater\updater-config.json` file as follows:

Testing release

```
{
   "serverManifestFile": "manifest-server-testing.json"
}
```

Dev release

```
{
   "serverManifestFile": "manifest-server-dev.json"
}
```

Then stop and start the `PoziConnectUpdater` service. Monitor the `updater.log` file for progress.

### Revert to Production Release

To rollback to a previous version (e.g., from `v2.3.0-beta.3` on `dev` manifest to `v2.2.0` on `production` manifest):

1. revert the manifest file to the `production` version by emptying the contents
2. rename the `server` folder
3. update the manifest from `dev` to `production`
4. stop and start the `PoziConnectUpdater` service

This will revert from the higher numbered `dev` manifest version to the lower numbered production manifest version.

Important note: any additional folders under the `server` folder that have been set up for "clean" URL configuration for QGIS Server will not appear in the new installation, which would be catastrophic for those sites that are using it. They must be copied from the renamed server folder.

## Troubleshooting

### Ping Test Failed

If you encounter a message that says "The ping test to connect.pozi.com failed", ensure that your machine has permissions to connect to connect.pozi.com.
