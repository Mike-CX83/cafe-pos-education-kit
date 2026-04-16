# prd — fourth wall cafe pos (student study draft)

**purpose:** turn the course README into **testable** behavior. use the checkboxes when you manually test before submit.

**source of truth:** [README.md](../README.md). this prd is a student aid only.

---

## product goal

staff use a **web browser** to run a small **point of sale** for the cafe: create orders, attach a **server**, add **line items**, then **close** the order by choosing a **payment type**. we do **not** store card numbers (external payment imaginary).

---

## definitions

- **open order:** a row in `CafeOrder` where `PaymentTypeID` is **null** (see README sample interaction).
- **closed order:** `PaymentTypeID` is **not** null.
- **active server:** for this course, interpret as: hired, and not terminated — use `Server` where `TermDate` is null or today is before term (your instructor may specify exact rule). `HireDate`/`TermDate` live in `db/setup.sql`.

---

## user stories and acceptance

### u1 — main menu / home

- [ ] user can see **open orders** (only unpaid / not finalized by payment type).
- [ ] user can start **create new order** from home.

**how to test:** open home; list shows only open orders; button exists for new order.

---

### u2 — create order (server + redirect)

- [ ] flow shows **servers that can take an order** (active per your rule).
- [ ] user **selects one server**.
- [ ] app **creates** a `CafeOrder` with **current** `OrderDate` and links `ServerID`.
- [ ] after create, browser goes to **order details** for that order id (readme: `RedirectToAction` with order id).

**how to test:** create order; url or page shows the new order; database row exists.

---

### u3 — view open orders and order details

- [ ] home lists open orders.
- [ ] each open order has a way to open **details** (link or button).
- [ ] details shows **line items** for that order (may be empty right after create).

**how to test:** pick an order from home; see details; lines match `OrderItem` rows for that `OrderID`.

---

### u4 — add items to an order

readme text mentions `ItemID` and `Quantity`. the provided sql schema stores lines in `OrderItem` with **`ItemPriceID`** and **`Quantity`** (price depends on item + time-of-day row). you must add rows that make sense for pricing (see [DATA_MODEL.md](DATA_MODEL.md)).

- [ ] from details, user can open **add items** (same page section or separate page).
- [ ] user sees **available items** (from `Item` / pricing as your instructor expects).
- [ ] choosing an item adds a line (or updates quantity — readme implies add; simplest is insert line).
- [ ] after add, **redirect back to details** for same order (`RedirectToAction` with order id).

**how to test:** add item; details list updates; refresh shows same data.

---

### u5 — pay and close

- [ ] from details, **process payment** leads to **payment types** list.
- [ ] picking a type opens a **finalize** step (form).
- [ ] submit sets **`PaymentTypeID`** on the order (no card fields required).
- [ ] order **disappears from open orders** on home.
- [ ] readme sample: after finalize, go **back to home**.

**how to test:** pay; home no longer lists it as open; db shows non-null `PaymentTypeID`.

---

## out of scope (unless instructor adds)

- real payment processor, pci, card validation  
- refunds, voids, removing line items (not required by readme)  
- authentication / login (unless assigned)  

---

## non-functional

- **minimal ui** is ok if flows work (instructor said clean beats fancy).  
- use **linq** / **ef** where the course expects it.  

---

## hint from readme (viewbag)

if a multi-step flow needs an id in the view, `ViewBag.OrderId = orderId;` is acceptable. strongly typed view models are also fine if you prefer.
