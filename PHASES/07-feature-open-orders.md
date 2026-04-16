# phase 07 — feature: open orders on home

## prerequisite

phases 05–06; `CafeOrder` queryable.

## goal

home page lists **only** orders where `PaymentTypeID == null`.

## steps you do

1. linq filter on `CafeOrder`.  
2. pass list to `Views/Home/Index.cshtml`.  
3. foreach order: show id, maybe server name (join or navigation).  
4. link to `Details` with `asp-route-id`.  

## sanity check

closed orders (if you seed one manually) do not appear.

## common mistakes

- forgot `.AsNoTracking()` for read-only (optional perf tip)  
- n+1 queries — use `.Include()` for server  

## reflection

how do you prove in sql that an order is open?
