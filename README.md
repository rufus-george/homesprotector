# Homes Protector

Landing page for **Homes Protector – Home Improvement & Remodeling**. Visitors can request a free estimate for roofing, windows and doors, siding, kitchen and bathroom remodeling, flooring and HVAC.

Built as a simple static site (plain HTML and CSS, no build step) and hosted on GitHub Pages.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | Main landing page: ZIP code hero, service cards, pop-up estimate forms, about, process, FAQ and footer |
| `thanks.html` | Thank-you page shown after any estimate form is submitted |
| `privacy.html` | Privacy policy page, linked from the footer and the estimate form |
| `logo-mark.png` | Shield logo used in the header, footer and browser tab icon |
| `README.md` | This file |

All files must stay in the same folder (the repository root) so the logo and the redirect to `thanks.html` work.

## Deploy on GitHub Pages

1. Upload all files to the repository root.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, set the source to **Deploy from a branch**, choose `main` and `/ (root)`, then save.
4. After a minute or two the site is live at `https://<username>.github.io/<repository>/`.

## How the forms work

The home page has no long form on the page itself. Instead:

1. Visitors enter their **ZIP code** in the hero (or the bottom banner) and click **Get my free estimate**. A pop-up opens with the *Get a Free Estimate* form and the ZIP code already filled in.
2. Each service card (**Roofing, Windows & Doors, Siding, Kitchen Remodeling, Bathroom Remodeling, Flooring, HVAC, Multiple Projects**) opens the same pop-up with questions specific to that service.
3. When the form is submitted, the visitor lands on `thanks.html`.

Every form sends to the same endpoint: `https://formspree.io/f/xoejpjen`. Each lead email has a subject such as *New Roofing Lead - Homes Protector* and a `form_source` field that shows where it came from (hero ZIP box, bottom ZIP box or a service card).

All leads include: service, name, phone, email, ZIP code, timeline, home ownership, project details and contact consent, plus the service-specific answers (for example roofing material, number of windows, kitchen budget or HVAC system type).

Submit a test request for at least one service after publishing to confirm the leads arrive and the thank-you page opens.

## Customize

**Colors** — edit the variables at the top of the `<style>` block in each HTML file:

```css
--navy: #1a4a80;       /* logo blue */
--navy-deep: #0f2f55;  /* dark blue for headings and footer */
--orange: #f39c1e;     /* logo orange */
--ice: #eef4fa;        /* light background */
```

**Fonts** — headings use Montserrat and body text uses Source Sans 3, loaded from Google Fonts. Change them in the Google Fonts `<link>` and in the `--head` and `--body` variables.

**Service questions** — open `index.html` and find the `SERVICES` object near the bottom of the file. Each service lists its questions as `SELECT(...)` (drop-down), `RADIO(...)` (one choice) or `CHECK(...)` (several choices). Edit the option lists, add a question, or remove one. The last argument `true` makes a question required.

**Adding a new service** — add a card in the services grid with a `data-service` value, add the same name as an `<option>` in the pop-up's "Select a Service" list, and add an entry with that exact name in `SERVICES`.

**Photos** — the hero shield photo is the `.s-photo` rule and the About photo is the `.about-image` rule. Replace the image URLs with your own.

## Before you go live

- Review `privacy.html` and make sure it matches how you actually handle leads (who receives them, how long you keep them). Add a contact email there if you want one, and consider a terms page too.
- Add your business phone number and service areas once confirmed.
- Check the FAQ and footer text so they reflect how your business actually works.

## License

© Homes Protector. All rights reserved.
