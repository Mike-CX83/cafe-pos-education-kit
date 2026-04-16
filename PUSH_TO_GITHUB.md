# push this folder to github (son's repo)

1. Create an **empty** repository on GitHub (no README) under his account.

2. In Terminal:

```bash
cd ~/Desktop/cafe-pos-education-kit
git remote add origin https://github.com/SON_USERNAME/REPO_NAME.git
git push -u origin main
```

Replace `SON_USERNAME` and `REPO_NAME` with his real repo. Use SSH instead of HTTPS if he uses SSH keys.

3. If `origin` already exists from a mistake:

```bash
git remote remove origin
git remote add origin <correct-url>
git push -u origin main
```
