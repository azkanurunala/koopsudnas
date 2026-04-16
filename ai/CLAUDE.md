# CLAUDE.md — AI-OPINT Training Koopsudnas

## Project Overview

Training AI untuk Pamen Koopsudnas (TNI AU). Total **36 file HTML** dengan struktur navigasi hierarkis (5 core modul + 1 advanced workflow modul 9-sesi). **Gemini-only** — tidak ada perbandingan Claude/ChatGPT. Semua contoh menggunakan konteks Koopsudnas (Rafale, F-16, Su-27/30, GM400α, Natuna, IKN).

---

## File Structure

```
index.html    ← ENTRY POINT
│
├── modul-01-ai-fundamentals.html
│   ├── sesi-01-01-demistifikasi-ai.html
│   ├── sesi-01-02-framework-risen.html
│   ├── sesi-01-03-hands-on-prompt.html
│   └── sesi-01-04-etika-ai.html
│
├── modul-02-intelligence-analysis.html
│   ├── sesi-02-01-deep-research.html
│   ├── sesi-02-02-pattern-recognition.html
│   ├── sesi-02-03-threat-assessment.html
│   └── sesi-02-04-multi-source-fusion.html
│
├── modul-03-visual-intelligence.html
│   ├── sesi-03-01-visual-principles.html
│   ├── sesi-03-02-sitrep-visual.html
│   ├── sesi-03-03-dashboard-infografis.html
│   └── sesi-03-04-command-briefing.html
│
├── modul-04-strategic-reasoning.html
│   ├── sesi-04-01-deep-thinking.html
│   ├── sesi-04-02-coa-analysis.html
│   ├── sesi-04-03-risk-wargaming.html
│   └── sesi-04-04-decision-support.html
│
├── modul-05-capstone.html
│   ├── sesi-05-01-intel-fusion.html
│   ├── sesi-05-02-visual-package.html
│   ├── sesi-05-03-coa-wargaming.html
│   └── sesi-05-04-decision-brief.html
│
└── modul-06-multi-tool-operations.html  ← STANDALONE DEEP-DIVE (9 sesi: 1 overview + 6 Gemini tools + NotebookLM + Capstone)
    ├── sesi-06-01-gemini-ecosystem.html
    ├── sesi-06-02-create-image.html                (Imagen 4)
    ├── sesi-06-03-canvas.html                      (Workspace interaktif)
    ├── sesi-06-04-deep-research.html               (Autonomous research agent)
    ├── sesi-06-05-create-video.html                (Veo)
    ├── sesi-06-06-create-music.html                (Audio generation — NEW)
    ├── sesi-06-07-guided-learning.html             (Adaptive walkthrough)
    ├── sesi-06-08-notebooklm-deep-dive.html
    └── sesi-06-09-multi-tool-workflow.html         (Capstone)
```

**Modul 06 Access Model:** Advanced workflow — diakses setelah Modul 01-05 (ditandai badge "ADVANCED WORKFLOW"). Deep dive ke seluruh 6 tool Gemini + NotebookLM dengan pipeline end-to-end Koopsudnas. Tidak lagi "optional" atau "standalone".

---

## Navigation Rules

### 1. Landing Page → Module Overview

Dari `index.html`, setiap module card harus link ke:

| Card | Link Target |
|------|-------------|
| Modul 01 | `modul-01-ai-fundamentals.html` |
| Modul 02 | `modul-02-intelligence-analysis.html` |
| Modul 03 | `modul-03-visual-intelligence.html` |
| Modul 04 | `modul-04-strategic-reasoning.html` |
| Modul 05 | `modul-05-capstone.html` |
| Modul 06 (optional) | `modul-06-multi-tool-operations.html` |

### 2. Module Overview → Sessions

Setiap module overview page harus punya link ke semua session dalam modul tersebut.

**Contoh untuk Modul 01:**
```html
<a href="sesi-01-01-demistifikasi-ai.html">Sesi 1.1</a>
<a href="sesi-01-02-framework-risen.html">Sesi 1.2</a>
<a href="sesi-01-03-hands-on-prompt.html">Sesi 1.3</a>
<a href="sesi-01-04-etika-ai.html">Sesi 1.4</a>
```

### 3. Session Page Navigation

Setiap session page harus punya navigasi:

