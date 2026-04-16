# phase 06 — views and razor

## prerequisite

phase 05.

## goal

a `.cshtml` page shows data from the controller **model**.

## steps you do

1. at top of view: `@model YourNamespace.SomeType`  
2. use `@Model.Property` (capital M on model object) per razor rules.  
3. loop: `@foreach (var x in Model.Lines) { ... }`  

## sanity check

page renders without runtime error when model non-null.

## common mistakes

- null model — add `if (Model == null)` or ensure controller always passes model  
- confusing `ViewBag` vs strongly typed `Model` — pick one style per page  

## reflection

when readme says `ViewBag.OrderId`, where is it set?
