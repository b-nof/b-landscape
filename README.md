# בחוץ – אדריכלות נוף

The website of **Bahutz Landscape Architecture** (בחוץ – אדריכלות נוף), a studio led by Dan Ilouz that designs public open spaces for developers, public bodies and local authorities.

It is a Hebrew, right-to-left, single-page site with these sections:

- **Hero**: the studio's positioning and who it works for
- **The studio (המשרד)**: the office and its founder
- **Planning process (תהליך התכנון)**: an interactive six-step walkthrough, from the first idea to site supervision
- **Our approach (הגישה שלנו)**: the studio's values, including topography as a design tool
- **Project types (פרויקטים)**: expanding cards covering scales from a single playground to whole neighbourhoods
- **Contact (צרו קשר)**: a contact form handled by Netlify Forms

## Tech

- [TanStack Start](https://tanstack.com/start) + React 19, Tailwind CSS v4
- Netlify Forms for contact submissions, with no backend code
- Netlify Image CDN for responsive WebP images
- Brand palette taken from the studio's identity: sky `#a2bac7`, stone `#e2e2d9`, clay `#ba7653`, leaf `#739771`, ink `#433f3a`
- Fonts: Frank Ruhl Libre (display) and Assistant (body), loaded from Google Fonts

## Running locally

```bash
pnpm install
netlify dev        # or: pnpm dev
pnpm test
```

Form submissions are only processed on a deployed Netlify site. Local previews show an error state on submit.

## Editing content

All copy is in `src/data/site.ts`: the process steps, values, project types and contact-form options. Images are in `public/img/`.

The project photos are illustrative, AI-generated imagery. Swap in photos of real projects when they're available.
