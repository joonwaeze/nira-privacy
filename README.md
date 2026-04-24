# Nira Privacy Policy — GitHub Pages Deployment

This folder contains a self-contained static site for Nira's privacy policy.
It has no external dependencies and loads instantly. Deploy it to GitHub Pages
to get a stable public URL for App Store Connect and TestFlight.

---

## Step 1 — Create the GitHub Repository

1. Go to [https://github.com/new](https://github.com/new)
2. Repository name: `nira-privacy`
3. Set visibility to **Public** (required for free GitHub Pages)
4. **Do NOT** initialise with a README — you'll push your own files
5. Click **Create repository**

---

## Step 2 — Push the Files

Run these commands from inside the `privacy-site/` folder:

```bash
cd privacy-site
git init
git add .
git commit -m "Add Nira privacy policy site"
git branch -M main
git remote add origin https://github.com/YOUR_GITHUB_USERNAME/nira-privacy.git
git push -u origin main
```

Replace `YOUR_GITHUB_USERNAME` with your actual GitHub username.

---

## Step 3 — Enable GitHub Pages

1. Go to your repo on GitHub: `https://github.com/YOUR_USERNAME/nira-privacy`
2. Click **Settings** → **Pages** (in the left sidebar)
3. Under **Source** → select **Deploy from a branch**
4. Branch: `main` | Folder: `/ (root)`
5. Click **Save**
6. Wait 1–2 minutes for GitHub to build the site
7. Your live URL will appear at the top of the Pages settings:
   ```
   https://YOUR_USERNAME.github.io/nira-privacy
   ```

---

## Step 4 — Verify Before Submitting to Apple

- Open the URL on your iPhone browser — confirm it loads correctly and all sections are visible
- Open in an incognito / private window — confirm no login is required to view the page
- Check that tables, lists, and the contact section all render without content being cut off

---

## Step 5 — Add the URL to App Store Connect

**App listing:**
1. Go to [App Store Connect](https://appstoreconnect.apple.com)
2. Select your app → **App Information**
3. Scroll to **Privacy Policy URL**
4. Paste your GitHub Pages URL
5. Save

**TestFlight:**
1. Go to your app → **TestFlight**
2. Select your build → **Test Information**
3. Scroll to **Privacy Policy URL**
4. Paste the same GitHub Pages URL
5. Save and re-submit your build for TestFlight review if needed

---

## Notes

- The `index.html` file is fully self-contained — no CDN, no external fonts, no JavaScript.
- To update the policy: edit `docs/PRIVACY_POLICY.md` in the main Nira project,
  regenerate `index.html`, and push to the `nira-privacy` repo. GitHub Pages
  will rebuild automatically within a minute or two.
- The live URL is permanent as long as the repo is public and GitHub Pages is enabled.
