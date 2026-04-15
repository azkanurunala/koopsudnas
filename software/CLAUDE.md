# CLAUDE.md — Modern Software Development Training

## Project Overview

Training course untuk developer profesional. **36 file HTML** di folder `software/` (sibling dari parent AI-OPINT course). Struktur mirror parent: 5 core modul + 1 optional AI deep-dive.

**Bahasa:** Mixed — narasi Bahasa Indonesia, kode & istilah teknis English.

**AI-Assisted:** Setiap sesi di Modul 01-05 punya dedicated slide 7 "AI-Assisted Workflow" dengan 3 concrete prompt examples (Cursor / GitHub Copilot / Claude Code). Modul 06 adalah deep-dive tool mastery.

---

## File Structure

```
software/
├── index.html    ← ENTRY POINT
│
├── modul-01-software-fundamentals.html          (sky blue #0ea5e9)
│   ├── sesi-01-01-clean-code.html
│   ├── sesi-01-02-version-control.html
│   ├── sesi-01-03-collaboration.html
│   └── sesi-01-04-dev-environments.html
│
├── modul-02-architecture-design.html            (cyan #06b6d4)
│   ├── sesi-02-01-system-design.html
│   ├── sesi-02-02-design-patterns.html
│   ├── sesi-02-03-api-design.html
│   └── sesi-02-04-data-modeling.html
│
├── modul-03-testing-quality.html                (indigo #6366f1)
│   ├── sesi-03-01-testing-pyramid.html
│   ├── sesi-03-02-tdd-bdd.html
│   ├── sesi-03-03-code-review.html
│   └── sesi-03-04-debugging-profiling.html
│
├── modul-04-devops-delivery.html                (violet #8b5cf6)
│   ├── sesi-04-01-cicd-pipelines.html
│   ├── sesi-04-02-containers-orchestration.html
│   ├── sesi-04-03-infrastructure-as-code.html
│   └── sesi-04-04-observability.html
│
├── modul-05-production-engineering.html         (fuchsia #d946ef)
│   ├── sesi-05-01-build-service.html            (Phase 1)
│   ├── sesi-05-02-deploy-pipeline.html          (Phase 2)
│   ├── sesi-05-03-monitor-debug.html            (Phase 3)
│   └── sesi-05-04-iterate-improve.html          (Phase 4)
│
└── modul-06-ai-assisted-development.html        (pink #ec4899) — DEEP DIVE, 9 sessions
    ├── sesi-06-01-ai-coding-landscape.html
    ├── sesi-06-02-github-copilot.html
    ├── sesi-06-03-cursor.html
    ├── sesi-06-04-claude-code.html
    ├── sesi-06-05-aider-windsurf.html
    ├── sesi-06-06-v0-bolt.html
    ├── sesi-06-07-mcp-tooling.html
    ├── sesi-06-08-codebase-indexing.html
    └── sesi-06-09-ai-workflow-capstone.html
```

**Total:** 36 HTML files (1 index + 6 module + 29 session).

---

## Color Scheme (cool blues → pink progression)

| Module | Primary | Dark | Tailwind class prefix |
|--------|---------|------|------|
| 01 Software Fundamentals | `#0ea5e9` sky | `#0284c7` | `sky-400/500` |
| 02 Architecture & Design | `#06b6d4` cyan | `#0891b2` | `cyan-400/500` |
| 03 Testing & Quality | `#6366f1` indigo | `#4f46e5` | `indigo-400/500` |
| 04 DevOps & Delivery | `#8b5cf6` violet | `#7c3aed` | `violet-400/500` |
| 05 Production Engineering | `#d946ef` fuchsia | `#c026d3` | `fuchsia-400/500` |
| 06 AI-Assisted Development | `#ec4899` pink | `#db2777` | `pink-400/500` |

**AI-Assisted slide** (slide 7 di setiap session Modul 01-05) selalu pink `#ec4899` — sebagai visual cue bahwa ini bagian AI.

---

## Navigation Map

### Module 01 — Software Fundamentals (sky blue)

| Session | Prev Link | Next Link |
|---------|-----------|-----------|
| sesi-01-01 | modul-01-software-fundamentals.html | sesi-01-02-version-control.html |
| sesi-01-02 | sesi-01-01-clean-code.html | sesi-01-03-collaboration.html |
| sesi-01-03 | sesi-01-02-version-control.html | sesi-01-04-dev-environments.html |
| sesi-01-04 | sesi-01-03-collaboration.html | sesi-02-01-system-design.html (cross-module) |

### Module 02 — Architecture & Design (cyan)

| Session | Prev Link | Next Link |
|---------|-----------|-----------|
| sesi-02-01 | modul-02-architecture-design.html | sesi-02-02-design-patterns.html |
| sesi-02-02 | sesi-02-01-system-design.html | sesi-02-03-api-design.html |
| sesi-02-03 | sesi-02-02-design-patterns.html | sesi-02-04-data-modeling.html |
| sesi-02-04 | sesi-02-03-api-design.html | sesi-03-01-testing-pyramid.html (cross-module) |

### Module 03 — Testing & Quality (indigo)

| Session | Prev Link | Next Link |
|---------|-----------|-----------|
| sesi-03-01 | modul-03-testing-quality.html | sesi-03-02-tdd-bdd.html |
| sesi-03-02 | sesi-03-01-testing-pyramid.html | sesi-03-03-code-review.html |
| sesi-03-03 | sesi-03-02-tdd-bdd.html | sesi-03-04-debugging-profiling.html |
| sesi-03-04 | sesi-03-03-code-review.html | sesi-04-01-cicd-pipelines.html (cross-module) |

