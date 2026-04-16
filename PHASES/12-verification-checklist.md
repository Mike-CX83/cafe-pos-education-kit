# phase 12 — verification checklist

## prerequisite

features 07–11 attempted.

## goal

manual test pass before submit.

## run through readme sample interactions

use [PRD.md](../PRD.md) checkboxes. minimum script:

1. **create:** home → create → pick server → lands details; new row in `CafeOrder`.  
2. **view open:** home lists only open orders; click through to details.  
3. **add item:** from details add flow → back to details; line in `OrderItem`.  
4. **pay:** payment flow → home; order not open; `PaymentTypeID` set.  

## edge cases (quick)

- bad order id in url  
- empty open order list (should not crash)  

## done when

- [ ] you can explain each step in plain english  
- [ ] project runs on a **fresh** clone with written steps (connection string!)  

## reflection

what would you demo first in a 2-minute video?
