# prompt templates — copy and edit

replace the brackets before sending.

---

## explain a concept

```
explain in plain language what [RedirectToAction] does and give a tiny example.
do not give me my assignment code.
```

---

## debug a crash

```
here is my full error message and stack trace:

[paste]

here is the file and line i think matters:

[paste]

what are 3 possible causes, ordered most likely first?
```

---

## narrow code request

```
give only the linq query for: open cafe orders where paymenttypeid is null.
include the method signature line but nothing else.
```

---

## quiz me

```
quiz me with 5 questions on [nullable foreign keys / ef include / razor for loops].
wait for my answer before the next question.
```

---

## review without rewriting

```
review this snippet for bugs and edge cases. list issues only. do not rewrite the whole file.

[paste]
```

---

## integrity check

```
explain how i would demo in my own words that an order is closed after payment.
no code.
```
