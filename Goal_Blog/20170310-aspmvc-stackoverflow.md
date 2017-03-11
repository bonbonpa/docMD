# Excel Research

## How to handle null values when adding to a collection.(Mvc, C#)

```cs
if ((col1Value != null && col2Value != null && col3Value != null && col4Value != null))
{
    exampleDataList.Add(new PersonalData {firstname = col1Value.ToString(),lastname = col2Value.ToString(), address=col3Value.ToString(), salary=col4Value.ToString() });
}

if ((col1Value != null && col2Value != null))
{
    exampleDataList.Add(new PersonalData {
            firstname = col1Value.ToString(),
            lastname  = col2Value.ToString(),
            address   = col3Value == null ? "" : col3Value.ToString(),
            salary    = col4Value == null ? "" : col4Value.ToString() });
}

if ((col1Value != null && col2Value != null))
{
    exampleDataList.Add(new PersonalData
        {
            firstname = col1Value.ToString(),
            lastname  = col2Value.ToString(),
            address   = "" + col3Value,
            salary    = "" + col4Value
        });
}
```
