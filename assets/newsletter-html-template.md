---
type: asset
id: newsletter-html-template
title: Newsletter HTML Template
description: "Base HTML email template for newsletter editions"
tags: []
connections: []
---

## Purpose

A responsive HTML email template structure for newsletter editions. This defines the layout sections that the newsletter writer prompt should target.

## Template Structure

### Header Section

```html
<!-- Logo and edition number -->
<header>
  <img src="[logo-url]" alt="[Newsletter Name]" />
  <p>Edition #[number] — [date]</p>
</header>
```

### Main Feature Section

```html
<!-- Primary article -->
<section class="feature">
  <h1>[Feature Title]</h1>
  <p>[Feature content — 300-500 words]</p>
</section>
```

### Quick Reads Section

```html
<!-- 2-3 shorter items -->
<section class="quick-reads">
  <h2>Quick Reads</h2>
  <article>
    <h3>[Item Title]</h3>
    <p>[50-100 words]</p>
  </article>
  <!-- Repeat for each item -->
</section>
```

### Curated Links Section

```html
<!-- 3-5 recommended resources -->
<section class="curated">
  <h2>Worth Reading</h2>
  <ul>
    <li><a href="[url]">[Title]</a> — [One-sentence description]</li>
    <!-- Repeat for each link -->
  </ul>
</section>
```

### Footer Section

```html
<!-- Sign-off, unsubscribe, social links -->
<footer>
  <p>[Personal sign-off]</p>
  <p><a href="[unsubscribe-url]">Unsubscribe</a> | <a href="[preferences-url]">Update preferences</a></p>
</footer>
```

## Design Notes

- Maximum width: 600px (email client standard)
- Use inline CSS for email client compatibility
- Test across: Gmail, Outlook, Apple Mail, Yahoo Mail
- Dark mode: ensure sufficient contrast with both light and dark backgrounds
- Images: always include alt text; do not rely on images for critical information
