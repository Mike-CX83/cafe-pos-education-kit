# comment style (your contract)

you asked for **layman** comments and this shape:

- c# line comments: `//comment`  
- **lowercase** after `//`  
- **no space** after `//` unless you must for readability on long lines  
- do not restate what the code says (`//increment i`). say **why** or **what was confusing**.

---

## c# examples (style only)

```csharp
//map null payment to "still open" in the ui
if (order.PaymentTypeID == null)
{
    //...
}
```

```csharp
//ef needs this navigation or details page will null-ref
.Include(o => o.OrderItems)
```

---

## razor (.cshtml)

razor files are **mostly html**. server-side comments use razor syntax:

```cshtml
@*hide closed orders on home*@
```

avoid `//` inside pure html (browsers may not treat it as comment). inside `@{ }` blocks, `//` is c# again.

---

## when not to comment

- obvious one-liners  
- the comment repeats the identifier name  

## when to comment

- business rule from readme (“open means paymenttypeid null”)  
- non-obvious ef include / why dto exists  
- workaround for a bug you will forget tomorrow  
