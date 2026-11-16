# Mobile-friendly calculators for the Notion lesson — Design

- **Date:** 2026-11-15
- **Status:** Approved (hosting choice: GitHub Pages)
- **Notion page:** "Panel Sizes: from door's panel to the cabinet panels" (Woodwork 11/12)

## Problem

Two HTML calculators were uploaded to the Notion lesson page as files and
embedded. On desktop Notion renders them, but on many phones and tablets
(especially iOS) Notion only offers the uploaded `.html` as a **download**.
Students use a mix of school and personal devices, so the calculators must work
in any mobile browser, inside the Notion page, with no download and no login.

## Requirements

1. Works on iOS/Android phones and tablets, Chromebooks, and desktops.
2. Shown inside the Notion page (students stay on the lesson).
3. Students must not need a Notion or any other account.
4. The lesson page itself stays read-only for students.
5. No student data collected.

## Options considered

| Option | Result | Why accepted / rejected |
| --- | --- | --- |
| Keep uploaded `.html` file embeds | Download prompt on mobile | Root cause of the problem |
| Notion database with formula columns | Worked, results verified | Rejected: students need edit access; public editing requires a Notion login and exposes the whole page to edits |
| Notion database + anonymous Notion form | Possible | Rejected by teacher: form questions and public sharing must be set up by hand, and students can't see their result on the form itself |
| **Static pages on GitHub Pages, embedded by URL** | Live iframe on every device | **Chosen**: free, stable, public, no login for students; Notion renders URL embeds on mobile |

## Design

- Each calculator is a single self-contained HTML file (inline CSS/JS, no
  external requests), with a mobile viewport meta tag.
- Hosted in the public repo `woodwork-calculators`, GitHub Pages serving the
  `main` branch root. `.nojekyll` so files are served as-is.
- Notion lesson page: replace each uploaded-file embed with an `/embed` block
  pointing at the live URL, plus a plain text link underneath as a fallback for
  devices or networks that block iframes.

## Calculators

### Door panel checker (`door-panel.html`)
- Inputs: frame opening, student's calculated panel size.
- Correct answer: `opening + 1 − 1/8` (1/2″ groove each side, 1/8″ clearance).
- Output: ✅ / ❌ only; the correct value is never shown (learning check).

### Top & bottom panel width (`top-bottom-panel.html`)
- Input: door width.
- Output: `door + 1/16 + 5/8 + 1/8 + 5/8`, rounded to nearest 1/16″, with breakdown.
- Example: 10 3/4″ → 12 3/16″.

## Leftovers from earlier attempts (in Notion)

The "Door Panel Checker" and "Top & Bottom Panel Calculator" Notion databases
(with form views and a "Submitted" column) still exist on the lesson page.
Remove them once the GitHub Pages embeds are confirmed working.

## Known content issue (not part of this work)

Section 2 of the lesson says crosscut to **34 1/4″** but its summary table says
**34 1/2″**. Teacher to confirm which is correct.
