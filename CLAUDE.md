# CLAUDE.md

This file provides guidance to Claude Code when working with knockout4acure.

## Project Overview

Static website for "Knockout 4 A Cure" - likely a charity boxing event or fundraiser for cancer research/awareness.

**Type**: Static HTML Website
**Deployment**: GitHub Pages or static web hosting

## Technology Stack

- **Frontend**: HTML5 + CSS (vanilla JavaScript if any)
- **Assets**: PNG image (1.6 MB logo/banner)
- **Favicon**: Custom favicon.ico (15 KB)
- **Hosting**: Static file hosting (GitHub Pages, Netlify, Azure Static Web Apps)

## Project Structure

```
knockout4acure/
├── index.html                   # Main homepage
├── purpose.html                 # Purpose/about page
├── knockout4acure.png           # Logo/banner image (1.6 MB)
├── favicon.ico                  # Site favicon
└── README.md                    # Empty documentation
```

## Features

Based on the structure:
- **Homepage**: Main landing page (index.html)
- **Purpose Page**: Explains the event/fundraiser mission
- **Branding**: Custom logo and favicon
- **Simple Design**: Minimal, static site

## Common Development Tasks

### Local Development

```bash
# Serve locally with Python
python3 -m http.server 8000

# Or with Node.js http-server
npx http-server -p 8000

# Open in browser
open http://localhost:8000
```

### Deployment

#### GitHub Pages

```bash
# Push to GitHub
git add .
git commit -m "Update website"
git push origin main

# Enable GitHub Pages in repository settings
# Settings → Pages → Source: main branch → Save
```

#### Netlify

```bash
# Deploy with Netlify CLI
npm install -g netlify-cli
netlify deploy --prod
```

#### Azure Static Web Apps

```bash
# Deploy with Azure CLI
az staticwebapp create \
  --name knockout4acure \
  --resource-group websites \
  --source https://github.com/jbmurphy/knockout4acure \
  --location eastus2 \
  --branch main
```

### Image Optimization

The PNG file is quite large (1.6 MB). Optimize it:

```bash
# Install ImageMagick or use online tools
convert knockout4acure.png -resize 50% knockout4acure_optimized.png

# Or with pngquant
pngquant --quality=65-80 knockout4acure.png
```

## Typical Website Structure

### index.html

Likely contains:
- Event name and logo
- Date and location
- Registration/donation buttons
- Sponsor logos
- Event details

### purpose.html

Likely contains:
- Mission statement
- Cancer awareness information
- How donations are used
- Impact statistics
- Contact information

## Enhancement Opportunities

### Add Features

1. **Registration Form**: Integrate with Google Forms or Typeform
2. **Donation Integration**: Add PayPal, Stripe, or GoFundMe
3. **Event Photos**: Gallery from past events
4. **Sponsor Section**: Display sponsor logos
5. **Social Media Integration**: Links to social profiles
6. **Analytics**: Google Analytics or similar

### Improve Performance

1. **Image Optimization**: Compress knockout4acure.png
2. **CDN**: Use Cloudflare or similar CDN
3. **Minification**: Minify HTML/CSS/JS
4. **Lazy Loading**: Lazy load images

### SEO Optimization

```html
<!-- Add meta tags -->
<meta name="description" content="Knockout 4 A Cure - Boxing fundraiser for cancer research">
<meta name="keywords" content="boxing, charity, cancer, fundraiser">
<meta property="og:image" content="knockout4acure.png">
<meta property="og:title" content="Knockout 4 A Cure">
```

## Deployment Checklist

- [ ] Optimize images (reduce knockout4acure.png size)
- [ ] Add meta tags for SEO
- [ ] Test on mobile devices
- [ ] Add social media sharing buttons
- [ ] Set up analytics
- [ ] Test all links
- [ ] Add SSL certificate (if not using GitHub Pages/Netlify)
- [ ] Add sitemap.xml
- [ ] Submit to search engines

## Security Considerations

For static sites:
- **HTTPS**: Always use SSL/TLS
- **No Secrets**: Don't commit API keys (if adding forms/payments)
- **CSP Headers**: Add Content Security Policy
- **Input Validation**: If adding forms, validate on backend

## Monitoring

### Analytics

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

### Uptime Monitoring

Use services like:
- UptimeRobot
- Pingdom
- StatusCake

## Related Projects

This could be integrated with:
- **financialdata.net**: If tracking donations
- **stock-prices**: If investments are part of fundraising

## Important Notes

- **Charity Event**: Likely an annual boxing fundraiser
- **Static Site**: No server-side code, just HTML/CSS
- **Image Size**: Main PNG is 1.6 MB - should be optimized
- **Simple Structure**: Only 2 HTML pages currently
- **No Framework**: Vanilla HTML, no React/Vue/etc.
