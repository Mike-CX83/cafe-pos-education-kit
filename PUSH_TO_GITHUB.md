# github remotes

## primary (pushed)

**Your account:** [github.com/Mike-CX83/cafe-pos-education-kit](https://github.com/Mike-CX83/cafe-pos-education-kit)

This Desktop folder tracks:

```text
origin → https://github.com/Mike-CX83/cafe-pos-education-kit.git
```

Updates:

```bash
cd ~/Desktop/cafe-pos-education-kit
git add .
git commit -m "your message"
git push
```

## optional — also push to another account (e.g. son)

Add a second remote (do **not** remove `origin` unless you want to):

```bash
git remote add son https://github.com/madoxhankins-lang/cafe-pos-education-kit.git
```

Create an **empty** repo `cafe-pos-education-kit` under that account first, then:

```bash
git push -u son main
```
