# Ms Renovations Pro — Website

**Live site:** https://msrenovationspro.com  
**Stack:** Static HTML/CSS/JS — no build step, no dependencies  
**Hosting:** Cloudflare Pages (auto-deploys on push to `main`)

---

## Deploy via GitHub → Cloudflare Pages

1. Push this repo to GitHub (or it's already there)
2. Cloudflare Dashboard → Workers & Pages → your project → Settings → Git Integration
3. Set **Build command:** *(empty)*  
4. Set **Build output directory:** `/` (root)
5. Every `git push` to `main` auto-deploys in ~30 seconds

---

## File map

```
index.html                          ← main site (edit this)
privacy.html                        ← privacy policy
accessibility.html                  ← accessibility statement
sitemap.xml                         ← submit to Google Search Console
robots.txt                          ← search engine instructions
og-image.jpg                        ← social share preview (1200×630)
favicon.ico / favicon-256.png       ← browser tab icons
apple-touch-icon.png                ← iPhone home screen icon
ms-renovations-pro-logo.png         ← nav + footer logo
ms-renovations-pro-owner-miami.jpg  ← founder portrait (About section)

# PROJECT PHOTOS (all real jobs, SEO-named)
miami-staircase-led-renovation-finished.jpg   ← hero AFTER + gallery feature
popcorn-ceiling-removal-miami-before.jpg      ← hero BEFORE
miami-luxury-lobby-renovation-finished.jpg
miami-commercial-office-renovation-finished.jpg
miami-interior-painting-finished.jpg
miami-renovation-crew-trim-work.jpg
miami-drywall-sanding-finish.jpg
miami-drywall-taping-coffered-ceiling.jpg
miami-commercial-framing-buildout.jpg
miami-ceiling-plaster-crew.jpg
miami-commercial-painting-prep.jpg
miami-hotel-corridor-painting-finished.jpg
miami-highrise-condo-drywall-repair.jpg
miami-staircase-painting-prep.jpg
miami-interior-painting-open-plan.jpg
miami-home-renovation-demo.jpg
miami-drywall-primer-interior.jpg
miami-drywall-prime-bright-room.jpg
miami-commercial-corridor-renovation.jpg
miami-drywall-tile-renovation.jpg
```

---

## Common edits

### Add Google Analytics
In `index.html`, find:
```js
const GA_ID='G-XXXXXXXXXX'
```
Replace with your real Analytics ID. GA only loads after user clicks "Accept" on the cookie banner.

### Replace a photo
1. Prepare your new photo (JPG, max 1600px longest side, <300KB ideally)
2. Name it **exactly** the same as the file it replaces (e.g. `miami-staircase-led-renovation-finished.jpg`)
3. Drop it in this folder, commit, and push — done.

### Add a new gallery photo
1. Add your image file to the root folder with a descriptive SEO name (e.g. `miami-bathroom-tile-remodel.jpg`)
2. In `index.html`, find the `.gallery-grid` section
3. Add a new tile: `<div class="gtile" style="background-image:url('your-image.jpg')" role="img" aria-label="Description"><span>Caption</span></div>`

### Change phone number
Search `index.html` for `754.900.8247` and `7549008247` — update both (display + `tel:` link).

### Change service copy
Find the `<section class="services"` block in `index.html`. Each service is an `<article class="svc">`.

---

## Before launch checklist

- [ ] Replace `G-XXXXXXXXXX` with real Google Analytics ID
- [ ] Confirm `www.msrenovationspro.com` is added as custom domain in Cloudflare Pages project
- [ ] Set up www → apex redirect rule in Cloudflare
- [ ] Submit `sitemap.xml` to Google Search Console
- [ ] Create/claim Google Business Profile (biggest local SEO move)

---

## Structure rules (keep these)
- All files live in **root** — no subfolders. HTML references images by plain filename.
- Each deploy via Cloudflare Pages replaces the entire site — always push all files.
- Privacy/accessibility pages are `noindex` — they won't compete in search results.
