
## Atribute routing

```cs
[Route("home/create")]
public ActionResult Create()
{
  return View();
}
```


## Filter

- Authorizations

### Authorize Attribute

```cs
[Authorize(Roles="administrator", Users="jsmith")]
[HttpPost]
public ActionResult Create(Customer customer)
{
  db.Customer.Add(customer);
  db.SaveCahnges();
  return RedirectToAction("Index");
}

```

### Controller-Level Filter

```cs
[Authorize]
public class CustomerController : Controller-Level
{
  public ActionResult Create()
  {
    //only authorized users as per controller attribute
  }
  [AllowAnonymous]
  public ActionResult Help()
  {
    //any visitor can view this page as per the method attribute
  }
}

```

- Action Filter

### Creating a Custom Action Filter
- Inherite from ActionFilterAttribute class
- Override OnActionexecuting method
- And/or override OnActionExecuted method

```cs
public class MyLoggingFilterActtribute : ActionFilterAttribute
{
  public override void OnActionExecuted(ActionExecutedContext filterContext)
  {
    var request = filterContext.HttpContext.Request;
    Logger.logRequest(request.UserHostAddress);
    base.OnActionExecuted(filterContext);
  }
}
```

```cs
public class Homecontroller : Controller
{
  //
  [MyLoggingFilter]
  public ActionResult Index()
  {
    return View();
  }
}
```


```cs
namespace xxx
{
  public class FilterConfig
  {
    public static void RegisterGlobalFilters(GlobalFilterCollection filters)
    {
      filters.Add(new HanddleErrorAtrribute());
      filters.Add(new MyLoggingFilterActtribute());
    }
  }
}

```

- ResultFilter

putput Cahcing

```cs
[OutputCache(Duration=1800)]
public ActionResult Index()
{
  return View();
}

[OutputCache(Duration=120,VaryByParam="id")]
public ActionREsult Details(int id)
{
  Product p = db.Products.Find(id);
  return View(p);
}

```

- Exception filter

```xml
<!--web.config-->

<system.web>
  <customErrors mode="On" />
</system.web>
```

```cs
[HandleError(View="MyError")]
[HttpPost]
public ActionResult Create(Customer customer)
{
  db.Customer.Add(customer);
  db.SaveChanges();
  return RedirectToAction("Index");
}
```
