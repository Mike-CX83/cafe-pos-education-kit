# push to github — madoxhankins-lang

**Remote is already set** in this folder:

`https://github.com/madoxhankins-lang/cafe-pos-education-kit.git`

## step 1 — create the empty repo (required)

`git push` fails with “repository not found” until this exists.

1. Sign in as **madoxhankins-lang** on GitHub.
2. Open **New repository**: [github.com/new](https://github.com/new)
3. **Repository name:** `cafe-pos-education-kit`
4. Choose **Public** (or Private).
5. **Do not** add README, .gitignore, or license (keep it empty).
6. Click **Create repository**.

## step 2 — push from this mac

```bash
cd ~/Desktop/cafe-pos-education-kit
git push -u origin main
```

If Git asks for credentials, use a **Personal Access Token** as the password (HTTPS), or set up **SSH** and change the remote:

```bash
git remote set-url origin git@github.com:madoxhankins-lang/cafe-pos-education-kit.git
git push -u origin main
```

## different repo name?

If you used another name on GitHub, fix the remote:

```bash
git remote set-url origin https://github.com/madoxhankins-lang/YOUR_REPO_NAME.git
git push -u origin main
```
