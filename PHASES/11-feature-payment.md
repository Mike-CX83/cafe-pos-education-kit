# phase 11 — feature: payment

## prerequisite

phase 09 (10 optional but typical before pay).

## goal

user picks `PaymentType`; post updates `CafeOrder.PaymentTypeID`; redirect home.

## steps you do

1. get: list rows from `PaymentType`.  
2. get: optional second step “finalize” with form — readme says selecting opens form; can be two steps or one.  
3. post: load order; set `PaymentTypeID`; `SaveChanges()`.  
4. `return RedirectToAction("Index", "Home")`.  

## sanity check

order no longer in open list; db shows non-null `PaymentTypeID`.

## common mistakes

- get vs post confusion — use `[HttpPost]` and antiforgery token in form  

## reflection

why is storing only payment **type** enough for this assignment?
