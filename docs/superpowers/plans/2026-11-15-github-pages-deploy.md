# GitHub Pages deployment — Implementation Plan

**Goal:** Publish both calculators on GitHub Pages and embed them in the Notion lesson.
**Design:** [../specs/2026-11-15-mobile-calculators-design.md](../specs/2026-11-15-mobile-calculators-design.md)

## Tasks

- [x] **1. Project folder** — `~/woodwork-calculators`, with calculators, landing page, README, docs.
- [x] **2. Install GitHub CLI** — `brew install gh` (v2.104.0).
- [ ] **3. Authenticate gh** — teacher runs `gh auth login --web` with the intended GitHub account.
      Verify: `gh auth status` shows the right account.
- [ ] **4. Create repo and push**
      ```bash
      git init -b main && git add -A && git commit -m "Initial calculators"
      gh repo create woodwork-calculators --public --source . --push
      ```
- [ ] **5. Enable GitHub Pages** (branch `main`, path `/`)
      ```bash
      gh api -X POST repos/{owner}/woodwork-calculators/pages -f "source[branch]=main" -f "source[path]=/"
      ```
      Verify: `https://<user>.github.io/woodwork-calculators/` loads (may take ~1 min).
- [ ] **6. Test** each page at phone width: valid input, `10-3/4`, `10.75`, invalid text.
- [ ] **7. Notion** — replace the two uploaded-file embeds with URL embeds + fallback text links.
      Record URLs in [../../notion-integration.md](../../notion-integration.md).
- [ ] **8. Clean up** — after teacher confirms on a phone, remove the old Notion databases/forms.
