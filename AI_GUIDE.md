# ai guide — tutor mode, not autopilot

you said you want to **write code yourself**. these rules keep ai in the **teacher** lane.

---

## rules

1. **paste errors verbatim** — include stack trace line, file name.  
2. **ask for explanation first** — “explain why redirecttoaction needs route values” before “write my controller.”  
3. **limit scope** — “give me **only** the linq for open orders, not the whole controller.”  
4. **refuse full file dumps** unless you are stuck **30+ minutes** and you named what you tried.  
5. **ask for a checklist** — “what 5 files do i touch for add-item post” instead of “build app.”  

---

## good prompts (patterns)

- “quiz me: what is nullable paymenttypeid on an open order?”  
- “give me 3 wrong answers and 1 right answer for what redirecttoaction does.”  
- “review my snippet and list bugs only, no rewrite.”  

bad prompts:

- “do the assignment”  
- “generate the whole solution”  

---

## academic integrity

your school rules apply. use ai to **learn**, not to **submit work you cannot explain**. if your instructor asks how payment works, you should be able to say: “i set paymenttypeid on cafeorder.”

---

## link

copy-paste shells: [templates/PROMPTS.md](templates/PROMPTS.md)
