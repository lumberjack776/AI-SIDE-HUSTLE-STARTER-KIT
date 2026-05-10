# A.I. Side Hustle Sales Page — Vercel Deployment

This is a static sales page ready to drop into Vercel. No build step, no framework, no server. Just files.

## What's in here

```
ai-side-hustle-sales-page/
├── index.html              ← The sales page itself
├── vercel.json             ← Vercel config (clean URLs, caching)
├── public/
│   └── images/
│       ├── jason.jpg            (founder photo, 17 KB)
│       ├── product-mockup.jpg   (book cover, 62 KB)
│       └── inside-preview.jpg   (3-page preview, 56 KB)
└── README.md               ← This file
```

Total page weight: ~140 KB. Loads under a second on any connection.

---

## How to deploy (3 ways)

### Option 1: Drag & drop (easiest — 60 seconds)

1. Go to https://vercel.com/new
2. Sign in with GitHub, Google, or email (free)
3. On the dashboard, click **"Add New" → "Project"**
4. Click the **"deploy a static site"** option, OR drag the entire `ai-side-hustle-sales-page` folder onto the page
5. Vercel auto-detects it as static, click **Deploy**
6. Done — you'll get a URL like `ai-side-hustle-xyz.vercel.app`

### Option 2: GitHub (best for ongoing edits)

1. Create a new GitHub repo
2. Upload these files to it
3. In Vercel, click **"Add New" → "Project" → Import** your repo
4. Click **Deploy** (no settings to change)
5. Every time you push to GitHub, Vercel auto-redeploys

### Option 3: Vercel CLI (advanced)

```bash
npm i -g vercel
cd ai-side-hustle-sales-page
vercel
```

Follow prompts. Done.

---

## Connect your custom domain

Once deployed:

1. In your Vercel project → **Settings → Domains**
2. Add `aisidehustle.digiblazemedia.com` (or whatever subdomain you want)
3. Vercel shows you the DNS record to add at IONOS (your domain registrar)
4. Add the CNAME record at IONOS pointing to `cname.vercel-dns.com`
5. Wait 5-30 minutes for DNS to propagate
6. Done — your sales page is live at your custom domain

**Important:** This sales page links the checkout button to `https://aisidehustle.digiblazemedia.com/e7c3d4d4` (your Systeme.io checkout). You'll want to use a *different* subdomain for the Vercel sales page so it doesn't conflict — for example:
- `start.digiblazemedia.com` → Vercel sales page
- `aisidehustle.digiblazemedia.com/e7c3d4d4` → Systeme.io checkout

OR keep aisidehustle.digiblazemedia.com pointed at Systeme.io and put the new sales page at something like `getstarted.digiblazemedia.com`.

---

## How to edit content later

The page is a single HTML file. To edit:

1. Open `index.html` in any text editor (VS Code, Notepad, TextEdit, etc.)
2. Find the text you want to change (Cmd/Ctrl+F)
3. Edit it
4. Save the file
5. If you used Option 1 (drag-drop): re-upload the folder to Vercel
6. If you used Option 2 (GitHub): commit and push, auto-deploys

### Common edits

**Change the price:** Search for `$17` — it appears in the price box, CTAs, and price stack.

**Change checkout link:** Search for `e7c3d4d4` — there are 9 instances. Replace all with your new checkout URL.

**Replace product mockup:** Drop a new image into `public/images/` and rename it `product-mockup.jpg` (overwrite the old one).

**Replace founder photo:** Same — drop in as `public/images/jason.jpg`.

---

## Adding real testimonials later

When you get real buyer testimonials (with photos, full names, and ideally a LinkedIn link to verify), find the section starting with:

```html
<!-- HONEST PROOF -->
```

Replace it with a standard testimonials block. Keep the founder note section as-is — it's gold.

---

## Performance notes

- **140 KB total page weight** — most "make money online" sales pages are 5-15 MB. Yours loads in milliseconds.
- **No tracking pixels** added by default. If you want Pinterest, Facebook, or Google Analytics tags, add them inside the `<head>` section.
- **Mobile-optimized.** All breakpoints handled at 720px.
- **No JavaScript dependencies.** Works even if scripts are blocked.

---

## Questions?

This is your file. You own it forever. No subscription, no platform lock-in. If Vercel changes their pricing or shuts down, you can deploy these same files to Netlify, Cloudflare Pages, GitHub Pages, or any static host with no changes.
