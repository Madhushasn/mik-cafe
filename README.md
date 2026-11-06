# Mik Café – Customer Service Website

A single-file, framework-free website for **Mik Café**, a family-owned specialty coffee and matcha café at 577 Burnhamthorpe Rd, Etobicoke, ON M9C 2Y3 · (416) 695-9331.

## What's in this folder

| File | Purpose |
| --- | --- |
| `index.html` | The entire site: HTML, CSS and JavaScript in one file. No libraries, fonts or network requests. |
| `images/` | Optimized copies of the four café photos. They are already embedded in `index.html` (as base64), so the site works without this folder; it is kept so you can swap or re-use the photos. |
| `.nojekyll` | Tells GitHub Pages to serve the files as-is. |
| `README.md` | This guide. |

## Publish on GitHub Pages

1. Create a new repository on GitHub (for example `mik-cafe`).
2. Upload `index.html`, `.nojekyll` and `README.md` to the repository root.
3. Go to **Settings → Pages**, set **Source** to *Deploy from a branch*, choose `main` and `/ (root)`, then **Save**.
4. After a minute or two the site is live at `https://<your-username>.github.io/mik-cafe/`.

## Things the café owner should confirm and edit

The site and Help Assistant never invent facts. Where details weren't provided, they say so and send visitors to the phone number. Once you have verified answers, update the text in `index.html`:

- **Wi-Fi, parking, accessibility, seating, dairy alternatives, catering, large groups, refund policy** – currently "please call" answers. Edit the `FAQS` array and the `INTENTS` array in the `<script>` block.
- **Menu items and prices** – these are *sample* items. Edit the `MENU` array in the script. Remove the "Sample menu & pricing" notice when the menu is final.
- **Online ordering link** – set `ORDER_URL` near the top of the script to switch on an "Order online" button.
- **Photos** – the hero and the "Pull up a chair" gallery use four photos supplied by the café. `croissant-latte-cookie.webp` is low resolution (224×298), so replace it with a larger original when you have one. To swap a photo, replace the `src="data:image/webp;base64,…"` value of that `<img>` (or point `src` at a file in `images/`). Add an `og:image` meta tag with the absolute URL of a photo once the site is live so links preview nicely when shared.
- **Testimonials** – the three reviews are labelled placeholders. Replace them with real customer feedback (with permission).
- **Social links** – the three icons are placeholders that show a "coming soon" message. Replace each `href="#"` (search for `data-placeholder`) with the real profile URL and remove the `data-placeholder` attribute.
- **Google Map** – a styled placeholder with an "Open in Google Maps" button. To embed a live map, replace the `<div class="map">` block with a Google Maps embed `<iframe>`.
- **Newsletter** – the form is front-end only. Connect it to your email provider when ready, and update the confirmation text.

## Privacy

The "Report an Order Problem" form, newsletter form and Help Assistant all run entirely in the browser. Nothing is sent to a server or stored. After submitting the order-problem form, visitors are directed to call the café with a summary and reference code.

## Accessibility

Skip link, semantic landmarks, keyboard-operable menu/FAQ/chat, visible focus rings, AA colour contrast, form errors announced to screen readers, 44px+ touch targets, and `prefers-reduced-motion` support.
