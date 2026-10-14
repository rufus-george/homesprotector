# Homes Protector

Landing page for **Homes Protector – Home Improvement & Remodeling**. Visitors can request a free estimate for roofing, windows and doors, siding, kitchen and bathroom remodeling, flooring and HVAC.

Built as a simple static site (plain HTML and CSS, no build step) and hosted on GitHub Pages.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | Main landing page: hero with estimate form, services, about, process, FAQ and footer |
| `thanks.html` | Thank-you page shown after the estimate form is submitted |
| `logo-mark.png` | Shield logo used in the header, footer and browser tab icon |
| `README.md` | This file |

All files must stay in the same folder (the repository root) so the logo and the redirect to `thanks.html` work.

## Deploy on GitHub Pages

1. Upload all files to the repository root.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, set the source to **Deploy from a branch**, choose `main` and `/ (root)`, then save.
4. After a minute or two the site is live at `https://<username>.github.io/<repository>/`.

## Contact form

The estimate form posts to a [Formsubmit](https://formsubmit.app) endpoint. Each submission is emailed with the subject *New Home Improvement Lead - Homes Protector*, then the visitor is redirected to `thanks.html`.

- Submit a test request after publishing to confirm that leads arrive.
- If you change the form endpoint, edit the `action` of the `<form>` in `index.html`.
- Fields collected: name, phone, email, service, ZIP code, timeline, project details and contact consent.

## Customize

**Colors** — edit the variables at the top of the `<style>` block in `index.html` and `thanks.html`:

```css
--navy: #1a4a80;       /* logo blue */
--navy-deep: #0f2f55;  /* dark blue for headings and footer */
--orange: #f39c1e;     /* logo orange */
--ice: #eef4fa;        /* light background */
```

**Fonts** — headings use Montserrat and body text uses Source Sans 3, loaded from Google Fonts. Change them in the Google Fonts `<link>` and in the `--head` and `--body` variables.

**Services** — each service is an `<article class="service">` block in `index.html`. To add one, copy a block and also add a matching `<option>` to the "Select a Service" dropdown. The `data-service` value on the link must match that option's text exactly.

**Hero photo and About photo** — the About section photo is set in the `.s-photo` CSS rule. Replace the image URL with your own photo if you prefer.

## Before you go live

- Add a privacy policy and terms page, and link them in the footer. The form collects personal contact information.
- Add your business phone number and service areas once confirmed.
- Check the FAQ and footer text so they reflect how your business actually works.

## License

© Homes Protector. All rights reserved.
