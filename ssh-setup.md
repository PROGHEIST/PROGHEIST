This error means that Git is trying to use **SSH** to clone the repo, but it **can’t authenticate your public key with GitHub**. Here’s how you can fix it:

---

### ✅ Step-by-step fix:

#### 1. **Check if you have an SSH key**
Run:
```bash
ls ~/.ssh
```
Look for files like `id_rsa` and `id_rsa.pub` or `id_ed25519` and `id_ed25519.pub`.

If you **don’t see any `.pub` key**, generate one:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```
Just press **Enter** at every prompt to accept defaults.

---

#### 2. **Add your SSH key to the SSH agent**
```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

---

#### 3. **Add your public key to GitHub**
- Copy your public key:
  ```bash
  cat ~/.ssh/id_ed25519.pub
  ```
- Go to [https://github.com/settings/keys](https://github.com/settings/keys)
- Click **"New SSH key"**
- Paste the key and save.

---

#### 4. **Test your SSH connection**
```bash
ssh -T git@github.com
```
You should see:
> Hi `your-username`! You've successfully authenticated...

---

#### 5. **Try cloning again**
```bash
git clone git@github.com:PROGHEIST/terravision.git
```

---

### 🔄 Alternative: Use HTTPS instead of SSH
If you don't want to set up SSH, just clone using HTTPS:

```bash
git clone https://github.com/PROGHEIST/terravision.git
```

---

Let me know which method you want to use and I’ll guide you further if needed.
