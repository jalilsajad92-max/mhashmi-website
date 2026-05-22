# Muheeb Hashimi — Accounting & Tax Services Website

A professional static website built with [Astro](https://astro.build), deployable for free on **GitHub Pages**.

## 🌐 Live Preview 

After deployment, your site will be live at:
`https://YOUR_GITHUB_USERNAME.github.io`

---

## 📋 Before You Deploy — 3 Quick Steps

### Step 1 — Set Up the Contact Form (Formspree, free)

The contact form sends messages directly to your email using [Formspree](https://formspree.io).

1. Go to [formspree.io](https://formspree.io) and create a free account
2. Click **+ New Form**, name it (e.g. "Website Contact"), enter your email
3. Copy your **Form ID** (the part after `formspree.io/f/` in the endpoint URL)
4. Open `src/components/Contact.astro` and replace:
   ```
   const FORMSPREE_ID = 'YOUR_FORMSPREE_ID';
   ```
   with your actual ID, e.g.:
   ```
   const FORMSPREE_ID = 'xabcde12';
   ```

Free plan allows **50 submissions/month** — more than enough to start.

---

### Step 2 — Add Your Photo

1. Place your professional headshot in the `/public` folder and name it `muheeb.jpg`
2. Open `src/components/About.astro`
3. Find this block and replace the entire `<div class="photo-placeholder" ...>` section with:
   ```html
   <img src="/muheeb.jpg" alt="Muheeb Hashimi" />
   ```

**Photo tips:**
- Portrait orientation (3:4 ratio)
- Minimum 600×800 px
- Keep file size under 500 KB

---

### Step 3 — Update Your GitHub URL in `astro.config.mjs`

```js
// astro.config.mjs
export default defineConfig({
  site: 'https://YOUR_GITHUB_USERNAME.github.io',  // ← change this
  base: '/',
  output: 'static',
});
```

---

## 🚀 Deploy to GitHub Pages (Free)

### Option A — Deploy via GitHub (recommended, no coding needed)

1. Create a new **public** repository on GitHub (e.g. `my-website`)
2. Upload all files to the repository (drag and drop in GitHub UI, or use Git)
3. Go to repository **Settings → Pages**
4. Under **Source**, select **GitHub Actions**
5. Push or commit any change — the site will deploy automatically in ~2 minutes
6. Your site is live at `https://YOUR_USERNAME.github.io/`

> 💡 If you used a repository name other than your username (e.g. `my-website`),
> update `base: '/my-website/'` in `astro.config.mjs`.

### Option B — Deploy from your local machine

```bash
# 1. Install dependencies
npm install

# 2. Preview locally (optional)
npm run dev

# 3. Build the site
npm run build

# 4. Push to GitHub (GitHub Actions will deploy automatically)
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git push -u origin main
```

---

## 🎨 Customization Guide

| What to change | Where |
|---|---|
| Your photo | `/public/muheeb.jpg` + `src/components/About.astro` |
| Contact form email | Formspree dashboard |
| Services list | `src/components/Services.astro` |
| About text | `src/components/About.astro` |
| Hero headline | `src/components/Hero.astro` |
| Colors / fonts | `src/layouts/Layout.astro` (CSS variables) |
| Footer links | `src/components/Footer.astro` |
| Page title & SEO | `src/layouts/Layout.astro` |

---

## 🗂️ Project Structure

```
muheeb-hashimi-site/
├── public/
│   ├── favicon.svg
│   └── muheeb.jpg          ← your photo goes here
├── src/
│   ├── components/
│   │   ├── Nav.astro
│   │   ├── Hero.astro
│   │   ├── WhyMe.astro
│   │   ├── Services.astro
│   │   ├── About.astro
│   │   ├── Contact.astro
│   │   └── Footer.astro
│   ├── layouts/
│   │   └── Layout.astro    ← global styles & fonts
│   └── pages/
│       └── index.astro     ← main page (assembles all components)
├── .github/
│   └── workflows/
│       └── deploy.yml      ← GitHub Actions auto-deploy
├── astro.config.mjs
├── package.json
└── README.md
```

---

## 🔧 Local Development

```bash
npm install      # Install dependencies
npm run dev      # Start dev server at http://localhost:4321
npm run build    # Build for production → ./dist/
npm run preview  # Preview production build locally
```

Requires **Node.js 18+**. Download at [nodejs.org](https://nodejs.org).

---

## 💰 Hosting Costs

| Service | Cost |
|---|---|
| GitHub Pages | **Free** |
| Formspree (contact form) | **Free** (50 submissions/month) |
| Google Fonts | **Free** |
| Custom domain (optional) | ~$10–15 CAD/year via Namecheap or Google Domains |

**Total cost to run: $0/month.**

---

## 🌐 Custom Domain (Optional)

To use `www.muheebhashimi.ca` instead of `github.io`:

1. Buy a domain from [Namecheap](https://namecheap.com) or similar (~$15 CAD/yr)
2. In your domain registrar DNS settings, add:
   - `CNAME www → YOUR_USERNAME.github.io`
   - Or `A` records pointing to GitHub's IPs (see [GitHub docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site))
3. In GitHub repo Settings → Pages → Custom domain, enter your domain
4. Update `site:` in `astro.config.mjs` to your custom domain

---

Built with ❤️ using [Astro](https://astro.build) · Deployed on [GitHub Pages](https://pages.github.com)