### Module 04 — DevOps & Delivery (violet)

| Session | Prev Link | Next Link |
|---------|-----------|-----------|
| sesi-04-01 | modul-04-devops-delivery.html | sesi-04-02-containers-orchestration.html |
| sesi-04-02 | sesi-04-01-cicd-pipelines.html | sesi-04-03-infrastructure-as-code.html |
| sesi-04-03 | sesi-04-02-containers-orchestration.html | sesi-04-04-observability.html |
| sesi-04-04 | sesi-04-03-infrastructure-as-code.html | sesi-05-01-build-service.html (cross-module) |

### Module 05 — Production Engineering Capstone (fuchsia)

| Session | Prev Link | Next Link |
|---------|-----------|-----------|
| sesi-05-01 (Phase 1) | modul-05-production-engineering.html | sesi-05-02-deploy-pipeline.html |
| sesi-05-02 (Phase 2) | sesi-05-01-build-service.html | sesi-05-03-monitor-debug.html |
| sesi-05-03 (Phase 3) | sesi-05-02-deploy-pipeline.html | sesi-05-04-iterate-improve.html |
| sesi-05-04 (Phase 4) | sesi-05-03-monitor-debug.html | sesi-06-01-ai-coding-landscape.html (cross-module) |

### Module 06 — AI-Assisted Development (pink, 9 sessions)

| Session | Prev Link | Next Link |
|---------|-----------|-----------|
| sesi-06-01 | modul-06-ai-assisted-development.html | sesi-06-02-github-copilot.html |
| sesi-06-02 | sesi-06-01-ai-coding-landscape.html | sesi-06-03-cursor.html |
| sesi-06-03 | sesi-06-02-github-copilot.html | sesi-06-04-claude-code.html |
| sesi-06-04 | sesi-06-03-cursor.html | sesi-06-05-aider-windsurf.html |
| sesi-06-05 | sesi-06-04-claude-code.html | sesi-06-06-v0-bolt.html |
| sesi-06-06 | sesi-06-05-aider-windsurf.html | sesi-06-07-mcp-tooling.html |
| sesi-06-07 | sesi-06-06-v0-bolt.html | sesi-06-08-codebase-indexing.html |
| sesi-06-08 | sesi-06-07-mcp-tooling.html | sesi-06-09-ai-workflow-capstone.html |
| sesi-06-09 | sesi-06-08-codebase-indexing.html | index.html |

---

## Session Template Structure (10 slides)

Setiap file `sesi-*.html` wajib punya struktur 10 slide:

1. **Title slide** — session title + brief intro + CTA "Mulai Sesi"
2. **Learning Objectives** — 4-card grid (md:grid-cols-2)
3. **Concept 1/3** — konsep pertama dengan penjelasan + comparison
4. **Concept 2/3** — konsep kedua, biasanya dengan code example
5. **Concept 3/3** — konsep ketiga, bisa dengan diagram/rule
6. **Comparison / Expected Output** — side-by-side bad vs good
7. **AI-Assisted Workflow** ⭐ **MANDATORY** — dedicated slide dengan 3 `.ai-card` boxes, masing-masing dengan concrete prompt di `.code-block` untuk Cursor/Copilot/Claude Code. Warna AI slide selalu pink terlepas dari warna module.
8. **Quiz** — 4-option Alpine interactive dengan correct-answer feedback
9. **Hands-On Exercise** — task + code template + AI prompt template
10. **Recap + Footer Nav** — key takeaways cards + prev/next nav buttons

## AI-Assisted Slide Rules

Slide 7 setiap sesi Modul 01-05 WAJIB:
- Kontainer `.ai-slide` dengan background gradient pink
- Badge `.ai-badge` dengan label "AI-ASSISTED WORKFLOW"
- 3 buah `.ai-card` boxes, masing-masing untuk:
  1. **Cursor** — inline edit / Composer use case
  2. **GitHub Copilot** — autocomplete / chat / review pattern
  3. **Claude Code** — CLI agent / skill / plan mode pattern
- Setiap card punya concrete prompt di `<pre class="code-block">` element
- Pitfall/warning note di akhir slide dengan warna pink border

## Checklist: Verify Navigation

- [ ] `software/index.html` link ke semua 6 module overview pages
- [ ] Setiap module overview page punya link back ke `software/index.html` dan link ke semua sessionnya
- [ ] Setiap session page punya: back-to-module link, prev-session link, next-session link
- [ ] Cross-module links benar: 01→02, 02→03, 03→04, 04→05, 05→06, 06→landing
- [ ] Tombol "Buka Sesi" di module overview page resolve ke file yang ada
- [ ] Semua session pages punya dedicated "AI-Assisted Workflow" slide 7 (Modul 01-05)
- [ ] Navbar back link arah `software/index.html` di module pages (bukan `../index.html`)
- [ ] Landing page `software/index.html` punya link `../index.html` back ke parent AI-OPINT course

## Notes

1. **All links relative** — file harus tetap dalam folder `software/`
2. **Self-contained** — semua CSS/JS inline, tidak ada shared asset files
3. **CDN-only** — Tailwind, Alpine.js, Google Fonts
4. **AI-Assisted is NOT optional** — ini core differentiator course ini
5. **Bahasa Indonesia narrative, English code/terms** — jangan terjemahkan term teknis