| Element | Link Target |
|---------|-------------|
| Back to Module | `modul-0X-*.html` (parent module) |
| Previous Session | `sesi-0X-0Y-*.html` (jika ada) |
| Next Session | `sesi-0X-0Y-*.html` (jika ada) |
| Previous Module | `modul-0X-*.html` (untuk sesi pertama) |
| Next Module | `modul-0X-*.html` (untuk sesi terakhir) |

**Session Navigation Pattern:**

```
┌─────────────────────────────────────────────────────────────┐
│  ← Modul 0X  │  SESI X.Y  │  40 Menit  │  TAG              │
├─────────────────────────────────────────────────────────────┤
│  ← Sesi X.(Y-1)                          Sesi X.(Y+1) →     │
└─────────────────────────────────────────────────────────────┘
```

---

## Complete Navigation Map

### Module 01: AI Fundamentals

| Session | Prev Link | Next Link |
|---------|-----------|-----------|
| sesi-01-01 | modul-01-ai-fundamentals.html | sesi-01-02-framework-risen.html |
| sesi-01-02 | sesi-01-01-demistifikasi-ai.html | sesi-01-03-hands-on-prompt.html |
| sesi-01-03 | sesi-01-02-framework-risen.html | sesi-01-04-etika-ai.html |
| sesi-01-04 | sesi-01-03-hands-on-prompt.html | modul-02-intelligence-analysis.html |

### Module 02: Intelligence Analysis

| Session | Prev Link | Next Link |
|---------|-----------|-----------|
| sesi-02-01 | modul-02-intelligence-analysis.html | sesi-02-02-pattern-recognition.html |
| sesi-02-02 | sesi-02-01-deep-research.html | sesi-02-03-threat-assessment.html |
| sesi-02-03 | sesi-02-02-pattern-recognition.html | sesi-02-04-multi-source-fusion.html |
| sesi-02-04 | sesi-02-03-threat-assessment.html | modul-03-visual-intelligence.html |

### Module 03: Visual Intelligence

| Session | Prev Link | Next Link |
|---------|-----------|-----------|
| sesi-03-01 | modul-03-visual-intelligence.html | sesi-03-02-sitrep-visual.html |
| sesi-03-02 | sesi-03-01-visual-principles.html | sesi-03-03-dashboard-infografis.html |
| sesi-03-03 | sesi-03-02-sitrep-visual.html | sesi-03-04-command-briefing.html |
| sesi-03-04 | sesi-03-03-dashboard-infografis.html | modul-04-strategic-reasoning.html |

### Module 04: Strategic Reasoning

| Session | Prev Link | Next Link |
|---------|-----------|-----------|
| sesi-04-01 | modul-04-strategic-reasoning.html | sesi-04-02-coa-analysis.html |
| sesi-04-02 | sesi-04-01-deep-thinking.html | sesi-04-03-risk-wargaming.html |
| sesi-04-03 | sesi-04-02-coa-analysis.html | sesi-04-04-decision-support.html |
| sesi-04-04 | sesi-04-03-risk-wargaming.html | modul-05-capstone.html |

### Module 05: Capstone

| Session | Prev Link | Next Link |
|---------|-----------|-----------|
| sesi-05-01 | modul-05-capstone.html | sesi-05-02-visual-package.html |
| sesi-05-02 | sesi-05-01-intel-fusion.html | sesi-05-03-coa-wargaming.html |
| sesi-05-03 | sesi-05-02-visual-package.html | sesi-05-04-decision-brief.html |
| sesi-05-04 | sesi-05-03-coa-wargaming.html | index.html |

### Module 06: Multi-Tool Operations (9 sesi — Gemini 6 tools + NotebookLM + Capstone) — STANDALONE

| Session | Prev Link | Next Link |
|---------|-----------|-----------|
| sesi-06-01 (Gemini Ecosystem) | modul-06-multi-tool-operations.html | sesi-06-02-create-image.html |
| sesi-06-02 (Create Image) | sesi-06-01-gemini-ecosystem.html | sesi-06-03-canvas.html |
| sesi-06-03 (Canvas) | sesi-06-02-create-image.html | sesi-06-04-deep-research.html |
| sesi-06-04 (Deep Research) | sesi-06-03-canvas.html | sesi-06-05-create-video.html |
| sesi-06-05 (Create Video) | sesi-06-04-deep-research.html | sesi-06-06-create-music.html |
| sesi-06-06 (Create Music — NEW) | sesi-06-05-create-video.html | sesi-06-07-guided-learning.html |
| sesi-06-07 (Guided Learning) | sesi-06-06-create-music.html | sesi-06-08-notebooklm-deep-dive.html |
| sesi-06-08 (NotebookLM Deep Dive) | sesi-06-07-guided-learning.html | sesi-06-09-multi-tool-workflow.html |
| sesi-06-09 (Multi-Tool Capstone) | sesi-06-08-notebooklm-deep-dive.html | index.html |

