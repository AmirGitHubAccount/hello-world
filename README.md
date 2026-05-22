# Hello World

A tiny interactive single-page site. Click the button — watch "Hello world" appear in a fresh vivid color every time.

## Live demo

> Fill this in after deploying: `https://<your-username>.github.io/<repo-name>/`

---

## Run locally

No build step required. Just open the file in any modern browser:

```
D:\Project\claude\Projects\Hello world\index.html
```

Or drag-and-drop `index.html` onto a browser tab.

---

## Deploy to GitHub Pages

### 1 — Create a new GitHub repository

1. Go to [github.com/new](https://github.com/new).
2. Name it anything (e.g. `hello-world`).
3. Set visibility to **Public** (required for the free GitHub Pages tier).
4. Leave *"Initialize this repository"* **unchecked** — you'll upload the file manually.
5. Click **Create repository**.

### 2 — Upload index.html

**Option A — browser upload (easiest)**

1. On the new repo page click **uploading an existing file**.
2. Drag `index.html` into the upload area (and `README.md` if you like).
3. Scroll down, add a commit message (e.g. `Initial commit`), and click **Commit changes**.

**Option B — Git CLI**

```bash
cd "D:\Project\claude\Projects\Hello world"
git init
git add index.html README.md
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

### 3 — Enable GitHub Pages

1. In your repository go to **Settings → Pages** (left sidebar).
2. Under **Source** select **Deploy from a branch**.
3. Set branch to **main** and folder to **/ (root)**.
4. Click **Save**.

### 4 — Get your URL

GitHub will show a banner:

> *Your site is live at* `https://<your-username>.github.io/<repo-name>/`

It usually takes 1–2 minutes for the first deployment to go live. Paste that URL into the **Live demo** section above.

---

## Tech stack

| Layer | Choice |
|-------|--------|
| Markup | HTML5 |
| Style | CSS3 (variables, keyframe animation) |
| Logic | Vanilla JS (ES6) |
| Font | Inter via Google Fonts |
| Dependencies | None |
