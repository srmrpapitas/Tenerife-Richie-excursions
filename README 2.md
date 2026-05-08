# Tenerife Richie Excursions

Single-page tourism website built as **one self-contained `index.html` file** — no build step, no dependencies. Drop it on GitHub Pages or Cloudflare Pages and you're live.

---

## 📁 What's inside

- `index.html` — the entire site (HTML + CSS + JS in one file)

That's it. No npm, no webpack, no framework.

---

## 🚀 Deploy to GitHub Pages

1. Create a new repo on GitHub (e.g. `tenerife-richie`)
2. Upload `index.html` to the root of the repo
3. Go to **Settings → Pages**
4. Under "Build and deployment" → Source, choose **Deploy from a branch**
5. Pick branch `main` and folder `/ (root)` → **Save**
6. Wait ~1 minute. Your site is live at `https://YOUR-USERNAME.github.io/tenerife-richie/`

---

## ☁️ Deploy to Cloudflare Pages

1. Log in to [Cloudflare dashboard](https://dash.cloudflare.com) → **Workers & Pages** → **Create → Pages**
2. **Connect to Git** → pick your GitHub repo
3. Build settings:
   - Framework preset: **None**
   - Build command: *(leave empty)*
   - Build output directory: `/`
4. Click **Save and Deploy**
5. Add your custom domain in **Custom domains** tab if you have one

---

## ✏️ How to edit content

Open `index.html` in any text editor. Search for what you want to change — everything is plain HTML.

### Change the WhatsApp number
Search for `447861305822` and replace with your new number (no `+`, no spaces).
There are several occurrences — use Find & Replace All.

### Change excursion prices
Each excursion card looks like this:
```html
<article class="ex-card" data-cat="sea" data-name="Maxicat Catamaran" data-price="59">
  ...
  <span class="ex-price">€59<small>/adult</small></span>
```
Update both the `data-price` attribute (used by the booking modal) **and** the visible `€59` price.

### Add or replace videos
The site uses placeholder videos from `cdn.coverr.co` (free stock). To replace:
```html
<video autoplay muted loop playsinline>
  <source src="YOUR_VIDEO_URL.mp4" type="video/mp4">
</video>
```
Best practice: upload your own MP4 files to a folder `/videos/` in the repo and reference them as `<source src="videos/jetski.mp4" type="video/mp4">`. Keep them under 5 MB each for fast loading.

### Add or replace images
Same idea — replace the `src="..."` URL inside `<img>` tags. Upload images to a `/images/` folder.

### Add a new excursion
Copy any existing `<article class="ex-card">...</article>` block inside the `<div class="ex-grid">` and edit the title, price, image and description.

### Update Google reviews
Replace the placeholder text inside each `<div class="review-card">` with real reviews when you have them. The `4.9` and `1,200+ reviews` numbers are inside the `.reviews-rating` block near the top of the reviews section.

---

## 📱 Booking flow

When a user clicks **Book now** on any excursion:
1. A booking modal opens with the excursion title and price
2. They pick a date, set adults/children/babies, optionally enter pickup hotel
3. Clicking **Reserve on WhatsApp** opens WhatsApp with a pre-filled message containing all booking details
4. You receive the message and confirm availability

Pricing logic in the modal:
- Adults: full price
- Children: 50% of adult price
- Babies: free

Adjust this inside the `updateTotal()` function in the script section if needed.

---

## 🎨 Brand colours

Edit the `:root` CSS variables at the top of `index.html` to change the palette globally:
```css
--aqua-500: #06b6d4;
--orange-500: #ff7a18;
--ink: #0b1f2a;
```

---

## ✅ Checklist before going live

- [ ] Replace placeholder videos with real footage of your excursions
- [ ] Replace placeholder Unsplash images with photos from your tours
- [ ] Update real Google reviews (text + author names)
- [ ] Confirm the WhatsApp number `+44 7861 305822` is correct everywhere
- [ ] Add Instagram / TikTok / Facebook real links in the footer
- [ ] Add a favicon (drop a `favicon.ico` in the root and add `<link rel="icon" href="favicon.ico">` inside `<head>`)
- [ ] Test the booking flow on mobile

---

Made with ☀️ for Tenerife.
