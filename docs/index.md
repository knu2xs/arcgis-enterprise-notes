---
title: General Notes
---

# General ArcGIS Enterprise Server Installation Notes

## Base Deployment Diagram

``` mermaid
architecture-beta

    group public(cloud)[Public]
    group private(cloud)[Private] in public

    service portal(server)[ArcGIS Portal] in private
    service server(server)[ArcGIS Server] in private
    service data(database)[ArcGIS Data Store] in private
    service portal_adapter(server)[ArcGIS Web Adapter] in public
    service server_adapter(server)[ArcGIS Web Adapter] in public

    portal_adapter:R -- L:portal
    server_adapter:R -- L:server
    portal:B -- T:server
    server:B -- T:data
```

## Component Installation Order

1. [ArcGIS Server](#arcgis-server)
2. [ArcGIS Portal](#arcgis-portal)
3. [ArcGIS Data Store](#arcgis-data-store)
4. [ArcGIS Web Adaptor](#arcgis-web-adaptor)

## Specific Components

### ArcGIS Server

##### User Account

- recommended to be domain account
- in multi-machine deployments, username and password must be identical on both machines
- _does not_ need to be part of local machine Administrators group

##### Server Files

- Install [.NET Desktop Runtime 8.0](https://dotnet.microsoft.com/en-us/download/dotnet/8.0) (enables SOI and SOE)

###### Configuration Store

- 

###### Server Directories

##### Hardware
- RAM
    - minimum: 8GB
- Disk Space: 10GB

##### Ports
- 6443
- High Availability: 4000-4002 (or higher)

### ArcGIS Portal

#### Hardware

#### Ports
 - 7443

### ArcGIS Data Store

#### Hardware

#### Ports

##### Object Store

- 9220
- 9320

##### Spatiotemporal Data Store

- 29878
- 29879

### ArcGIS Web Adaptor