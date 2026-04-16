# phase 08 — feature: create order

## prerequisite

phase 07.

## goal

user picks **active server**; you insert `CafeOrder`; redirect to details.

## steps you do

1. get action: list servers where `TermDate == null` (or instructor rule).  
2. post action: `new CafeOrder { ServerID = ..., OrderDate = DateTime.Now, PaymentTypeID = null }`.  
3. `SaveChanges()`.  
4. `return RedirectToAction("Details", new { id = order.OrderID });`.  

## sanity check

new row in `CafeOrder`; browser url changes to details.

## common mistakes

- `OrderDate` left default `0001` — readme wants current time  
- forgot `SaveChanges()`  

## reflection

why is redirect better than returning the details view directly after post?
