# phase 10 — feature: add items

## prerequisite

phase 09; understand [DATA_MODEL.md](../DATA_MODEL.md) itempriceid.

## goal

user picks an item; you insert `OrderItem` with valid `ItemPriceID` and `Quantity`; redirect details.

## steps you do

1. get: build list of purchasable rows — at minimum each row shows item name + **itempriceid** as hidden or route.  
2. choose pricing rule: which `ItemPrice` row for “now” (document in comment).  
3. post: `new OrderItem { OrderID = id, ItemPriceID = ..., Quantity = n, ExtendedPrice = ... }`.  
4. `SaveChanges()`; `RedirectToAction("Details", new { id })`.  

## sanity check

refresh details; line persists; totals plausible.

## common mistakes

- quantity default 0  
- wrong price row — extended price does not match unit * qty  

## reflection

why does schema use `ItemPriceID` instead of raw `ItemID`?
