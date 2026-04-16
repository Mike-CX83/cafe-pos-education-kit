# phase 05 — controllers and routing

## prerequisite

phase 02.

## goal

you understand **route → action** and return `View()` vs `RedirectToAction()`.

## steps you do

1. add `OrderController` (name example) with `Details(int id)`.  
2. add route attribute or rely on convention `/Order/Details/5`.  
3. return `View(model)` with a **viewmodel** or entity (course may prefer viewmodels).  

## sanity check

typing url manually loads details page (even placeholder).

## common mistakes

- action name typo vs view file name  
- forgot `[HttpPost]` on forms  

## reflection

what is the difference between `return View()` and `return RedirectToAction()` for the user’s browser?
