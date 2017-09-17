
## [Adding CSS class to Html.BeginForm()](http://stackoverflow.com/questions/13984029/adding-css-class-to-html-beginform)

```cs
@using (Html.BeginForm("ActionName", "ControllerName",
            new { ReturnUrl = ViewBag.ReturnUrl },
            FormMethod.Post, new { @class="login-form" }))
{
  etc.
}
```

## [Searching with a dropdown list in asp.net MVC](http://stackoverflow.com/questions/30125142/searching-with-a-dropdown-list-in-asp-net-mvc)

```cs
public ActionResult Index(string CompanyID)
{
    DentiCareEntities db = new DentiCareEntities();
    ViewBag.CompanyId = new SelectList(db.Companies, "CompanyId", "CompanyName", CompanyID);    // preselect item in selectlist by CompanyID param

    if (!String.IsNullOrWhiteSpace(CompanyID))
    {
        return View();
    }vg
Center

SP_GET_ACTUAL
-- exec SP_GET_ACTUAL 'AkasakaI','Beam','1'

exec SP_GET_ACTUAL 'Shinhibiya','Beam','9'

SP_GET_REPORT_DRAWING_REPORT_CENTER

exec SP_GET_REPORT_DRAWING_REPORT_CENTER 'Shinhibiya','Beam','9'

SP_GET_REPORT_DRAWING_REPORT_CENTER_HEAD

-- exec SP_GET_REPORT_DRAWING_REPORT_CENTER_HEAD 'AkasakaI','Beam','1'
-- exec SP_GET_REPORT_DRAWING_REPORT_CENTER_HEAD 'Shinhibiya','Beam','9'



    return View(db.Treatments.Where(x => x.CompanyID == CompanyID).Take(50));
}
```

```cs
@model IEnumerable<Treatment>

@{
    ViewBag.Title = "Index";
    Layout = "~/Views/Shared/_Layout.cshtml";
}

<h2>Quickly Generate Invoice</h2>

@using (Html.BeginForm("Index", "GenerateInvoice", FormMethod.Get))
{
    @Html.AntiForgeryToken()

    @Html.DropDownList("CompanyId", (SelectList)ViewBag.CompanyId, "Select Company", new { @class = "form-control" })
    <input type="submit" value="Search" class="btn btn-primary" />
}

@if(Model != null && Model.Any())
{
    foreach(var item in Model)
    {
        @Html.DisplayFor(model => item)
    }
}
```

## From

```cs
@using (Html.BeginForm("AddPhoneNumber", "Manage", FormMethod.Post, new { @class = "form-horizontal", role = "form" }))
{
    @Html.AntiForgeryToken()
    <h4>Add a phone number</h4>
    <hr />
    @Html.ValidationSummary("", new { @class = "text-danger" })
    <div class="form-group">
        @Html.LabelFor(m => m.Number, new { @class = "col-md-2 control-label" })
        <div class="col-md-10">
            @Html.TextBoxFor(m => m.Number, new { @class = "form-control" })
        </div>
    </div>
    <div class="form-group">
        <div class="col-md-offset-2 col-md-10">
            <input type="esubmit" class="btn btn-default" value="Submit" />
        </div>
    </div>
}

@section Scripts {
    @Scripts.Render("~/bundles/jqueryval")
}
```

## [ASP.NET MVC - How to show unauthorized error on login page?](http://stackoverflow.com/questions/1498727/asp-net-mvc-how-to-show-unauthorized-error-on-login-page)

```cs
[AttributeUsage(AttributeTargets.Class | AttributeTargets.Method)]
public class CustomAuthorizeAttribute : AuthorizeAttribute
{

    // NOTE: This is not thread safe, it is much better to store this
    // value in HttpContext.Items.  See Ben Cull's answer below for an example.
    private bool _isAuthorized;

    protected override bool AuthorizeCore(System.Web.HttpContextBase httpContext)
    {
        _isAuthorized = base.AuthorizeCore(httpContext);
        return _isAuthorized;
    }

    public override void OnAuthorization(AuthorizationContext filterContext)
    {
        base.OnAuthorization(filterContext);

        if(!_isAuthorized)
        {
            filterContext.Controller.TempData.Add("RedirectReason", "Unauthorized");
        }
    }
}
```

```cs
@if(TempData["RedirectReason"] == "Unauthorized")
{
    <b>You don't have permission to access that area</b>
}
```

----------------------------------------

## Filters

 AjaxOnly
 HttpDelete
 HttpGet
 HttpHead
 HttpPost
 HttpPut
 RequireHttps

 Timeout
 Cache
 Authorize
 HandleError

```cs
[HttpPost] public ActionResult Create(ItineraryItem data)
{
	if (ModelState.IsValid)
	{
		// Handle saving the data only if // the model state is valid
	}
	else
	{
		ModelState.AddModelError("", "The data you entered was not valid");
	}
	return View();
}
```
------------------------------

## Redirect Page

เรื่องของการ ReDirect

[UnAuthorized Page Access in MVC - ReDirect to UnAuthrized view instead of Login Page](http://stackoverflow.com/questions/22074474/unauthorized-page-access-in-mvc-redirect-to-unauthrized-view-instead-of-login)


```cs
public class CustomAuthorize : AuthorizeAttribute
{
    protected override void HandleUnauthorizedRequest(AuthorizationContext filterContext)
    {
        //filterContext.Result = new HttpUnauthorizedResult(); // Try this but i'm not sure
          filterContext.Result = new RedirectResult("~/Home/Unauthorized");
    }

    public override void OnAuthorization(AuthorizationContext filterContext)
    {
        if (this.AuthorizeCore(filterContext.HttpContext))
        {
            base.OnAuthorization(filterContext);
        }
        else
        {
            this.HandleUnauthorizedRequest(filterContext);
        }
    }

}
```
