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