---

## Navigation HTML Templates

### Navbar untuk Session Page

```html
<nav class="fixed top-0 w-full z-50 bg-navy-900/80 backdrop-blur-xl border-b border-white/5">
  <div class="max-w-7xl mx-auto px-6 py-3 flex items-center justify-between">
    <div class="flex items-center gap-4">
      <!-- Back to Module -->
      <a href="modul-0X-[MODULE_NAME].html" class="flex items-center gap-2 text-white/60 hover:text-white">
        <svg class="w-5 h-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7"/>
        </svg>
        <span class="text-sm">Modul 0X</span>
      </a>
      <div class="h-4 w-px bg-white/20"></div>
      <!-- Session Info -->
      <div class="text-sm">
        <span class="text-[ACCENT_COLOR] font-mono">SESI X.Y</span>
        <span class="text-white/40 mx-2">•</span>
        <span class="text-white/60">XX Menit</span>
        <span class="ml-2 px-2 py-0.5 bg-[ACCENT_COLOR]/20 text-[ACCENT_COLOR] text-xs rounded-full">TAG</span>
      </div>
    </div>
    <!-- Prev/Next Navigation -->
    <div class="flex items-center gap-4">
      <a href="[PREV_SESSION].html" class="text-xs text-white/40 hover:text-white/60">← Sesi X.Y</a>
      <span class="text-white/20">|</span>
      <a href="[NEXT_SESSION].html" class="text-xs text-white/40 hover:text-white/60">Sesi X.Y →</a>
    </div>
  </div>
</nav>
```

### Footer Navigation untuk Session Page

```html
<div class="flex flex-col sm:flex-row gap-4">
  <a href="[PREV_SESSION].html" class="flex-1 py-3 px-6 glass rounded-xl text-center hover:bg-white/10">
    ← [PREV_SESSION_TITLE]
  </a>
  <a href="[NEXT_SESSION].html" class="flex-1 py-3 px-6 bg-[ACCENT_COLOR] rounded-xl text-center text-navy-900 font-semibold hover:bg-[ACCENT_COLOR_LIGHT]">
    [NEXT_SESSION_TITLE] →
  </a>
</div>
```

---

## Color Scheme per Module

| Module | Primary Color | CSS Variable | Tailwind Class |
|--------|---------------|--------------|----------------|
| 01 | Purple | `#a855f7` | `tactical-purple` / `purple-400` |
| 02 | Cyan/Teal | `#22d3ee` / `#14b8a6` | `tactical-cyan` / `cyan-400` |
| 03 | Blue | `#3b82f6` | `tactical-blue` / `blue-400` |
| 04 | Amber | `#f59e0b` | `tactical-amber` / `amber-400` |
| 05 | Orange | `#f97316` | `tactical-orange` / `orange-400` |
| 06 | Indigo / Violet | `#6366f1` | `tactical-indigo` / `indigo-400` |

### Session Colors within Module 04 (example)

| Session | Color | Hex |
|---------|-------|-----|
| 4.1 | Amber | `#f59e0b` |
| 4.2 | Green | `#10b981` |
| 4.3 | Red | `#ef4444` |
| 4.4 | Purple | `#a855f7` |

---

## Checklist: Verify Navigation

Run this checklist untuk setiap file:

### Landing Page
- [ ] Link ke semua 5 module overview pages
- [ ] Semua link relative (bukan absolute URL)

### Module Overview Pages
- [ ] Link back ke landing page
- [ ] Link ke semua 4 sessions dalam modul
- [ ] Link ke prev/next module (jika ada)

### Session Pages
- [ ] Link back ke parent module
- [ ] Link ke prev session (atau prev module untuk sesi pertama)
- [ ] Link ke next session (atau next module untuk sesi terakhir)
- [ ] Consistent navbar format
- [ ] Footer navigation buttons

---

## Quick Fix Commands

### Check for broken links (grep pattern)

```bash
# Find all href links
grep -h 'href="[^"]*\.html"' *.html | grep -oP 'href="\K[^"]+' | sort | uniq

# Compare with existing files
ls *.html | sort
```

