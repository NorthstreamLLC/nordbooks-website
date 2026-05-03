# Accounting Website — Starter

A modern, single-page accounting business website with a separate blog page.
Pure HTML + CSS + a tiny bit of JS for the mobile menu — no build step, no framework.

## Files

- `index.html` — Main single-page site (Hero, Services, About, Testimonials, Contact)
- `blog.html` — Blog listing page
- `styles.css` — Shared design system used by both pages
- `README.md` — This file 

## Preview locally

Just double-click `index.html` to open it in your browser.

If you want a proper local server (recommended for testing the contact form
and clean URLs), from this folder run one of:

```
# Python (built into macOS / most Linux)
python3 -m http.server 8000

# Node (if you have it)
npx serve .
```

Then open http://localhost:8000

## Things to customize (find-and-replace)

These placeholders appear throughout the HTML — do a project-wide find-and-replace:

| Placeholder              | Replace with                                  |
| ------------------------ | --------------------------------------------- |
| `[Business Name]`        | The actual business name                      |
| `[Your Name]`            | Owner's full name                             |
| `[YN]`                   | Owner's initials (used in the about portrait) |
| `[CPA / EA]`             | Actual credential (CPA, EA, or remove)        |
| `[XX]`                   | Years of experience                           |
| `[Your State]`           | Licensing state                               |
| `[Professional Org]`     | e.g. AICPA, NATP, state society               |
| `(555) 123-4567`         | Real phone number                             |
| `hello@[business-name].com` | Real email                                |
| `[123 Main Street, Suite 100]` | Real street address                     |
| `[City, ST 00000]`       | Real city / state / zip                       |
| `[Sample Client]`        | Real client name (with permission)            |
| `[Sample Business]`      | Real client business                          |

The brand mark is a single letter "B" in the top-left — change it in both
`index.html` and `blog.html` (search for `class="brand-mark">B<`) and the
`B` after the mark to the business initials.

## Customizing the look

All design tokens live at the top of `styles.css` under `:root` — change
the colors there once and they apply everywhere. The current palette:

- Background:    cream (`#FAF8F4`)
- Accent:        deep sage green (`#2F6F5E`)
- Text:          dark navy (`#1B2A3A`)
- Gold accent:   `#C4A35A` (used on stars)

Fonts come from Google Fonts (Inter + Source Serif 4). If you want to use
local fonts or a different family, swap the `<link>` tag and update the
`--font-sans` / `--font-serif` variables.

## Replacing the hero visual

The hero currently shows a decorative stat-card mockup. To use a real
photo or illustration, find this block in `index.html`:

```html
<div class="hero-visual" aria-hidden="true">
  ...
</div>
```

Replace its contents with `<img src="hero.jpg" alt="..." style="width:100%;height:100%;object-fit:cover" />`.

## Wiring up the contact form

The form currently shows a placeholder alert on submit. Easiest options:

1. **Formspree** (free tier) — sign up at formspree.io, paste the form
   endpoint into the `<form action="...">` attribute, and remove the
   `onsubmit="..."` attribute.
2. **Netlify Forms** — if you host on Netlify, add `netlify` as an
   attribute on the form and remove the `onsubmit`.
3. **Custom backend** — point the form at your own API endpoint.

## Hosting

Any static host works:
- **Netlify** or **Vercel** — drag-and-drop the folder; free SSL + custom domain
- **GitHub Pages** — commit the folder to a repo and enable Pages
- **Cloudflare Pages** — same flavor as Netlify
- A regular cPanel host — upload via FTP

## Adding real blog posts

`blog.html` lists 6 sample posts that all link to `#`. To turn one into a
real post, create e.g. `posts/year-end-tax-moves.html` (you can copy
`blog.html` as a starting template) and update the `<a href="#">` links
in `blog.html` to point at it.
