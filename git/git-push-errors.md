Here is the **clean step-by-step Git workflow (English Markdown)** focused only on **clone → README → init → commit → SSH → remote check → push**:

````markdown
# 📌 Git Setup & Push Workflow (Step by Step)

---

## 1. Create README file
```bash
touch README.md
````

---

## 2. Initialize Git repository

```bash
git init
```

---

## 3. Add files to staging

```bash
git add .
```

---

## 4. First commit

```bash
git commit -m "initial commit"
```

---

## 5. Setup SSH (One-time)

Generate SSH key:

```bash
ssh-keygen -t ed25519 -C "your_email@gmail.com"
```

Start SSH agent:

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

Show public key:

```bash
cat ~/.ssh/id_ed25519.pub
```

👉 Then add this key to GitHub:
[https://github.com/settings/keys](https://github.com/settings/keys)

---

## 6. Check remote origin

```bash
git remote -v
```

### 👉 If NO remote exists:

Output will be:

```bash
fatal: not a git repository (or any of the parent directories): .git
```

OR
(no output at all)

---

### 👉 If remote already exists:

Output will be like:

```bash
origin  https://github.com/username/repo.git (fetch)
origin  https://github.com/username/repo.git (push)
```

---

## 7. Remove existing remote (if needed)

```bash
git remote remove origin
```

Check again:

```bash
git remote -v
```

Expected output:

```bash
# no output (empty)
```

---

## 8. Add SSH remote

```bash
git remote add origin git@github.com:USERNAME/REPO_NAME.git
```

Verify:

```bash
git remote -v
```

Expected output:

```bash
origin  git@github.com:USERNAME/REPO_NAME.git (fetch)
origin  git@github.com:USERNAME/REPO_NAME.git (push)
```

---

## 9. Push to GitHub (first time)

```bash
git branch -M main
git push -u origin main
```

---

## 📌 Final Workflow Summary

```bash
touch README.md
git init
git add .
git commit -m "initial commit"

git remote remove origin   # (only if exists)
git remote add origin git@github.com:USERNAME/REPO_NAME.git

git branch -M main
git push -u origin main
```

```

If you want, I can also make a **:contentReference[oaicite:0]{index=0}** or a **:contentReference[oaicite:1]{index=1}**.
```