### Find missing navigation

```bash
# Check if all sessions have back-to-module link
for f in sesi-*.html; do
  grep -q 'modul-0' "$f" || echo "Missing module link: $f"
done
```

---

## File Naming Convention

```
[TYPE]-[MODULE]-[SESSION]-[SLUG].html

TYPE:
  - index = landing page
  - modul = module overview
  - sesi = session detail

MODULE: 01, 02, 03, 04, 05, 06

SESSION: 01, 02, 03, 04 (within module)

SLUG: kebab-case description
```

---

## Notes

1. **All links are relative** — files harus di folder yang sama
2. **Consistent design system** — gunakan Tailwind + custom CSS variables
3. **Alpine.js** untuk interactivity (quiz, accordion, copy button)
4. **No GSAP** di session files — pakai CSS animations saja untuk reliability
5. **Mobile responsive** — semua navigation harus work di mobile

---

## Gemini Implementation Callout Pattern (Modul 01-05 → cross-reference ke Modul 06)

Beberapa sesi di Modul 01-05 punya sub-section callout "GEMINI IMPLEMENTATION" yang memberikan step-by-step cara menggunakan Gemini tools spesifik untuk task di sesi tersebut. Pattern HTML (collapsible, indigo theme):

```html
<div class="mt-12 glass-lit rounded-2xl border border-indigo-500/30 overflow-hidden" x-data="{ open: false }">
  <button @click="open = !open" class="w-full p-6 flex items-center justify-between gap-4 cursor-pointer">
    <div class="flex items-center gap-4">
      <div class="w-12 h-12 rounded-xl bg-indigo-500/20 flex items-center justify-center">
        <svg class="w-6 h-6 text-indigo-400" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 9l3 3-3 3m5 0h3M5 20h14a2 2 0 002-2V6a2 2 0 00-2-2H5a2 2 0 00-2 2z"/></svg>
      </div>
      <div class="text-left">
        <div class="font-mono text-xs text-indigo-400 mb-1">GEMINI IMPLEMENTATION • [TOOL NAME]</div>
        <h3 class="text-lg font-semibold">[Judul: cara Gemini melakukan hal yang sama]</h3>
      </div>
    </div>
    <svg class="w-5 h-5 text-white/40 transition-transform" :class="open ? 'rotate-180' : ''" ...>...</svg>
  </button>
  <div class="accordion-content" :class="open ? 'open' : ''">
    <div class="px-6 pb-6 pt-2 border-t border-indigo-500/20">
      <!-- step-by-step Gemini implementation untuk task tersebut -->
      <!-- Cross-link ke Modul 06: -->
      <a href="modul-06-multi-tool-operations.html" class="...">Deep dive di Modul 06 →</a>
    </div>
  </div>
</div>
```

Sesi yang punya callout ini:
- sesi-01-02-framework-risen.html — RISEN di 3 jalur: gemini.google.com Consumer, Gems, AI Studio
- sesi-02-01-deep-research.html — Deep Research untuk intel background brief
- sesi-02-04-multi-source-fusion.html — NotebookLM sebagai fusion engine
- sesi-03-02-sitrep-visual.html — Gemini Imagen untuk visual generation
- sesi-03-03-dashboard-infografis.html — Gemini Canvas untuk dashboard
- sesi-04-01-deep-thinking.html — Gemini 2.5 Pro Thinking Mode

---

## Known Issues to Fix

_(Status at 2026-04-16)_

1. ~~**Module overview pages** perlu ditambahkan direct links ke session files~~ ✅ DONE
2. ~~**Cross-module navigation** — sesi terakhir tiap modul harus link ke modul berikutnya~~ ✅ DONE
3. ~~**Gemini-only refactor** — hapus semua referensi Claude/ChatGPT, ganti dengan Gemini ekosistem~~ ✅ DONE (36 file, 0 referensi tersisa)
4. ~~**Modul 06 "optional" framing** — ubah ke "Advanced Workflow", akses setelah Modul 01-05~~ ✅ DONE
5. **Breadcrumb** — belum ada full breadcrumb (Landing > Module > Session) _(future enhancement, tidak kritikal)_

---

## Future Improvements

- [ ] Add progress tracking (localStorage)
- [ ] Add completion certificate
- [ ] Add search functionality
- [ ] Add print-friendly stylesheet
- [ ] Add offline PWA support
