# Code C# and SQL

### Date Time String Format

[Unable to set datetime format in MVC 4 using data annotations](http://stackoverflow.com/questions/12109007/unable-to-set-datetime-format-in-mvc-4-using-data-annotations)
```

```


[@Html.DisplayFor - DateFormat (“mm/dd/yyyy”)](http://stackoverflow.com/questions/28114874/html-displayfor-dateformat-mm-dd-yyyy)

```
@if (Model.AuditDate.HasValue)
{
    @Model.AuditDate.Value.ToString("MM/dd/yyyy")
}
```

[How to render a DateTime in a specific format in ASP.NET MVC 3?](http://stackoverflow.com/questions/6001654/how-to-render-a-datetime-in-a-specific-format-in-asp-net-mvc-3)
```
@Html.DisplayFor(m => m.MyDateTime, "ShortDateTime")
```
Format datetime type to dd/mm/yyyy hh:mm using Razor and Display/EditorTemplates
https://forums.asp.net/t/1812998.aspx?Format+datetime+type+to+dd+mm+yyyy+hh+mm+using+Razor+and+Display+EditorTemplates

```
ToString("dd/MM/yyyy hh:mm")
i.e.,

@Html.DisplayFor(Function(modelItem) currentItem.DateCreated.ToString("dd/MM/yyyy hh:mm"))
```

# HTMLHelpers

## Stack overflow

[ASP.NET Actionlink with glyphicon and text with different font](http://stackoverflow.com/questions/26174013/asp-net-actionlink-with-glyphicon-and-text-with-different-font)
