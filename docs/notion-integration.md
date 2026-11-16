# Notion integration

Where each calculator appears in Notion, and its live URL.

**Lesson page:** Panel Sizes: from door's panel to the cabinet panels
(Woodwork 11/12) — `https://app.notion.com/p/40e19d02a7ee80f19cffcb00ec497362`

| Calculator | Notion section | Live URL | Embedded? |
| --- | --- | --- | --- |
| Door panel checker | 1. What's my door panel size? | https://audaciousjin.github.io/woodwork-calculators/door-panel.html | Yes (URL embed + fallback link), added 2026-11-15 |
| Top & bottom panel width | 3. What are the widths of my top and bottom panels? | https://audaciousjin.github.io/woodwork-calculators/top-bottom-panel.html | Yes (URL embed + fallback link), added 2026-11-15 |

Landing page: https://audaciousjin.github.io/woodwork-calculators/
Repository: https://github.com/audaciousjin/woodwork-calculators

## Still on the Notion page (to remove after phone check)

- The two old **uploaded-file** embeds (`preview (1).html`, `top_bottom_panel_calculator.html`),
  directly above each new embed. The Notion API cannot select these blocks — delete by hand
  (hover → ⋮⋮ → Delete).
- The **Door Panel Checker** and **Top & Bottom Panel Calculator** Notion databases
  (earlier formula/form attempt), directly below each new embed.

## How to embed (manual)

1. In Notion, type `/embed`, paste the live URL, press **Embed link**.
2. Resize the embed so the whole calculator shows without scrolling on a phone.
3. Underneath, add a plain link: "Calculator not showing? Open it here →".

## Why URL embeds

Uploaded `.html` files are offered as downloads on many mobile devices.
A URL embed is rendered as a live iframe in Notion on all platforms.
