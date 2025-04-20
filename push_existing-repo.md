To push a local project to an **existing remote GitHub repository**, follow these steps:

---

### ✅ **Steps to Push Local Project to Existing Repo**

#### 1. **Initialize Git (if not already initialized)**

```bash
git init
```

#### 2. **Add your remote repository URL**

```bash
git remote add origin https://github.com/your-username/your-repo-name.git
```

> Replace `your-username` and `your-repo-name` with your actual GitHub username and repo name.

#### 3. **Add all files**

```bash
git add .
```

#### 4. **Commit your changes**

```bash
git commit -m "Initial commit"
```

#### 5. **Push to the existing repository (main branch)**

If your remote uses `main` (most likely):

```bash
git push -u origin main
```

> If your remote uses `master` instead of `main`:
```bash
git push -u origin master
```

---

### ✅ Check Remote Branch Name (Optional)

If you're unsure about the remote branch name:

```bash
git branch -r
```

---

Let me know if you're using GitHub Desktop or VS Code Git panel instead — I can guide you through that too!
