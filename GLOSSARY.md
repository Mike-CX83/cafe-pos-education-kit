# glossary — slow definitions

terms appear in the order you might meet them building this assignment.

---

## .net

microsoft’s runtime and libraries. your **c#** code runs on **.net**.

---

## asp.net core

the **web** part of .net: http server, routing, mvc, razor pages.

---

## mvc

**model** = data + rules. **view** = html page. **controller** = glue for requests. **separation of concerns** so each file has one job.

---

## razor

syntax for `.cshtml` files: mix **html** with small **c#** snippets. `@` switches to c#.

---

## entity framework (ef) core

**orm** = object-relational mapper. you write **c# classes** and **linq**; ef turns that into **sql** for mysql.

---

## dbcontext

a class that represents **one session** with the database. it has `DbSet<T>` properties — each maps to a table in practice.

---

## migration

a **generated** file that describes how to change the database. for this class you may **apply** migrations to match `setup.sql` or **scaffold** from existing db — follow instructor.

---

## linq

query syntax in c# (`where`, `select`, …). used on `IQueryable` from ef.

---

## nullable

`int?` or `PaymentTypeID` nullable means “no value yet” — **open order** uses **null** payment.

---

## IActionResult

return type for controller actions: view, redirect, json, etc.

---

## model binding

automatically filling **action parameters** from form fields or route values (`/order/details/5` → `id`).

---

## ViewBag

dynamic bag of data for a view. readme suggests `ViewBag.OrderId = orderId;` when passing ids through flows.

---

## navigation property

on an entity class, a property that points to **related** rows (`Order` has `List<OrderItem>`). helps `.Include()` eager load.

---

## redirecttoaction

tells browser to **go to another url** after post — readme wants this after create/add item.

---

## ItemPriceID vs ItemID

see [DATA_MODEL.md](DATA_MODEL.md). orders store **priced lines**, not raw item ids only.
