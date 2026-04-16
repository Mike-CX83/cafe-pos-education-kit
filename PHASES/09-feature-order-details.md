# phase 09 — feature: order details

## prerequisite

phase 08.

## goal

details page shows order header + **order lines** (zero lines ok for new order).

## steps you do

1. load `CafeOrder` by id; `Include` order items → item price → item as needed.  
2. if id missing: `return NotFound()`.  
3. view: table of lines (quantity, name, extended price).  

## sanity check

matches data you see in mysql for `OrderItem` rows.

## common mistakes

- lazy load disabled — navigation null — add `Include`  

## reflection

what happens if user edits url to another order id?
