# data model — matches `db/setup.sql`

your repo ships **mysql** schema in [db/setup.sql](../db/setup.sql). entity framework models should **line up** with these tables unless the instructor gives a different script.

---

## tables at a glance

| table | role |
|-------|------|
| `Server` | wait staff; `HireDate`, `TermDate` (null = still employed) |
| `CafeOrder` | one ticket; links `ServerID`, optional `PaymentTypeID`, `OrderDate` |
| `OrderItem` | one line on a ticket; links `OrderID`, `ItemPriceID`, `Quantity`, money fields |
| `Item` | menu item name + category |
| `ItemPrice` | price for an item for a **time of day** + date range (`StartDate`/`EndDate`) |
| `TimeOfDay` | breakfast, lunch, etc. |
| `PaymentType` | cash, visa, … |
| `Category` | menu grouping |

---

## open vs closed order

- **open:** `CafeOrder.PaymentTypeID` **is null** (readme).  
- **closed:** `PaymentTypeID` points at a row in `PaymentType`.

no card number column exists — good — you only store **which payment type**.

---

## readme says itemid + quantity — sql says itempriceid

readme: “add items … based on `ItemID` and `Quantity`.”

schema: `OrderItem` references **`ItemPriceID`**, not `ItemID` directly.

**what that means in practice:**

- each **sellable price** is a row in `ItemPrice` (item + time-of-day + effective dates).  
- when user picks an **item** in the ui, you must pick **which `ItemPriceID`** to use — often: filter `ItemPrice` rows for that `ItemID` where **today** is between `StartDate` and `EndDate` (watch null `EndDate` as “still active”), and match a `TimeOfDay` rule your instructor wants (sometimes “current meal period” or “always lunch” for the assignment).  

**simplest defensible approach for a crunch:** pick one rule in comments (`//use first active itemprice for this item for today`) and implement that consistently.

---

## relationships (plain language)

- one **server** has many **orders** over time.  
- one **order** has many **order items**.  
- one **order item** points to one **item price** row (which points to one **item**).  

---

## money fields

`CafeOrder` has `SubTotal`, `Tax`, `Tip`, `AmountDue` nullable. readme may not require full register math. **minimum:** store line `ExtendedPrice` on `OrderItem` if you add lines; totals can be computed on save or left for later — **confirm with rubric**.

---

## seed data

`setup.sql` inserts servers, categories, items, prices, payment types. you should see rows in mysql workbench or `mysql` cli after import.
