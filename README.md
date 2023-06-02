# Bulk Edit
Documentation and issues tracking for BulkEdit addon

## Supported versions

The supported version is EPiServer.CMS 12.17.1+
EPiserver 11 is not supported.

## Introduction

The project is an EPiserver addon for content bulk editing.

## Install

```
Install-Package Advanced.CMS.BulkEdit
```

In order to start using BulkEdit module you need to add the following statement to Startup.cs

```c#
public class Startup
{
    ...
    public void ConfigureServices(IServiceCollection services)
    {
        ...
        services.AddBulkEdit();
        ...
    }
    ...
}
```

## Reporting bugs and requesting new features

To report bugs or request for new features please use [Issues](/gregwiechec/bulk-edit-documentation/issues) tab.  
