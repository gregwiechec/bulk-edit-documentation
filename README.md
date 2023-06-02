# Bulk Edit

Repository for documentation and issues tracking for BulkEdit EPiserver addon.

## Supported versions

The supported version is EPiServer.CMS 12.17.1+. EPiserver 11 is not supported.

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

## Using BulkEdit addon

Bulk editing functionality is available from page tree

![Bulk Edit command](assets/bulk_edit_command.jpg "Bulk edit command")

When command was executed, the selection dialog is displayed

![Bulk Edit selector](assets/bulk_edit_selector.jpg "Bulk edit selector")

When content items are selected, Editor can configure which fields should be edited

![Bulk Edit form](assets/bulk_edit_form.jpg "Bulk edit form")

After clicking **Next** the content are updates and Editor will see progress dialog

![Bulk Edit progress](assets/bulk_edit_progress_window.jpg "Bulk edit progress")

### Handling errors

![Bulk Edit save errors](assets/bulk_edit_save_error.jpg "Bulk edit save error")

### Publishing edited content

![Bulk Edit project command](assets/bulk_edit_project_command.jpg "Bulk edit project command")

### Hiding properties on bulk edit form

```c#
[ContentType(GUID = "638D8271-5CA3-4C72-BABC-3E8779233263")]
public class NewsPage : PageData
{
    // ...

    [AllowBulkEdit(false)]
    public virtual string TestProperty { get; set; }

    // ...
}
```

## How form is created

Form is created from content types metadata.

## Limitations

Editing content items using bulk edit will not start the transaction. Each content is saved separately.
The update will not sop when one of the content was not saved successfully.

## Reporting bugs and requesting new features

To report bugs or request for new features please use [Issues](https://github.com/gregwiechec/bulk-edit-documentation/issues) tab.  
