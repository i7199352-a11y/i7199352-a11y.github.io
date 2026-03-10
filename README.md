# ✦ Celestial Horoscope — GitHub Pages Site

A complete, SEO-optimized static astrology blog ready to deploy on GitHub Pages.

---

## 📁 Folder Structure

```
/
├── index.html              ← Homepage
├── about.html              ← About page
├── contact.html            ← Contact page
├── privacy.html            ← Privacy Policy
├── sitemap.xml             ← XML sitemap (update daily!)
├── robots.txt              ← Search engine directives
├── .nojekyll               ← Disables Jekyll on GitHub Pages
├── css/
│   └── style.css           ← All styles
├── today/
│   └── index.html          ← "Today's Horoscope" landing page
├── posts/
│   ├── 2026-03-07.html     ← Full 12-sign post (use as template)
│   ├── 2026-03-08.html
│   └── 2026-03-09.html
└── zodiac/
    ├── aries.html
    ├── taurus.html
    ... (all 12 signs)
    └── pisces.html
```

---

## 🚀 Deploying to GitHub Pages

1. Create a new GitHub repository (e.g. `celestial-horoscope` or `yourusername.github.io`)
2. Upload all files maintaining the folder structure above
3. Go to **Settings → Pages** → Set source to **main branch / root**
4. Your site will be live at `https://yourusername.github.io/` within minutes

**Important:** Replace all instances of `yourusername.github.io` with your actual GitHub Pages URL throughout all HTML files.

---

## 📝 How to Add a New Daily Post

### Step 1: Copy the template
Copy `posts/2026-03-07.html` and rename it with today's date:
```
posts/YYYY-MM-DD.html
e.g. posts/2026-03-10.html
```

### Step 2: Update the meta tags
At the top of your new file, update:
- `<title>` — e.g. `Daily Horoscope March 10, 2026 — [Planetary Event]`
- `<meta name="description">` — 150-160 character summary with today's key astrology
- `<link rel="canonical">` — Update to the new post URL
- `<meta property="og:url">` — Same as canonical
- `<meta property="article:published_time">` — Today's date

### Step 3: Update the hero section
```html
<p class="post-date">Tuesday, March 10, 2026 · [Planetary Event]</p>
<h1>Daily Horoscope — March 10, 2026</h1>
<p class="post-intro">Your cosmic overview paragraph...</p>
```

### Step 4: Write each sign's forecast
For each of the 12 sign sections, update:
- The star ratings in `.forecast-meta`
- The 2-3 paragraph reading
- Lucky number, color, and affirmation

Each sign section has an `id` matching the sign slug (e.g. `id="aries"`) — this enables deep-linking from the Today page.

### Step 5: Update the "Recent Posts" sidebar
```html
<li><a href="2026-03-10.html">🌟 March 10 — [Event]</a></li>
<li><a href="2026-03-09.html">🌕 March 9 — Full Moon in Virgo</a></li>
<li><a href="2026-03-08.html">☿ March 8 — Mercury Sextile Saturn</a></li>
```

### Step 6: Update `today/index.html`
Change the date references and banner link to point to your new post:
```html
<p class="post-date">Tuesday, March 10, 2026 · [Planetary Event]</p>
<h2>🌟 Today's Horoscope — March 10, 2026</h2>
<a href="../posts/2026-03-10.html" class="btn btn-primary">Read Full Article →</a>
```

Also update the star ratings in the zodiac grid quick-snapshot section.

### Step 7: Update `index.html` (Homepage)
Add your new article as the first card in the "Latest Horoscopes" section, and push the oldest one out.

### Step 8: Update `sitemap.xml`
Add a new `<url>` entry:
```xml
<url>
  <loc>https://yourusername.github.io/posts/2026-03-10.html</loc>
  <lastmod>2026-03-10</lastmod>
  <priority>0.9</priority>
</url>
```

### Step 9: Commit and push to GitHub
```bash
git add .
git commit -m "Add horoscope for March 10, 2026"
git push
```

GitHub Pages will update within 1-2 minutes.

---

