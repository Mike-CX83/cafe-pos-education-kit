# phase 02 — ef core models

## prerequisite

phase 01; database schema exists.

## goal

c# **entity classes** + **dbcontext** that match [db/setup.sql](../../db/setup.sql) for the tables you need.

## steps you do

1. add nuget packages: `Microsoft.EntityFrameworkCore`, mysql provider your course uses (often `Pomelo.EntityFrameworkCore.MySql`).  
2. create classes: properties match column names/types closely (`int`, `string`, `DateTime`, `decimal?`, …).  
3. on `DbContext`, add `DbSet<YourEntity>` for each table you query in v1.  
4. register context in `Program.cs` with `AddDbContext` and connection string.  

## sanity check

app starts without migration errors **or** run first migration if instructor requires — many classes use **database-first** from existing sql instead.

## common mistakes

- forgot `[Table("CafeOrder")]` if class name differs from table name  
- `Server` class name may clash with asp.net `Server` — use namespace or rename entity to `CafeServer` with table attribute  

## reflection

which entity has the nullable `PaymentTypeID`?
