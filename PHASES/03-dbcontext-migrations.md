# phase 03 — migrations (if required)

## prerequisite

phase 02.

## goal

database schema in mysql matches your models **or** you use **scaffold-dbcontext** from existing db — follow instructor.

## paths (pick one)

**a) code-first:** `dotnet ef migrations add InitialCreate` then `dotnet ef database update` — **warning:** may fight existing `setup.sql` tables. many classes instead **import sql once** and scaffold.

**b) database-first:** scaffold entities from live database — less hand-mapping.

## sanity check

ef can `SaveChanges()` a test row in dev **or** read `SELECT` without exception.

## common mistakes

- running migrations against production docker without backup  
- mismatch between ef model and actual column type  

## reflection

which approach did your instructor demonstrate this module?
