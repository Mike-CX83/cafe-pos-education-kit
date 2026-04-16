# github remotes

## primary (pushed)

**Your account:** [github.com/Mike-CX83/cafe-pos-education-kit](https://github.com/Mike-CX83/cafe-pos-education-kit)

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

---

## copy to [madoxhankins-lang](https://github.com/madoxhankins-lang) (cannot auto-push from your login)

Your GitHub user **cannot** create or push to another person’s account without their permission. So this machine keeps a **second remote** named `son` for when the repo exists **and** you have push access:

```text
son → https://github.com/madoxhankins-lang/cafe-pos-education-kit.git
```

### option a — easiest: fork (son does this while logged in as madoxhankins-lang)

1. Open **[Mike-CX83/cafe-pos-education-kit](https://github.com/Mike-CX83/cafe-pos-education-kit)**.
2. Click **Fork**.
3. Owner: **madoxhankins-lang**. Create fork.

Son then has the same files under **his** account (may be named `cafe-pos-education-kit` under his user). No password from you required.

### option b — empty repo + collaborator

1. Son logs in as **madoxhankins-lang**, **[New repository](https://github.com/new)**, name **`cafe-pos-education-kit`**, empty, create.
2. Repo **Settings → Collaborators**: add **Mike-CX83** with **Write** access (son accepts email if needed).
3. On your Mac:

```bash
cd ~/Desktop/cafe-pos-education-kit
git push -u son main
```

### option c — son’s token (not recommended)

Son creates a **Personal Access Token** and you `git push` using that URL as remote — only if you both understand token risk.
