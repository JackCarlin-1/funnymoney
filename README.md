# Funny Money: deploy on Vercel

This is a plain static site (no build step). Files must sit at the TOP LEVEL of the repository.

## 1. Put the files in a GitHub repository
1. On github.com click New repository, name it (for example funny-money), choose Private, click Create repository.
2. Click "uploading an existing file".
3. Unzip this zip, then drag the FILES inside (index.html, firebase-config.js, manifest.webmanifest, sw.js,
   the three icon PNGs, vercel.json, README.md) onto the page. Do not drag a folder that contains them.
4. Click Commit changes.

## 2. Deploy on Vercel
1. Go to vercel.com, sign in with GitHub, click Add New > Project, and Import your repository.
2. Framework Preset: Other. Leave Build Command and Output Directory empty (or default). Root Directory: ./
3. Click Deploy. Vercel gives you a link like your-project.vercel.app.

## 3. Allow the new link in Firebase (required)
Firebase console > Authentication > Settings > Authorized domains > Add domain > your-project.vercel.app
(without https://). Sign-in will not work on the new link until you do this.

## 4. Use it
Open the link in Safari on your iPhone > Share > Add to Home Screen. Sign in with your existing email and password.
Your data lives in Firebase, so everything is already there.

## Updating later
Replace the changed files in the repository (Add file > Upload files, or edit on GitHub). Vercel redeploys automatically
within a minute.
