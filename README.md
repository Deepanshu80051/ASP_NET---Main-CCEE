# ASP_NET---Main-CCEE

## Partial View
1. Reusable view component
2. UI ka small part (header, footer, menu)
3. File name mostly _PartialName.cshtml
4. Partial View me @RenderBody() nahi hota
```
@Html.Partial("_Header")
or
@await Html.PartialAsync("_Header")

🔥Partial View Start with  _

```
## ChildAction
1. Direct URL se call nahi hota
2. Sirf View ke andar call hota hai
3. URL se call- Action Not Child && View Se call- Child Not action
4. Question bole “reusable UI without layout” → Partial View
5. Question bole “action not callable via URL” → Child Action


```
[ChildActionOnly]
public IActionResult Menu()
{
    return PartialView("_Menu");
}
call kaise karte h :-
@Html.Action("Menu", "Home")

```
## Layout
1. File → _Layout.cshtml
2. @RenderBody()
3. View → Layout inherit karta hai
4. One layout → multiple views
```
Layout ko view k saatth use
Layout = "~/Views/Shared/_Layout.cshtml";
or
_ViewStart.cshtml:- automatically
Layout = "_Layout";

```
## Bundling
1. Multiple CSS/JS files ko ek file me combine karna
2. ❓ Performance improve kaise hoti hai?
✅ Bundling
## Minification
1. Extra spaces, comments remove and file size kam

* ❓ Bundles kaha define hote hain?
✅ BundleConfig
```
bundles.Add(new ScriptBundle("~/bundles/js")
    .Include("~/Scripts/jquery.js"));

CSS :-
@Styles.Render("~/Content/css")
Java Script :-
@Scripts.Render("~/bundles/js")
```
## Custom Helper Function

1. Reusable HTML logic
2. Static class + extension method
3. ❓ Custom HTML generate karne ke liye?
✅ Custom Helper
```
public static class CustomHelper
{
    public static string Hello()
    {
        return "Hello MVC";
    }
}

```
## Asynchronous Action
```
public async Task<IActionResult> Index()
{
    await Task.Delay(1000);
    return View();
}

```
## Error Handling in MVC (MCQ Favorite)
Techniques:

1. Try-Catch

2. Custom Error Page

3. Logging
```
try { }
catch(Exception ex)
{
    // Log error
}
```
MCQ Direct : - 

❓ Error track karne ke liye?
✅ Logging


## Filter
1. Cross-cutting concerns handle karta hai..
2. execute code before action” → Filter
```
Types (MCQ GOLD):

Authorization Filter

Action Filter

Result Filter

Exception Filter
```
## Custom Action Filter
Inherit from  ActionFilterAttribute
```
public class LogFilter : ActionFilterAttribute
{
    public override void OnActionExecuting(...)
}

```