## 💰 Adding Google AdSense

1. Sign up at [adsense.google.com](https://adsense.google.com) and get approved
2. In each HTML file, replace the ad slot comments with your actual AdSense code:

```html
<!-- BEFORE (placeholder) -->
<div class="ad-slot ad-slot-leaderboard" aria-label="Advertisement">
  <!-- Google AdSense: Replace with your ad unit code -->
</div>

<!-- AFTER (live AdSense) -->
<div class="ad-slot ad-slot-leaderboard" aria-label="Advertisement">
  <ins class="adsbygoogle"
       style="display:block"
       data-ad-client="ca-pub-YOUR_PUBLISHER_ID"
       data-ad-slot="YOUR_AD_SLOT_ID"
       data-ad-format="auto"
       data-full-width-responsive="true"></ins>
  <script>(adsbygoogle = window.adsbygoogle || []).push({});</script>
</div>
```

3. Add the AdSense auto-ads script to the `<head>` of every page:
```html
<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-YOUR_PUBLISHER_ID" crossorigin="anonymous"></script>
```

**Ad slot locations in each post page:**
- `ad-slot-leaderboard` — Top of post (728×90 or responsive)
- `ad-slot-rectangle` — Mid-post (300×250)
- `ad-slot-rectangle` in sidebar — (300×250)
- `ad-slot-leaderboard` — Bottom of post
- `ad-slot-banner` — Footer area (728×90 or responsive)

---

## 🔍 SEO Checklist

### Per new post, always include:
- [ ] Unique `<title>` with date and planetary event (50–60 chars)
- [ ] Unique `<meta description>` (140–160 chars)
- [ ] `<link rel="canonical">` matching exact URL
- [ ] `<meta property="article:published_time">` with ISO date
- [ ] Open Graph `og:title`, `og:description`, `og:url`
- [ ] JSON-LD Article schema with `datePublished`
- [ ] Correct `<h1>` (one per page)
- [ ] Internal links to zodiac pages and previous posts
- [ ] Updated sitemap.xml entry

### Google Search Console
1. Verify your GitHub Pages domain at [search.google.com/search-console](https://search.google.com/search-console)
2. Submit your sitemap URL: `https://yourusername.github.io/sitemap.xml`
3. Use URL Inspection tool after publishing each new post to request indexing

### Google Discover Tips
- Use compelling, emoji-enhanced titles (e.g. "🌕 Full Moon in Virgo — Your Complete Forecast")
- Publish at a consistent daily time (Google rewards freshness)
- Add a real featured image (1200×630px) to each post and reference it in `og:image`
- Ensure pages load fast — this site is already lightweight

---

## 📸 Adding Featured Images (Recommended)

Create an `/images/` folder and add:
- `og-home.jpg` — 1200×630px homepage Open Graph image
- `og-YYYY-MM-DD.jpg` — per-post Open Graph image

Then update each post's og:image meta tag:
```html
<meta property="og:image" content="https://yourusername.github.io/images/og-2026-03-10.jpg">
```

Free image tools: Canva, Adobe Express, or generate with AI image tools.

---

## 📧 Setting Up the Contact Form

The contact form uses [Formspree](https://formspree.io) by default (free tier available):
1. Sign up at formspree.io
2. Create a new form and copy your form ID
3. In `contact.html`, replace `YOUR_FORM_ID`:
   ```html
   <form action="https://formspree.io/f/YOUR_ACTUAL_FORM_ID" method="POST">
   ```

Alternative: Use Netlify Forms if you migrate hosting to Netlify.

---

## 🌐 Custom Domain (Optional)

To use a custom domain (e.g. `celestialhoroscope.com`):
1. Buy a domain from Namecheap, Google Domains, etc.
2. In GitHub Pages settings, enter your custom domain
3. Update your domain's DNS to point to GitHub Pages IPs
4. Replace all `yourusername.github.io` URLs with your custom domain
5. GitHub will auto-provision an HTTPS certificate

---

*Built with pure HTML, CSS, and minimal JavaScript. No frameworks, no dependencies, no build tools required.*
