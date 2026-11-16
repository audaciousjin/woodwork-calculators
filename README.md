# Woodwork Calculators

Small, self-contained web calculators for the **Woodwork 11/12** cabinet project.
They are hosted on GitHub Pages and embedded in the class Notion page so students
can use them on any phone, tablet, or computer without downloading anything.

## Calculators

| Page | What it does | Formula |
| --- | --- | --- |
| [`door-panel.html`](door-panel.html) | Checks a student's door panel size answer (✅ / ❌), without revealing the answer | Panel = Opening + 1″ − 1/8″ |
| [`top-bottom-panel.html`](top-bottom-panel.html) | Calculates the cutting width for both the top and bottom cabinet panels | Panel = Door width + 1/16″ + 5/8″ + 1/8″ + 5/8″ |
| [`index.html`](index.html) | Landing page linking to both calculators | — |

**Entering sizes:** each size is a whole-inch number box plus a fraction drop-down
(`+ 0` … `+ 15/16`, in 1/16″ steps). Students never type `/`: phone number pads
don't have it, and on many phone keyboards it is hidden on a second page.

## Live site

Once GitHub Pages is on, the pages are served at
`https://<github-user>.github.io/woodwork-calculators/<page>.html`.
The current live URLs are recorded in
[docs/notion-integration.md](docs/notion-integration.md).

## Project layout

```
woodwork-calculators/
├── index.html                 # landing page
├── door-panel.html            # door panel answer checker
├── top-bottom-panel.html      # top & bottom panel width calculator
├── .nojekyll                  # serve files as-is (no Jekyll processing)
├── README.md
└── docs/
    ├── notion-integration.md  # where each page is embedded in Notion, live URLs
    └── superpowers/
        ├── specs/             # design documents (why / what)
        └── plans/             # implementation plans (how / steps)
```

## Editing a calculator

1. Edit the `.html` file. Each page is a single file with its own CSS and JS — no build step.
2. Open it in a browser and test at phone width (≈375 px).
3. Commit and push to `main`. GitHub Pages republishes within a minute or two.
   The Notion embeds update automatically because they point at the live URL.

## Rules for every page

- Must include `<meta name="viewport" content="width=device-width, initial-scale=1">`.
- Never require typing fractions: use a whole-inch box + 1/16″ fraction picker.
- No external scripts, fonts, or trackers: pages must work on locked-down school networks.
- No student data is stored or sent anywhere; everything runs in the browser.
