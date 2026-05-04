# Nordstrom Company — Website

Live at: **https://nordstromcompany.com**

A modern, single-page accounting business website with a blog. Pure HTML + CSS +
a tiny bit of JS for the mobile menu. No build step, no framework.

## Files

- `index.html` — Main site (Hero, Services, About, Testimonials, Contact)
- `blog.html` — Blog listing page
- `posts/year-end-tax-moves.html` — First blog post
- `styles.css` — Shared design system
- `logo.svg` — Brand mark + wordmark (also used as favicon)

## How to deploy a change

The site is hosted on Vercel and connected to the GitHub repo
`NorthstreamLLC/nordbooks-website`. Any commit to the `main` branch
auto-deploys within ~30 seconds.

To push a change without using the terminal:

1. Open the repo on github.com.
2. Click into the file you want to edit, then click the pencil icon (top-right) to edit.
3. Make your changes, scroll down, click **Commit changes**.
4. Wait ~30 seconds — your change is live at nordstromcompany.com.

To upload new files (e.g. a new blog post or a logo):
1. On the repo page, click **Add file** → **Upload files**.
2. Drag in the file(s).
3. Commit.

## Things still to do (placeholders to swap)

A search through the HTML for `[` will find any remaining placeholders. Currently:

- `[Your Phone]` — appears in `index.html`, `blog.html`, and `posts/year-end-tax-moves.html`. Replace with the real phone number, or remove the phone row entirely if you don't want one displayed.
- Testimonials show `[Sample Client]` and `[Sample Business]` — swap these for real client names (with permission) once you have testimonials, or hide the Testimonials section by removing/commenting out the `<section id="testimonials">` block in `index.html`.

## Email

The site links `jill@nordstromcompany.com`. To make that address actually work,
set up email forwarding in GoDaddy:

1. godaddy.com → My Products → find `NordstromCompany.com`.
2. Click **Email & Office** → **Forward Email** (or "Set up forwarding").
3. Forward `jill@nordstromcompany.com` → your real inbox.
4. Test by sending a message from a different email address.

## Wiring up the contact form

The form currently shows a placeholder alert on submit. To make it actually send:

1. Sign up at **formspree.io** (free up to 50 submissions/month).
2. Create a new form, copy the form's endpoint URL (looks like `https://formspree.io/f/xxxxxxx`).
3. In `index.html`, find the `<form class="contact-form" ...>` line.
4. Replace `onsubmit="event.preventDefault(); alert(...);"` with `action="https://formspree.io/f/xxxxxxx" method="POST"`.
5. Commit the change. Test the form.

## Customizing the look

All design tokens live at the top of `styles.css` under `:root` — change colors
once and they apply everywhere. The current palette:

- Background:  cream (`#FAF8F4`)
- Accent:      deep sage green (`#2F6F5E`)
- Text:        dark navy (`#1B2A3A`)
- Gold accent: `#C4A35A` (used on stars)

## Adding more blog posts

1. Copy `posts/year-end-tax-moves.html` → `posts/your-new-slug.html`.
2. Edit the title, meta description, byline, and body content.
3. In `blog.html`, find the post card with `Coming soon` for the topic you're writing,
   change `<a href="#">` to `<a href="posts/your-new-slug.html">`, remove the
   "· Coming soon" suffix, and update the read-more link.
4. Commit. The new post is live.

## Hosting

- **Vercel** (current host) — auto-deploys from GitHub `main` branch.
- **Domain** — `nordstromcompany.com` (registered at GoDaddy, DNS pointing to Vercel).
- **SSL** — auto-provisioned by Vercel (Let's Encrypt). Renewed automatically.
