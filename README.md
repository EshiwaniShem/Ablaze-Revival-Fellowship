# Ablaze Revival Fellowship — Website Documentation

## Project Overview

A complete, production-ready ministry website for Ablaze Revival Fellowship (ARF), built with modern HTML5, CSS3, and vanilla JavaScript. Designed for immediate launch and long-term use.

---

## File Structure

```
ablaze-revival-fellowship/
├── index.html          ← Main website (all pages in one file)
├── README.md           ← This documentation
└── assets/             ← (Create this folder for your images/media)
    ├── images/
    ├── audio/
    └── video/
```

---

##  Quick Deployment Options

### Option 1: Netlify (Recommended — Free)
1. Go to [netlify.com](https://netlify.com) and create a free account
2. Click **"Add new site" → "Deploy manually"**
3. Drag and drop your `index.html` file (or the entire project folder)
4. Your site is live! You'll get a URL like `https://ablaze-revival.netlify.app`
5. Connect your custom domain (e.g. `ablazerevival.org`) in Site Settings

### Option 2: Vercel (Free)
1. Go to [vercel.com](https://vercel.com) and sign up
2. Click **"Add New Project"**
3. Upload or connect your GitHub repository
4. Vercel auto-deploys — done!

### Option 3: GitHub Pages (Free)
1. Create a GitHub account and a new repository named `ablaze-revival-fellowship`
2. Upload `index.html` to the repo
3. Go to Settings → Pages → Source: main branch
4. Your site is live at `https://yourusername.github.io/ablaze-revival-fellowship`

### Option 4: Shared Hosting (Hostinger, cPanel, Bluehost etc.)
1. Purchase hosting + domain (Hostinger Kenya is affordable)
2. Upload `index.html` via File Manager or FTP
3. Point your domain to the hosting server

---

## Customisation Guide

### 1. Ministry Information
Open `index.html` and find/replace:
- `info@ablazerevival.org` → your real email
- `+254 700 000 000` → your real phone number
- `ARF0001` → your real M-Pesa account number
- `247247` → your real Paybill number
- `0110XXXXXXXXX` → your real bank account number

### 2. Images
Replace the placeholder blocks with real images:
```html
<!-- Find this div: -->
<div class="welcome-img-main">
  <div class="img-placeholder-text">...</div>
</div>

<!-- Replace with: -->
<div class="welcome-img-main">
  <img src="assets/images/fellowship-photo.jpg" 
       style="width:100%;height:100%;object-fit:cover;border-radius:8px" 
       alt="Ablaze Revival Fellowship">
</div>
```

### 3. Colors
Find `:root` in the CSS and adjust:
```css
:root {
  --gold: #C9922A;        /* Primary gold accent */
  --fire: #D44D12;        /* Fire/orange accent */
  --navy: #0D1B2A;        /* Deep navy background */
}
```

### 4. Social Media Links
Search for `href="#"` in the footer/social sections and replace with your actual links:
```html
<a href="https://facebook.com/ablazerevivalfellowship">
<a href="https://youtube.com/@ablazerevival">
<a href="https://instagram.com/ablazerevival">
<a href="https://wa.me/254700000000">
```

### 5. WhatsApp Button
Find the `.whatsapp-float` link:
```html
<a href="https://wa.me/254700000000" class="whatsapp-float">
```
Replace `254700000000` with your real WhatsApp number (254 + number without 0).

---

## Adding Real Sermons (YouTube)

To embed a YouTube sermon, add this in the sermon section:
```html
<div class="sermon-thumb" style="height:auto;padding-bottom:56.25%;position:relative;">
  <iframe style="position:absolute;inset:0;width:100%;height:100%"
    src="https://www.youtube.com/embed/YOUR_VIDEO_ID"
    frameborder="0" allowfullscreen>
  </iframe>
</div>
```
Replace `YOUR_VIDEO_ID` with the ID from your YouTube URL.

---

## Adding Google Maps

Find the map placeholder at the bottom of the Contact page:
```html
<div style="width:100%;height:300px;background:var(--navy)...">
```
Replace with a real Google Maps embed:
1. Go to [maps.google.com](https://maps.google.com)
2. Search for your location
3. Click Share → Embed a map → Copy HTML
4. Paste the `<iframe>` code in place of the placeholder div

---

## Contact Form Integration

The forms currently show toast notifications. To make them send real emails, use one of:

### Formspree (Free, easy)
1. Go to [formspree.io](https://formspree.io) and create an account
2. Create a new form and get your form ID
3. Update the form submit button:
```javascript
// Replace showToast() in the form button onclick with:
submitForm('https://formspree.io/f/YOUR_FORM_ID', formData)
```

### EmailJS (Free tier)
1. Go to [emailjs.com](https://emailjs.com)
2. Connect your Gmail or other email service
3. Use the EmailJS SDK in your HTML

---

## CMS / Content Management

For easy content updates without coding, integrate one of these headless CMS options:

### Option A: Sanity CMS (Recommended)
1. Install: `npm create sanity@latest`
2. Configure schemas for: sermons, events, blog posts, testimonials
3. Fetch content via Sanity's API and render dynamically

### Option B: Contentful
1. Sign up at [contentful.com](https://contentful.com) (free tier)
2. Create content types: Sermon, Event, BlogPost, Testimony
3. Fetch via REST API or GraphQL

### Option C: Simple JSON Files
For simpler setups, create JSON data files:
```json
// sermons.json
[
  {
    "title": "The Fire That Never Goes Out",
    "speaker": "Lead Minister",
    "date": "2025-05-15",
    "scripture": "Leviticus 6:13",
    "youtubeId": "VIDEO_ID"
  }
]
```
Then fetch and render with JavaScript.

---

## SEO Setup

The website includes basic meta tags. For full SEO:

1. **Update meta description** in `<head>`:
```html
<meta name="description" content="Ablaze Revival Fellowship — A Christ-centered revival fellowship in Kenya focused on prayer, worship and discipleship.">
```

2. **Add Google Analytics**:
```html
<!-- In <head> tag -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

3. **Create sitemap.xml** and submit to Google Search Console

4. **Register on Google My Business** for local search visibility

---

## Progressive Web App (Optional)

To make the site installable on phones:
1. Create `manifest.json` with your app details
2. Add a service worker for offline support
3. Add `<link rel="manifest" href="manifest.json">` in `<head>`

---

## Domain & SSL

1. Purchase domain at [Namecheap](https://namecheap.com) or [Kenya Domains](https://kenic.or.ke)
2. Recommended: `ablazerevival.org` or `ablazerevivalfellowship.org`
3. SSL is free and auto-configured on Netlify, Vercel, and GitHub Pages

---

## Support & Next Steps

### Immediate Action Items:
- [ ] Replace placeholder contact info with real details
- [ ] Add real photos to image placeholders
- [ ] Set up real M-Pesa Paybill number
- [ ] Connect social media links
- [ ] Set up email for contact form (Formspree)
- [ ] Deploy to Netlify/Vercel
- [ ] Connect custom domain
- [ ] Submit to Google Search Console
- [ ] Register on Google My Business

### Phase 2 Enhancements:
- [ ] Integrate YouTube API for auto-loading latest sermons
- [ ] Add Sanity CMS for easy content updates
- [ ] Add live stream integration (YouTube/Facebook Live embed)
- [ ] Set up Google Calendar integration
- [ ] Add podcast player (Spotify/Apple Podcasts embed)
- [ ] Build member portal / login system

---

*Built with love for Ablaze Revival Fellowship — Ignite. Revive. Transform.*
