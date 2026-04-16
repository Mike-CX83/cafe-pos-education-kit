# phase 04 — repositories or services (optional layer)

## prerequisite

phase 02–03 stable.

## goal

some teams put all linq in **repository** classes; some keep linq in **controllers** for small homework. pick **one** style for this project.

## steps you do

1. if repository: interface + class per aggregate (`IOrderRepository`).  
2. if not: keep queries in controllers but **keep methods short** — extract private methods when messy.  

## sanity check

you can unit test **something** later (optional for week 5).

## common mistakes

- giant controller methods — hard to debug  

## reflection

did the course require repositories this week? if no, skip.
