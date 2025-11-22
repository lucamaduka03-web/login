# Portfolio — Tochukwu (ChukS)

Simple static portfolio site and demos. This README describes the files in this folder, how to run the site and individual project demos, and quick notes about editing/deploy.

## Quick start

- Open the site locally: open `index.html` in your browser or serve the folder.
- Serve via Node (recommended): from the portfolio folder run:
  - npx http-server . -p 8080 -c-1
  - Open http://localhost:8080
- Or Python: `python -m http.server 8080`
- Or use the VS Code Live Server extension.

## Structure (important files)

- index.html — Home / landing page.
- style.css — Main stylesheet used across pages.
- script.js — Global scripts (if present).
- about.html — About page (matches home visual style).
- projects.html — Projects index page (links to case studies and demos).
- contact.html — "Get in touch" page with contact form placeholder.
- README.md — This file.

Case study pages (one per project):
- projects_color.html — Color Palette case study + links to demo.
- projects_password.html — Password Generator case study.
- projects_dictionary.html — Dictionary case study.
- projects_quiz.html — Quiz-Game case study.
- (Budget has its own case study / demo files in `budget/` if included; budget case study intentionally excluded.)

Demo folders (place demo files here, if present):
- color_palette/ or color_palette-demo/ — demo for Color Palette.
- password_generator/ — demo for Password Generator.
- dictionary/ — demo for Dictionary app.
- quiz-game/ — demo for Quiz-Game.
- project-one-demo/, project-two-demo/, project-three-demo/ — generic demo placeholders.
- budget/ — Budget demo (if present).

Each demo folder may include a package.json with a start script that uses http-server:
- Example start command (from demo folder): `npm start`
- Ports used in templates: 8081 / 8082 / 8083 (adjust if needed).

## How the pages tie together

- Navigation links point to `index.html`, `about.html`, `projects.html`, `contact.html`.
- Projects index should link to case-study pages which in turn link to demo folders.
- style.css is shared — edit it to change global look and spacing.
- To make the container/header blend, use semi-transparent backgrounds and border-radius rules in style.css (see comments in stylesheet).

## Editing notes

- Fonts are loaded via Google Fonts in the head of each HTML file. Change or remove fonts in each file if altering typography.
- The contact form uses a placeholder action. Replace `action="#"` with your form endpoint (Formspree, Netlify Forms, server endpoint) and adjust script.js if you add client-side submission.
- Demo placeholders: drop built demo files (index.html, assets) into each demo folder. Each demo folder can be served independently.

## Running multiple demos

If you host several demos locally, run each demo on a separate port:
- Project One: `npx http-server project-one-demo -p 8081`
- Project Two: `npx http-server project-two-demo -p 8082`
- Project Three: `npx http-server project-three-demo -p 8083`

Or open each demo via Live Server in VS Code.

## Accessibility & Performance

- Case-study templates include recommended accessibility notes (aria-live for dynamic updates, keyboard focus management).
- Keep images optimized and lazy-load heavy media for better performance.

## Deployment

- Static hosting options: GitHub Pages, Netlify, Vercel.
- For each demo folder, deploy that folder or the whole repo and point case-study links to the deployed demo URLs.

## Useful commands (Windows / cross-platform)

- Serve portfolio root:
  - npx http-server . -p 8080 -c-1
- Serve a demo folder:
  - npx http-server .\project-one-demo -p 8081 -c-1
- Python:
  - python -m http.server 8080

## Next steps (suggested)

- Wire contact form to a real endpoint.
- Replace demo placeholders with built projects and confirm relative paths.
- Add images/screenshots to case studies and update metrics/results.
- Optionally add a top-level package.json to run multiple demos with different npm scripts.

## License & contact

- Add a LICENSE file if you want to clarify reuse.
- Contact: update `contact.html` email address to your real address.

---
Keep files organized: place each demo inside its own folder, confirm links in case-study pages point to the correct demo paths, and run demos locally before deploying.
