# GitHub Pages deployment — Implementation Plan

**Goal:** Publish both calculators on GitHub Pages and embed them in the Notion lesson.
**Design:** [../specs/2026-11-15-mobile-calculators-design.md](../specs/2026-11-15-mobile-calculators-design.md)

## Tasks

- [x] **1. Project folder** — `~/woodwork-calculators`, with calculators, landing page, README, docs.
- [x] **2. Install GitHub CLI** — `brew install gh` (v2.104.0).
- [x] **3. Authenticate gh** — signed in as `audaciousjin` (HTTPS, keyring).
- [x] **4. Create repo and push** — https://github.com/audaciousjin/woodwork-calculators
      ```bash
      git init -b main && git add -A && git commit -m "Initial calculators"
      gh repo create woodwork-calculators --public --source . --push
      ```
- [x] **5. Enable GitHub Pages** (branch `main`, path `/`) — live at https://audaciousjin.github.io/woodwork-calculators/
      ```bash
      gh api -X POST repos/{owner}/woodwork-calculators/pages -f "source[branch]=main" -f "source[path]=/"
      ```
      Verify: `https://<user>.github.io/woodwork-calculators/` loads (may take ~1 min).
- [x] **6. Test** each page at phone width — all pages fit 375 px with no sideways scroll;
      door checker: `10 3/4`/`11 5/8` ✅, `10-3/4`/`11 3/4` ❌, `10.75`/`11.625` ✅, `abc` → error;
      top/bottom: `10 3/4`, `10-3/4"`, `10.75` → 12 3/16″, `abc` → error. (Desktop Chrome, 375 px frame; not yet on a real phone.)
- [x] **7. Notion** — URL embeds + fallback links added in sections 1 and 3.
      Old uploaded-file embeds could not be removed via API; see [../../notion-integration.md](../../notion-integration.md).
- [ ] **7b. Teacher check** — open the lesson's public link on a phone and confirm both embeds work.
- [ ] **8. Clean up** — after teacher confirms on a phone, remove the old Notion databases/forms.
