# critical path — ~3 day plan

this is a **schedule**, not a moral judgment. skip depth docs until the app runs.

---

## day 1 — environment + spine

**goal:** mysql running, asp.net project runs, ef can talk to `FourthWallCafe`, you can show **one** page backed by the database.

**tasks (order matters):**

1. start docker db: from repo root, `docker compose up -d` (or your class steps).  
2. run `setup-database.sh` or equivalent so `db/setup.sql` loads (see repo [README](../README.md) if your class has extra steps).  
3. `dotnet new mvc` (or blank solution + mvc project per course).  
4. add ef core + pomelo mysql (or provider your course uses). connection string points at `localhost:3306`, database `FourthWallCafe`, user matches docker.  
5. create `DbContext` with `DbSet<>` for tables you need **first** (at minimum: `CafeOrder`, `Server`, `OrderItem`, `Item`, `ItemPrice`, `PaymentType` — trim if course starts smaller).  
6. **either:** scaffold from existing database **or** hand-write entity classes to match `db/setup.sql` columns. names must match enough that queries work.  
7. run app; prove list page or `/` returns 200.

**end of day 1 check:** `dotnet run` works; no crash on startup; one read query works (even “count servers”).

**if time is short:** skip css. skip repositories until controllers work.

---

## day 2 — vertical slice: home + create + details

**goal:** home shows **open orders**; user can **create** order and land on **details** with correct id in the route or model.

**tasks:**

1. query open orders: `CafeOrder` where `PaymentTypeID == null` (linq).  
2. `Server` list filtered to **active** (define active = `TermDate == null` unless instructor says otherwise).  
3. post create: insert `CafeOrder` with `ServerID`, `OrderDate = DateTime.Now`, `PaymentTypeID = null`.  
4. `return RedirectToAction("Details", "Order", new { id = order.OrderID });` (names flexible).  
5. details get: load order + include order lines + item names via joins/navigation.

**end of day 2 check:** you can demo: home → create → details (empty lines ok).

---

## day 3 — add items + payment + polish

**goal:** full readme **sample interactions** pass manually.

**tasks:**

1. add item: show catalog; on pick, insert `OrderItem` with valid `ItemPriceID` + `Quantity`; recompute line price if required by rubric (`ExtendedPrice`).  
2. payment: list types; post sets `PaymentTypeID`; redirect home.  
3. walk through [PRD.md](PRD.md) checkboxes.  
4. fix null refs, routing typos, wrong includes.  

**end of day 3 check:** all prd boxes checked; project zipped or submitted per course.

---

## if you fall behind — cut scope in this order

1. keep: create order + details + payment (minimum story).  
2. defer: fancy layout, extra validation messages.  
3. do **not** defer: correct `PaymentTypeID` null/open logic, correct redirects with ids.  
4. add items: if stuck, implement **add one default quantity = 1** before quantity ui.

---

## daily timeboxing (suggestion)

- **25 min** read error + fix  
- **50 min** code one feature  
- **10 min** write 3 sentences: what broke, what fixed  

---

## link to phase docs

when you have time, use [PHASES/](PHASES/) for slower explanations. **do not block day 3 on reading all phases.**
