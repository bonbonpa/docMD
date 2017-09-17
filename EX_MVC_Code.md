## MVC

### Controller

```cs
public ActionResult xxx(int? id)
{
    if(id==null)
        return new HttpStatusCodeResulr(HttpStatusCode.BadRequest);
    Product product = db.Products.Find(id);
    if(product == null)
    {
        return HttpNotFound();
    }
    return View();
}

//model
  public class ContactContext : DbContext
    {
        public DbSet<Contact> Contacts { get; set; }

    }


//Routing
[Route("home/create")]
public ActionResult Create()
{
    return View();
}

//Claim
```

### C# Code

```cs
string temp = "AAA" + artname + "AAA" + artname;

same best

string tempp = $"AAA {artname} AAA {Artname}";
```