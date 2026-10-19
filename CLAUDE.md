# MindMotion marketing website

Static landing page for MindMotion, an AI preventive health platform for urban India. The company is in stealth and the product is at MVP stage. Readers are startup-program reviewers (Google, AWS, Microsoft) and outreach contacts, so the page must read as credible, informative and early-stage.

## Repo and deploy
- The whole site is one file: `index.html` (inline CSS and JS, logo and wheel image embedded as base64). There is no package.json, build step or vercel.json.
- Hosted on Vercel, connected to GitHub (`RAMindMotion/website`). Production branch: `main`. Other branches and PRs get Vercel preview URLs.
- Lines 193 and 331 of `index.html` hold huge base64 images. Never print them whole; read with `cut -c1-200` or by line range, and never rewrite or re-encode them.

## Stealth mode
- No founder names, bios, photos or team section. Remove nothing the user did not ask about, but never add any of these.
- Early access is reachable only through the nav button ("Early access", `#early-access`) and the bottom section of the page.
- Early access must be connected to contact@mindmotion.in. Check this whenever the form is touched: the form action, where submissions land, and that the address in the footer matches. Report if it is not connected.

## Messaging
- Tagline: "Live healthier, longer."
- Hero label: "Personal Health Agent".
- Positioning: "preventive health intelligence", framed as What / Why / How.

## Brand
- Font: Mulish.
- Palette: Cream #F5F2EA, Pine #17251F, Deep Pine #21443A, Teal #2F7D6E, Sage #9CBBA6, Mist #D9E3DA. Use the CSS variables in `:root`; do not introduce new colours without asking.
- Keep the existing logo. Do not recreate, redraw or re-encode it.

## Footer (must keep)
- MindMotion Healthtech Private Limited
- CIN U62090HR2026PTC143626
- Gurugram
- contact@mindmotion.in
- The medical disclaimer
- No Privacy or Terms links until those pages exist.

## Claims discipline
- Every statistic needs a visible source on the page.
- No absolute claims such as "most NCDs are preventable". Use "strongly linked to daily lifestyle choices".
- Do not state or imply diagnosis, treatment or cure. Product screens are labelled as concepts.

## Mobile-first
- Check every change at 390px width: no horizontal overflow.

## Workflow (every change)
1. Never push to `main`. Branch `claude/<short-description>`, commit, push, open a pull request.
2. Before opening the PR: render the page at 1440px and 390px wide. Check for horizontal overflow (`document.documentElement.scrollWidth <= innerWidth`), broken sections and missing images, and confirm HTML tags are balanced. Do not trust that a string replacement worked: look at the rendered result.
3. PR description: what changed, before/after screenshots where possible, and the Vercel preview URL once available.
4. Make only the changes asked for. List anything else noticed as suggestions instead of changing it.
5. Commits and PRs follow the attribution lines the session provides.

## Known open items (suggestions, not yet approved changes)
- Form action is the placeholder `https://formspree.io/f/YOUR_FORM_ID`; the script shows "Form not connected yet." until replaced.
- `og:image` is missing (TODO comment at line 13); needs a 1200x630 image.
- Analytics is a TODO comment at line 18.
- Unused `.team-grid` / `.avatar` CSS remains from a removed team section.
- Copy at lines 220 and 247 says "largely preventable", which conflicts with the claims rule.
