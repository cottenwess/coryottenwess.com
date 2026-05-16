# Personal Site

A static, single-page hub. No build step, no dependencies, no framework. Just an `index.html` and a CNAME file. The whole thing fits in your head.

## Editing

Open `index.html` in any text editor. All the CSS lives in the `<style>` block at the top, all the content lives in the `<body>` below. Project cards, elsewhere links, contact email: search and replace.

The two fonts (Fraunces and JetBrains Mono) load from Google Fonts. The color palette is in the `:root` block at the top of the CSS, named so it's obvious which is which.

## Deploying to GitHub Pages

1. **Create a new repository on GitHub.** Name it whatever you want. Make it public (private repos need a paid plan for Pages).
2. **Upload these files** to the repository. You can drag and drop them into the GitHub web interface if you're not in the mood for git on the command line.
3. **Edit `CNAME`** to contain only your actual domain on a single line. No `https://`, no `www.` unless you want www to be canonical. Just `yourdomain.com`.
4. **Turn on Pages.** In the repo, go to Settings → Pages. Under "Build and deployment," set Source to "Deploy from a branch," select `main` and `/ (root)`, and save.
5. **Point your domain.** At your domain registrar, edit DNS records:
   - Create an `A` record for `@` (apex/root) pointing to these four GitHub IPs:
     - `185.199.108.153`
     - `185.199.109.153`
     - `185.199.110.153`
     - `185.199.111.153`
   - Create a `CNAME` record for `www` pointing to `YOURUSERNAME.github.io`
6. **Wait.** DNS propagation takes anywhere from ten minutes to a few hours. Once it resolves, return to Settings → Pages and check the "Enforce HTTPS" box. GitHub will provision a free Let's Encrypt cert.

That's it. Edits to `index.html` go live within a minute of pushing.

## What lives where

- `index.html` — the entire site
- `CNAME` — your custom domain, one per line
- `README.md` — this file

## Adding pages later

When you want a second page (a real `/writing` index, an essay archive, etc.), drop a new HTML file in the repo root or a subfolder. The styling is self-contained per file so you can either copy the `<style>` block or refactor it into a shared `style.css`. No rush.
