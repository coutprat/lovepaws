# Love Paws Foundation — storyline, note and demo site

Working repo for the Love Paws Foundation brief: a storyline and note on stray management in India, and a demo website built from it.

## What is here

| Path | What it is |
|---|---|
| [public/index.html](public/index.html) | The website. One self-contained file. This is what Vercel serves. |
| [docs/01-storyline-and-note.md](docs/01-storyline-and-note.md) | The storyline (six beats, the argument in the order it should be told) and the note (evidence, structured against Vishal's mail: status, stats, government programme, failures, solutions, goals, BHAG). Includes sources and open questions. |
| [vercel.json](vercel.json) | Static deploy config: serves `public/`, no build step. |
| [serve.mjs](serve.mjs) | Zero-dependency local static server, for previewing without deploying. |

## Viewing it

Three ways, in order of least effort:

1. **Open the file.** Double-click `public/index.html`. It is fully self-contained, so it works straight off disk with no server and no internet.
2. **Serve it locally**, if you want a real `http://` origin:

```bash
node serve.mjs
```

Then open http://localhost:4173. No `npm install` needed; the server has no dependencies.

3. **Deploy it.** See below.

## Deploying to Vercel

The repo is zero-config static. There is no build step, no framework and no dependencies, so a deploy is a copy of `public/` onto the CDN.

**From the dashboard:** New Project, import `coutprat/lovepaws`, deploy. `vercel.json` already sets the framework to none and the output directory to `public`, so leave every field at its default.

**From the CLI:**

```bash
npx vercel --prod
```

Pushes to `main` deploy to production automatically once the project is linked. Pull requests get their own preview URL.

## Notes on the build

- **Eleven sections of evidence.** Beyond the argument itself: the census contradiction, state-by-state burden, what a sterilisation really costs, the rabies transmission chain, four Indian precedents (Goa, Jaipur, Sikkim, Ahmedabad) and a policy timeline running 1960 to 2030. Every chart, timeline and diagram is drawn in CSS, SVG or canvas, so there are no image files and no external requests.
- **The storyline is on the page.** Right after the hero, "The argument, in six beats" states the spine and lists all six beats, each linking to the section that makes it. It reads in under a minute and doubles as the contents, so the page can be handed over on its own.
- **Brass on ink.** The palette runs warm bone type and a brass accent over a cool ink-blue ground, with verdigris marking anything verified. The temperature contrast between warm type and cool ground is what keeps it from reading flat. Both themes measured against WCAG AA.
- **Not a template.** The page is set in a serif for the argument and a monospace for evidence, on a bone-paper ground, deliberately reading as a survey document rather than a charity landing page. Light and dark themes both ship, with a toggle in the masthead.
- **The scroll-driven section is the point.** In "Sixty-nine per cent is not almost", sterilisation coverage in a sample zone climbs from 0 to 85 per cent as you scroll. The ward map fills in, and the population curve beside it stays stubbornly upward until coverage crosses 70, then turns down. That single interaction carries the whole argument.
- **The projection is illustrative** and labelled as such on the page. It shows direction and threshold behaviour, not a forecast for any specific ward.
- **Every figure is sourced** in the footer and in the note. The ₹200 crore figure from the original mail is deliberately not on the site: it could not be confirmed from public record. See §10 of the note.
- **No external requests.** No CDN, no webfont, no analytics, no tracker. Fonts are system stacks, graphics are drawn on canvas at runtime. The page works offline and loads in one request.
- Placeholder content is limited to the contact address and entity details, and the footer says so plainly.

## Next

App strategy, per the sequence in Vishal's mail. A one-page outline is already in §12 of the note.
