# AGENTS.md

Marketing site for **בחוץ – אדריכלות נוף** (Bahutz Landscape Architecture). Hebrew, RTL, single page.

## Architecture

- TanStack Start + React 19 + Tailwind v4 (`vite.config.ts` wires Tailwind, the Netlify adapter, Start, and React).
- `src/routes/__root.tsx`: the HTML shell (`lang="he" dir="rtl"`), metadata, favicon and Google Fonts links.
- `src/routes/index.tsx` → `src/components/MarketingPage.tsx`: every page section is a local function component (Header, Hero, About, Stats, Process, Approach, Projects, Partners, Philosophy, Contact, Footer).
- `src/components/ContactForm.tsx`: an AJAX Netlify Forms submission, URL-encoded and POSTed to `/__forms.html`.
- `public/__forms.html`: static registration for the `contact` form. **Keep its field names in sync with ContactForm** (`subject, name, organization, email, phone, project-type, message, bot-field`). `src/data/site.test.ts` checks this.
- `src/data/site.ts`: all copy and lists, plus the `img(name, width)` helper that builds Netlify Image CDN URLs.
- `src/styles.css`: brand colour tokens (`sky, stone, clay, leaf, ink, paper`), fonts (headings: self-hosted Kedem Sans in `public/fonts`, whose CC BY 4.0 credit is in the footer and must stay; body: Calibri, falling back to Carlito/Assistant), the `.topo` contour-line background, and the `.action`, `.action-ghost`, `.eyebrow` and `.form-input` classes.
- `public/img/`: logos supplied by the client (`logo-full.png`, `logo-mark.png`, `wordmark.png` for the header, and light versions `logo-full-light.png`, `logo-mark-light.png` for dark backgrounds), brand graphics `shapes-color/ink/light.png` (used as faint decorative accents, `aria-hidden`), and AI-generated illustrative imagery (`hero, park, plaza, playground, studio`), and the founder's photo `dan.jpg` (cropped to the face with CSS in the About section).

## Conventions

- RTL first: use logical utilities (`ms-`, `me-`, `ps-`, `start-`, `text-start`) rather than left/right.
- Reference images in `public/img` through `img()` (Image CDN), not by their raw PNG path. Logos are small and are linked directly.
- There are no project or portfolio claims beyond the client's own text. The `partners` list in `site.ts` holds the client-supplied authorities and organisations with their logos in `public/img/partners`, which were recoloured to a single ink silhouette with ImageMagick so they stay quiet. Recolour any new logo the same way. Don't invent client names, project names, phone numbers or emails. Ask for them. The real phone, email and WhatsApp link live in `site` in `src/data/site.ts`.
- The template's product catalogue and routes were removed on purpose.

## Possible next steps

Real project portfolio pages with photos, an office address, and social links.
