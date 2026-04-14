# PROMPT ADJUSTMENT GUIDE — Training AI Koopsudnas

> **Tujuan dokumen:** Panduan rework prompt/contoh/skenario di seluruh 31 HTML file training supaya merepresentasikan **5 tugas pokok Koopsudnas**, bukan hanya intelligence/threat analysis.
>
> **Status:** Reference document. Implementasi akan dilakukan sesi-per-sesi, dokumen ini jadi source of truth.

---

## 0. Konteks Tugas Pokok Koopsudnas

Koopsudnas (Komando Operasi Udara Nasional) adalah komando utama tempur TNI AU. Tugas pokok:

| # | Tugas Pokok | Scope | Coverage Saat Ini |
|---|-------------|-------|-------------------|
| 1 | **Operasi Pertahanan Udara** | Pengawasan & penindakan wilayah udara, hanud, intercept | 90% (over-represented) |
| 2 | **OMSP** (Operasi Militer Selain Perang) | Bencana, pengungsian, SAR, bantuan kemanusiaan | **0%** |
| 3 | **Pembinaan Satuan** | Kesiapan operasional Koopsud I/II/III + Kopasgat | **0%** |
| 4 | **Pengembangan Doktrin** | Doktrin, organisasi, strategi alutsista hanud | **0%** |
| 5 | **Penegakan Hukum Udara** | Kerja sama lintas instansi (AirNav, Basarnas, Kemlu, Bea Cukai) | 5% (minimal) |

**Prinsip:** Framework yang sudah ada (RISEN, CACS, CoT, COA analysis, wargaming, fusion, visual principles) **sudah solid dan tidak diganti**. Yang di-adjust hanya *context, skenario, dan contoh* yang dibawa oleh prompt.

---

## 1. Prinsip Adjustment

### 1.1 Rasio Representasi Target
Setiap sesi dengan prompt/contoh konkret idealnya memiliki representasi lintas tugas pokok. Target kasar:
- **Modul 01 (Fundamentals):** 1 contoh per tugas pokok di section relevant
- **Modul 02 (Intel Analysis):** Default intel, 1–2 variant non-intel (OMSP/Gakkum)
- **Modul 03 (Visual):** 4 variant per template (threat/SAR/bencana/pembinaan)
- **Modul 04 (Reasoning):** Default hanud, 2–3 variant (OMSP/doktrin/pembinaan)
- **Modul 05 (Capstone):** 3 pathway (A=threat, B=SAR, C=doktrin) — student pilih 1
- **Modul 06 (Multi-Tool):** Scenario matrix footnote, tool tetap sama

### 1.2 Aturan OPSEC (untuk semua skenario baru)
- **Generic callsigns:** ALPHA, BRAVO, GARUDA-01, BANTENG-03 — bukan callsign nyata
- **Generic locations:** sektor NE-7, Zulu-9, FIR Ujung Pandang — bukan koordinat pangkalan nyata
- **Fictional unit designations:** Skadron Udara XX, Wing Udara YY — bukan unit nyata dengan data sensitif
- **No real procurement data:** gunakan "pesawat tempur multi-role" bukan nama varian spesifik yang sensitif
- **Aman untuk training publik** — assume dokumen bisa dibaca orang di luar koopsudnas

### 1.3 Framing OMP vs OMSP
- **OMP (Operasi Militer Perang):** tone combat, ROE ketat, adversarial, time-critical. Cocok untuk Domain A, sebagian E.
- **OMSP:** tone humanitarian, multi-agency, resource-allocation, non-adversarial. Cocok untuk Domain B, sebagian C & E.
- **Peacetime pembinaan/doktrin:** tone analytical, strategic, long-horizon. Cocok untuk Domain C & D.
- **Etika AI (Sesi 1.4):** tetap jadi benchmark di SEMUA domain — weapon release keputusan manusia, decision support AI OK.

---

## 2. Skenario Bank — 5 Domain × 3–4 Skenario

Skenario di bank ini **reusable across modul**. Ketika implementasi sesi tertentu, tinggal ambil satu skenario dari bank yang cocok dengan framework sesi tsb.

### Domain A — Operasi Pertahanan Udara *(existing, retain)*

**A1 — "GARUDA ALERT"**
Unidentified contact memasuki sektor udara perbatasan pada 0430L. Radar long-range mendeteksi kontak pada altitude 28,000 ft, speed 480 kt, heading 270°. Transponder OFF. Tidak ada flight plan terdaftar di AirNav.
- Tools: Radar data, SIGINT, HUMINT border observer
- Output: Threat assessment brief, intercept recommendation, escalation ladder

**A2 — "Reconnaissance Threat NE-7/8/9"** *(existing Capstone A)*
Surge komunikasi 340% di 3 frekuensi baru, 47 unidentified aircraft contacts dengan pola racetrack di 15,000–25,000 ft, HUMINT melaporkan aktivitas darat tidak lazim, OSINT indikasi exercise cover story regional.
- Tools: 4-source fusion (SIGINT + Radar + HUMINT + OSINT)
- Output: Unified threat assessment, COA deterrence, decision brief

**A3 — "Radar Anomaly + SIGINT Spike"**
Dalam 48 jam terakhir: 4 anomali radar (transponder shuffle, altitude deviation, kontak hilang di area blind spot), SIGINT mendeteksi freq hopping pattern baru.
- Tools: Pattern recognition (temporal, spatial, behavioral)
- Output: Anomaly table + correlation matrix + recommended response

---

### Domain B — OMSP / Bencana / SAR *(new)*

**B1 — "CENDRAWASIH RESCUE"**
Gempa M7.2 di Banda Sea jam 0215L. Sebuah pesawat komersial ATR-72 rute Ambon–Kaimana lost contact pada 0230L, last known position 4.2°S 129.8°E, altitude 18,000 ft. Cuaca bad weather, visibility <2 km. 68 penumpang + 4 kru di manifest. Basarnas request koordinasi airlift SAR.
- Tools: Fusion (weather forecast + radar last track + survivor probability + SAR asset availability)
- Output: Search area prioritization, resource allocation, SITREP Basarnas
- **Multi-agency:** TNI AU (airlift) + Basarnas (coordination) + TNI AL (maritime) + Kemenhub (KNKT) + BMKG (weather)

**B2 — "Banjir Bandang Sulawesi"**
Banjir bandang di 3 kabupaten Sulawesi, 12,000 pengungsi, 4 shelter aktif, akses darat terputus. Tasking Koopsudnas: airlift logistik + evakuasi medis prioritas.
- Tools: Resource allocation (C-130 sortie planning, cargo prioritization, shelter demand matrix)
- Output: Air tasking order, shelter resupply priority list, command dashboard
- **Multi-agency:** BNPB (lead) + TNI AU (airlift) + Pemda + PMI + Kemenkes

**B3 — "NEO — Evakuasi WNI"**
Situasi regional memanas, 2,400 WNI di negara tetangga perlu dievakuasi dalam 72 jam. Landing rights pending clearance diplomatik.
- Tools: CoA analysis (3 routing options), risk wargaming (diplomatic complications)
- Output: NEO execution plan, diplomatic clearance tracker, decision brief
- **Multi-agency:** Kemlu (lead) + TNI AU (airlift) + BIN + Imigrasi

**B4 — "Karhutla Response"**
Kebakaran hutan & lahan Kalimantan, water bombing operation, koordinasi dengan BNPB & Pemda. 5 titik api aktif, radius 15 km.
- Tools: SITREP visual, spatial pattern analysis (fire spread), resource dashboard
- Output: Daily SITREP, water bombing tasking, trend analysis fire progression

---

### Domain C — Pembinaan Satuan *(new)*

**C1 — "Readiness Assessment Menjelang ADEX"**
Koopsud II akan ikut Air Defense Exercise multinational dalam 90 hari. Assessment kesiapan: serviceability rate 3 skadron, flight hours crew, ammo stock, maintenance backlog, training gap.
- Tools: Gap analysis, pattern recognition (readiness trend), COA comparison (remediation options)
- Output: Readiness assessment brief, remediation roadmap, resource request memo
- **Non-adversarial, analytical tone**

**C2 — "Training Pipeline Gap — Kopasgat"**
Kopasgat dapat kapabilitas baru (misalnya: forward air control + combat control team). Pipeline training existing belum punya modul tsb.
- Tools: Deep research (best practice lintas doktrin), CACS sintesis
- Output: Training curriculum gap analysis, recommended pipeline update, timeline

**C3 — "Resource Prioritization Lintas 3 Koopsud"**
Anggaran pemeliharaan tahun depan minus 15%, harus prioritisasi antara Koopsud I (asset tertua, backlog besar), II (operasional tertinggi), III (wilayah timur strategis).
- Tools: Weighted COA comparison, deep thinking chain-of-thought
- Output: Resource allocation memo ke Pangkoopsudnas, trade-off matrix

**C4 — "Post-Exercise Lessons Learned"**
Setelah latihan Angkasa Yudha, compile lessons learned dari 12 participating units, kategorisasi (training gap, doctrine gap, equipment gap), recommend corrective action.
- Tools: Pattern recognition (common failure modes), multi-source fusion (AAR reports)
- Output: Lessons learned document, corrective action tracker

---

### Domain D — Pengembangan Doktrin *(new)*

**D1 — "IADS Doctrine Review"**
Review doktrin Integrated Air Defense System Koopsudnas vs best practice NATO/regional (mis. Singapore, Australia). Apakah posture perlu update menghadapi era UAV & long-range precision strike?
- Tools: NotebookLM (source-grounded literature synthesis), deep research, deep thinking
- Output: Doctrine gap analysis, recommended posture update, stakeholder briefing
- **Cocok sekali untuk Modul 06 NotebookLM**

**D2 — "Lessons Learned → Doctrine Note"**
Sintesis hasil 3 exercise multinational terakhir jadi draft doctrine note. Identifikasi pattern yang cukup kuat untuk diformalkan sebagai doktrin.
- Tools: CACS fusion, pattern recognition, deep thinking
- Output: Draft doctrine note section, supporting evidence matrix

**D3 — "Interoperability Multi-Platform"**
Flight line masa depan: F-16 legacy + Rafale + kandidat KF-21. Doktrin tactical employment & C2 perlu di-review. Brief policy options ke Kasau.
- Tools: Comparative analysis, scenario planning, COA analysis
- Output: Policy briefing deck, risk assessment doktrinal, recommended direction

**D4 — "Cyber-Air Doctrine"**
Doktrin integrasi cyber defense di air operations belum komprehensif. Research best practice + draft doctrinal framework.
- Tools: Deep research (NotebookLM), structured synthesis
- Output: Doctrinal framework paper, implementation roadmap

---

### Domain E — Penegakan Hukum Udara *(new)*

**E1 — "Flight Information Region Violation"**
Pesawat asing small business jet memasuki FIR Jakarta tanpa clearance, tidak merespons radio, heading menuju ruang udara sensitif. Prosedur force-down & koordinasi AirNav/Kemlu.
- Tools: Decision tree (escalation ladder), real-time SITREP
- Output: Incident report, escalation decision brief, diplomatic notification draft
- **Multi-agency:** AirNav (ATC) + TNI AU (intercept) + Kemlu (diplomatic) + Kemenhub

**E2 — "Dugaan Penerbangan Gelap"**
SIGINT + radar anomaly menunjukkan kemungkinan penerbangan gelap untuk pengangkutan ilegal (narkotika/satwa) di FIR Ujung Pandang. Koordinasi Bea Cukai, Polri, BNN.
- Tools: Multi-source fusion, pattern recognition (route anomaly)
- Output: Joint operation plan, evidence package, chain-of-custody protocol

**E3 — "Force-Down Legal Chain"**
Setelah berhasil force-down pesawat unauthorized, prosedur legal chain-of-custody evidence, koordinasi dengan Kejaksaan Militer & sipil.
- Tools: Procedural checklist, decision support
- Output: Incident documentation package, legal handover brief

---

## 3. Per-File Adjustment Plan

Setiap entri berisi: current state, gap, proposed adjustment, priority.

### Landing & Module Overview Pages

#### `index.html`
- **Current:** Landing page, module cards framing training sebagai "AI-OPINT" (Operations Intelligence)
- **Gap:** Framing terlalu sempit ke OPINT
- **Proposed:** Reframe sebagai "AI untuk Operasi Koopsudnas" dengan sub-deskripsi mencakup 5 tugas pokok. Module card copy di-update agar tidak semua intel-centric.
- **Priority:** MEDIUM

#### `modul-01-ai-fundamentals.html`
- **Current:** Generic AI fundamentals
- **Gap:** Contoh use-case di overview mungkin intel-leaning
- **Proposed:** Pastikan 4 use-case di overview ada 1 per tugas pokok (intel, SAR, pembinaan, doktrin)
- **Priority:** LOW

#### `modul-02-intelligence-analysis.html`
- **Current:** Framing "intelligence analysis"
- **Gap:** Titel modul OK (intel memang core skill), tapi intro perlu jelaskan bahwa skill yang sama berlaku untuk non-intel scenarios
- **Proposed:** Tambah paragraph "Prinsip analisis di modul ini juga berlaku untuk OMSP (fusion data SAR), pembinaan satuan (fusion readiness data), dan penegakan hukum udara"
- **Priority:** MEDIUM

#### `modul-03-visual-intelligence.html`
- **Current:** "Visual intelligence" framing
- **Gap:** Titel masih intel, padahal skill visual universal
- **Proposed:** Subtitle "untuk SITREP, dashboard, dan command briefing — intel maupun OMSP". Intro highlight 4 variant visual deliverable.
- **Priority:** MEDIUM

#### `modul-04-strategic-reasoning.html`
- **Current:** Strategic reasoning framing generic OK
- **Gap:** Contoh di overview combat-heavy
- **Proposed:** Tambah contoh reasoning untuk pembinaan & doktrin sebagai peer contoh dari combat COA
- **Priority:** LOW

#### `modul-05-capstone.html`
- **Current:** Single scenario "GARUDA SHIELD" (threat/reconnaissance)
- **Gap:** Kunci — capstone hanya 1 pathway
- **Proposed:** **Restructure ke 3 pathway** — Capstone A (GARUDA SHIELD / threat, existing), Capstone B (CENDRAWASIH RESCUE / OMSP-SAR, new), Capstone C (IADS Doctrine Review / doktrin, new). Student pilih 1 pathway, 4 phase tetap sama.
- **Priority:** HIGH

#### `modul-06-multi-tool-operations.html`
- **Current:** Tool ecosystem overview
- **Gap:** OK tapi use-case example di overview masih threat-focused
- **Proposed:** Use-case grid diperluas ke 5 tugas pokok (mis: NotebookLM untuk doktrin synthesis, Gemini Canvas untuk SAR dashboard, Imagen untuk infografis OMSP)
- **Priority:** MEDIUM

---

### Modul 01 — AI Fundamentals

#### `sesi-01-01-demistifikasi-ai.html`
- **Current:** Teori dasar AI, contoh use-case minimal
- **Gap:** Use-case list generic, belum konkrit ke 5 tugas pokok
- **Proposed:** Section "Use case AI untuk Pamen Koopsudnas" berisi 5 bullet:
  - Operasi Hanud: auto-summary radar log
  - OMSP/SAR: fusion data multi-source untuk prioritisasi search area
  - Pembinaan Satuan: readiness trend analysis
  - Doktrin: literature synthesis dari policy papers
  - Gakkum Udara: anomaly detection pola penerbangan
- **Priority:** LOW

#### `sesi-01-02-framework-risen.html`
- **Current:** 1 example RISEN = "Analis Intelijen Senior TNI AU" untuk morning briefing
- **Gap:** Hanya 1 domain
- **Proposed:** Retain example primary (intel), **tambah 3 RISEN example variant** di section "RISEN Lintas Domain":
  1. RISEN untuk SAR Brief (Role: SAR coordinator; Goal: search prioritization brief)
  2. RISEN untuk Readiness Assessment (Role: staff pembinaan; Goal: gap analysis memo)
  3. RISEN untuk Doctrine Note (Role: doctrine officer; Goal: draft doktrinal synthesis)
- **Priority:** MEDIUM

#### `sesi-01-03-hands-on-prompt.html`
- **Current:** Exercise "GARUDA ALERT" threat assessment dari radar + field report
- **Gap:** Single exercise, intel-only
- **Proposed:** **Retain GARUDA ALERT** sebagai exercise 1, **tambah Exercise 2 "CENDRAWASIH RESCUE"** — student gunakan RISEN builder yang sama untuk draft prompt SAR coordination brief
- **Priority:** MEDIUM

#### `sesi-01-04-etika-ai.html`
- **Current:** Balanced ethical framework (COA, SITREP, report writing permissible; weapon release forbidden)
- **Gap:** Contoh keputusan semua combat-oriented
- **Proposed:** Tambah 2 contoh ethical contrast:
  - **OMSP context:** Permissible (resource prioritization dengan human sign-off) vs Forbidden (autonomous triage siapa yang diselamatkan)
  - **Gakkum context:** Permissible (evidence analysis) vs Forbidden (autonomous use of force decision)
- **Priority:** LOW

---

### Modul 02 — Intelligence Analysis

#### `sesi-02-01-deep-research.html`
- **Current:** CACS framework + 4-source intel fusion generic
- **Gap:** Example hanya intel
- **Proposed:** Retain CACS framework. Tambah **2 variant CACS example**:
  1. CACS untuk **D1 (IADS Doctrine Review)** — sources jadi policy papers, NATO STANAGs, regional doctrine
  2. CACS untuk **B1 (CENDRAWASIH RESCUE)** — sources jadi weather forecast, radar last track, survivor probability model, SAR asset database
- **Priority:** MEDIUM

#### `sesi-02-02-pattern-recognition.html`
- **Current:** 3 pattern types (temporal, spatial, behavioral) pakai 48-hour radar log
- **Gap:** Patterns hanya untuk threat detection
- **Proposed:** Retain temporal/spatial/behavioral framework. Tambah **"Operational Tempo Patterns"** section dengan 2 mini-case:
  1. **Training cycle patterns** (C-domain): identifikasi anomaly dalam training tempo lintas 3 skadron
  2. **SAR mission patterns** (B-domain): pattern waktu respons Basarnas vs TNI AU lintas bencana
- **Priority:** MEDIUM

#### `sesi-02-03-threat-assessment.html`
- **Current:** "Sektor Bravo" exercise, heavy threat-to-airspace framing, rubric 100% threat-centric
- **Gap:** Kritis — 100% intel. Tidak ada OMSP/Gakkum risk assessment.
- **Proposed:** **Major rework:**
  - Retain Sektor Bravo sebagai **primary exercise**
  - Reframe section "Threat Assessment" jadi "**Risk Assessment**" (lebih inklusif)
  - Tambah **2 variant exercise**:
    - **Humanitarian Risk Assessment** (OMSP): risk to civilian casualties di zona bencana, risk to SAR mission success
    - **Legal Risk Assessment** (Gakkum): risk escalation diplomatik saat force-down, risk chain-of-custody
  - Rubric di-update dari "threat justification" jadi "risk justification" (domain-agnostic)
- **Priority:** HIGH

#### `sesi-02-04-multi-source-fusion.html`
- **Current:** "Operation CORAL SEA" — 4 source fusion (SIGINT/IMINT/HUMINT/OSINT) untuk determine naval exercise vs hostile activity
- **Gap:** Fusion 100% intel-centric
- **Proposed:** **Major rework:**
  - Retain CORAL SEA sebagai Example 1 (intel fusion)
  - Tambah **Example 2 — "SAR Fusion"**: fusion 4 source non-intel (weather forecast BMKG + radar last track + survivor probability + SAR asset availability) untuk determine priority search area CENDRAWASIH RESCUE
  - Tambah **Example 3 — "Doctrine Fusion"** (ringkas): fusion 4 source (NATO doctrine + regional doctrine + lessons learned + policy papers) untuk draft posture update
  - Correlation matrix framework tetap sama
- **Priority:** HIGH

---

### Modul 03 — Visual Intelligence

#### `sesi-03-01-visual-principles.html`
- **Current:** Generic design principles (hierarchy, color, simplicity, 3-second rule, actionable)
- **Gap:** Contoh aplikasi belum lintas domain
- **Proposed:** Prinsip tetap. Tambah **mini-gallery "Prinsip dalam Praktik"** dengan 4 thumbnail:
  - Dashboard threat (existing)
  - Dashboard SAR progress
  - Dashboard readiness satuan
  - Dashboard doctrine compliance
- Color-coding guidance tambah skema untuk non-combat (mis. hijau = SAR progress, biru = logistik, kuning = pending clearance)
- **Priority:** LOW

#### `sesi-03-02-sitrep-visual.html`
- **Current:** SITREP + Threat Map, semua threat-centric (RED=hostile, BLUE=friendly)
- **Gap:** 1 template only, threat-only
- **Proposed:** **Major rework** — 4 variant SITREP template dengan tab selector:
  1. **Threat SITREP** (existing — retain as default)
  2. **SAR SITREP** (B1 CENDRAWASIH): search sectors, discovered debris, survivor locations, weather overlay
  3. **Bencana SITREP** (B2 Banjir Sulawesi): shelter status, supply distribution, airlift progress
  4. **Readiness SITREP** (C1 ADEX): unit readiness status, training progress, gap indicators
- Tiap variant pakai prompt template sendiri, framework 6-element tetap sama
- **Priority:** HIGH

#### `sesi-03-03-dashboard-infografis.html`
- **Current:** Dashboard threat level + infografis intel threat matrix
- **Gap:** 1 dashboard + 1 infografis, semua threat
- **Proposed:** **Major rework** — 4 variant dashboard + 4 variant infografis:
  - Dashboard: situational awareness / SAR ops / disaster relief / unit readiness
  - Infografis: intel threat / SAR results / bencana impact / doctrine compliance trend
- Section "YOUR MISSION" exercise: student pilih 1 variant untuk dikerjakan (tidak wajib threat)
- **Priority:** HIGH

#### `sesi-03-04-command-briefing.html`
- **Current:** 4-slide briefing package (exec dashboard, threat map, trend, recommendations) — threat scenario
- **Gap:** 1 briefing type only
- **Proposed:** **Major rework** — 4 variant command briefing package:
  1. Threat briefing (existing)
  2. OMSP briefing (SAR/bencana)
  3. Readiness briefing (pembinaan)
  4. Doctrine briefing (review doktrinal)
- Each variant dengan prompt lengkap untuk generate seluruh 4 slide
- **Priority:** HIGH

---

### Modul 04 — Strategic Reasoning

#### `sesi-04-01-deep-thinking.html`
- **Current:** Deep thinking CoT template dengan role "strategic military advisor / air defense ops"
- **Gap:** Single example, combat-oriented
- **Proposed:** Retain template. Tambah **3 contoh aplikasi CoT** di section "CoT Lintas Domain":
  1. **OMSP decision** (B1): deep thinking untuk SAR deployment strategy
  2. **Pembinaan decision** (C3): deep thinking untuk prioritisasi anggaran pemeliharaan
  3. **Doctrine decision** (D3): deep thinking untuk multi-platform interop doctrine
- **Priority:** MEDIUM

#### `sesi-04-02-coa-analysis.html`
- **Current:** COA comparison template dengan 5 kriteria terbobot, example combat COAs
- **Gap:** Example hanya combat
- **Proposed:** Retain template & kriteria (effectiveness, risk, cost, speed, flexibility — semua domain-agnostic). Tambah **3 mini-case COA comparison**:
  1. **SAR strategy** (B1): grid search vs probability-based vs tipoff-driven
  2. **Training approach** (C2): simulator-heavy vs field-heavy vs mixed
  3. **Doctrine rollout** (D1): big bang vs phased vs pilot unit
- **Priority:** MEDIUM

#### `sesi-04-03-risk-wargaming.html`
- **Current:** Red Team wargaming = simulate enemy response; MLR / MDR framing
- **Gap:** Combat-exclusive framing. Red Team = musuh saja.
- **Proposed:** **Major reframe** — Red Team diperluas jadi "**Disruption Team**" yang simulate berbagai sumber complications, bukan hanya musuh:
  - **Adversary complications** (existing Red Team): musuh dengan doctrine tertentu
  - **Environmental complications**: weather, terrain, darkness (untuk SAR / OMSP)
  - **Resource complications**: maintenance failure, personnel unavailability (untuk pembinaan)
  - **Institutional complications**: resistance to change, legal constraint (untuk doktrin)
- MLR / MDR tetap valid framing. Tambah 2 contoh wargaming lengkap: (1) SAR environmental wargame, (2) Doctrine transition institutional wargame
- **Priority:** HIGH

#### `sesi-04-04-decision-support.html`
- **Current:** Decision Support Package 4-part (situation, COA, risk, recommendation), context combat
- **Gap:** Template generic sudah OK, context combat-heavy
- **Proposed:** Retain template. Tambah **3 contoh DSP lengkap** sebagai appendix references:
  1. DSP for SAR decision (B1)
  2. DSP for resource allocation decision (C3)
  3. DSP for doctrine adoption decision (D1)
- Prompt master template ditulis agar domain-agnostic (no hardcoded "threat" terminology)
- **Priority:** MEDIUM

---

### Modul 05 — Capstone

**KEY DECISION:** Capstone di-restructure jadi **3 pathway** yang student pilih 1. Framework 4-phase (Intel Fusion → Visual Package → COA Wargaming → Decision Brief) tetap sama untuk ketiga pathway.

**Pathway A — GARUDA SHIELD** (existing, threat/reconnaissance)
**Pathway B — CENDRAWASIH RESCUE** (new, OMSP/SAR)
**Pathway C — IADS DOCTRINE REVIEW** (new, doktrin)

#### `sesi-05-01-intel-fusion.html`
- **Current:** Phase 1 — fusion 4 intel source for GARUDA SHIELD threat assessment
- **Gap:** Single pathway
- **Proposed:** Add tab selector pathway A/B/C:
  - **A (existing):** 4 intel sources → threat assessment
  - **B (new):** Weather + Radar track + Survivor probability + SAR asset availability → SAR priority assessment
  - **C (new):** NATO doctrine + Regional doctrine + Lessons learned + Policy papers → doctrine gap assessment
- Framework sama (extract → correlate → synthesize), konten source berbeda
- **Priority:** HIGH

#### `sesi-05-02-visual-package.html`
- **Current:** Dashboard + Threat Map + SITREP for GARUDA SHIELD
- **Gap:** Single pathway
- **Proposed:** 3 pathway variant visual package:
  - **A:** Threat dashboard + threat map + formal SITREP (existing)
  - **B:** SAR dashboard + search area map + SAR SITREP
  - **C:** Doctrine gap dashboard + comparison matrix + doctrine note draft
- **Priority:** HIGH

#### `sesi-05-03-coa-wargaming.html`
- **Current:** 3 COAs for deterrence vs reconnaissance threat
- **Gap:** Single pathway
- **Proposed:** 3 pathway variant COAs:
  - **A:** Assertive / Graduated / Diplomatic (existing deterrence options)
  - **B:** Grid search / Probability-based / Tipoff-driven (SAR strategy)
  - **C:** Big bang / Phased / Pilot unit (doctrine rollout)
- Wargaming framework (disruption team) sama untuk ketiga
- **Priority:** HIGH

#### `sesi-05-04-decision-brief.html`
- **Current:** 7-section commander decision brief for GARUDA SHIELD recommendation
- **Gap:** Single pathway
- **Proposed:** 3 pathway variant decision brief, 7-section struktur sama. Template prompt master diberikan 3 kali dengan placeholder A/B/C.
- **Priority:** HIGH

---

### Modul 06 — Multi-Tool Operations

#### `sesi-06-01-gemini-ecosystem.html`
- **Current:** 3 Gemini scenarios "vague" disebut tapi tidak detail, hands-on 20 min
- **Gap:** Contoh scenario tidak konkret ke 5 tugas pokok
- **Proposed:** Detail 3 scenario hands-on jadi eksplisit:
  1. **Hanud context:** Claude vs Gemini untuk threat assessment brief (existing default)
  2. **OMSP context:** Claude vs Gemini untuk SAR coordination brief (B1)
  3. **Doktrin context:** Claude vs Gemini untuk doctrine synthesis memo (D1)
- **Priority:** LOW

#### `sesi-06-02-notebooklm-deep-dive.html`
- **Current:** 4 use-case (doktrin digest, threat landscape, equipment assessment, exercise patterns). Doktrin sudah ada.
- **Gap:** Balance OK, tinggal refresh contoh biar explicit 5 tugas pokok
- **Proposed:** Tambah 1 use-case OMSP ("NotebookLM untuk compile best practice SAR multi-agency dari lessons learned regional") jadi total 5 use-case mapping 1:1 ke tugas pokok
- **Priority:** LOW

#### `sesi-06-03-gemini-visual-generation.html`
- **Current:** Imagen 4 + Canvas + Veo, framework prompt, 5 OPSEC checks
- **Gap:** Contoh visual generation belum domain-spesifik
- **Proposed:** 5 prompt template example yang ada diperluas jadi cover 5 tugas pokok:
  1. Infografis intel threat (existing)
  2. Infografis SAR progress
  3. Infografis unit readiness
  4. Infografis doctrine comparison
  5. Infografis gakkum incident
- **Priority:** LOW

#### `sesi-06-04-multi-tool-workflow.html`
- **Current:** Capstone scenario "briefing package UAV threat regional 30 menit"
- **Gap:** Single scenario, threat-focused
- **Proposed:** Retain scenario primary (UAV threat). Tambah **"Scenario Matrix" footnote** di awal:
  - Workflow (NotebookLM → Claude → Gemini → Package) berlaku untuk:
    - **Threat brief** (existing UAV regional)
    - **SAR coordination package** (B1)
    - **Doctrine synthesis package** (D1)
- 4 principles (Ground → Reason → Visualize → Human gate) universal
- Di section exercise: opsional bagi student pilih scenario alternatif
- **Priority:** MEDIUM

---

## 4. Implementation Checklist

Centang saat file sudah di-adjust sesuai panduan ini.

### Landing & Overview (7 files)
- [x] `index.html`
- [x] `modul-01-ai-fundamentals.html`
- [x] `modul-02-intelligence-analysis.html`
- [x] `modul-03-visual-intelligence.html`
- [x] `modul-04-strategic-reasoning.html`
- [x] `modul-05-capstone.html`
- [x] `modul-06-multi-tool-operations.html`

### Modul 01 — AI Fundamentals (4 files)
- [x] `sesi-01-01-demistifikasi-ai.html` *(LOW)*
- [x] `sesi-01-02-framework-risen.html` *(MEDIUM)*
- [x] `sesi-01-03-hands-on-prompt.html` *(MEDIUM)*
- [x] `sesi-01-04-etika-ai.html` *(LOW)*

### Modul 02 — Intelligence Analysis (4 files)
- [x] `sesi-02-01-deep-research.html` *(MEDIUM)*
- [x] `sesi-02-02-pattern-recognition.html` *(MEDIUM)*
- [x] `sesi-02-03-threat-assessment.html` *(HIGH)*
- [x] `sesi-02-04-multi-source-fusion.html` *(HIGH)*

### Modul 03 — Visual Intelligence (4 files)
- [x] `sesi-03-01-visual-principles.html` *(LOW)*
- [x] `sesi-03-02-sitrep-visual.html` *(HIGH)*
- [x] `sesi-03-03-dashboard-infografis.html` *(HIGH)*
- [x] `sesi-03-04-command-briefing.html` *(HIGH)*

### Modul 04 — Strategic Reasoning (4 files)
- [x] `sesi-04-01-deep-thinking.html` *(MEDIUM)*
- [x] `sesi-04-02-coa-analysis.html` *(MEDIUM)*
- [x] `sesi-04-03-risk-wargaming.html` *(HIGH)*
- [x] `sesi-04-04-decision-support.html` *(MEDIUM)*

### Modul 05 — Capstone (4 files)
- [x] `sesi-05-01-intel-fusion.html` *(HIGH)*
- [x] `sesi-05-02-visual-package.html` *(HIGH)*
- [x] `sesi-05-03-coa-wargaming.html` *(HIGH)*
- [x] `sesi-05-04-decision-brief.html` *(HIGH)*

### Modul 06 — Multi-Tool (4 files)
- [x] `sesi-06-01-gemini-ecosystem.html` *(LOW)*
- [x] `sesi-06-02-notebooklm-deep-dive.html` *(LOW)*
- [x] `sesi-06-03-gemini-visual-generation.html` *(LOW)*
- [x] `sesi-06-04-multi-tool-workflow.html` *(MEDIUM)*

**Total:** 31 files. Suggested order:
1. HIGH priority first (10 files) — biggest impact
2. MEDIUM (11 files) — contextual refresh
3. LOW (10 files) — polish & consistency

---

## 5. Framing Notes

### 5.1 OMP vs OMSP Tone Guide
| Aspect | OMP (Combat) | OMSP / Peacetime |
|--------|-------------|------------------|
| Tone | Kinetic, ROE-strict, adversarial | Humanitarian, coordinated, supportive |
| Time horizon | Minutes-hours | Hours-days-weeks |
| Decision authority | Commander-centric, chain-of-command tight | Multi-stakeholder, consensus-oriented |
| Success metric | Mission accomplishment vs adversary | Lives saved, damage mitigated, capability built |
| Language cue | "threat", "engage", "deter" | "coordinate", "support", "prioritize" |

### 5.2 Etika AI sebagai Benchmark Universal
Regardless of domain (combat atau OMSP atau pembinaan), aturan Sesi 1.4 berlaku:
- ✅ **Permissible:** analysis, synthesis, draft, visualization, scenario generation, decision support
- ❌ **Forbidden:** autonomous decision on use of force, autonomous triage (who lives/dies), autonomous legal determination

Saat menulis contoh di domain baru, explicit-kan batas ini. Contoh dalam SAR: AI boleh rekomendasi priority search area, tapi keputusan finasl alokasi aset rescue = human commander.

### 5.3 Cross-Reference Callout Tool-Comparison (Modul 06)
Pattern accordion indigo di 6 sesi (01-02, 02-01, 02-04, 03-02, 03-03, 04-01) tetap dipertahankan. Yang berubah hanya **content** callout: saat sesi di-rework untuk cover domain baru, callout tool-comparison harus ikut mencerminkan bagaimana tool Gemini/NotebookLM handle domain baru tsb.

### 5.4 Re-use Skenario Bank
Saat implementasi sesi tertentu, **ambil skenario dari Section 2 bank** dan adaptasi, bukan bikin skenario baru from scratch. Ini menjaga konsistensi cross-session — kalau student kerja di Capstone B (CENDRAWASIH RESCUE), mereka akan mengenali skenario dari sebelumnya di Sesi 2.4 (SAR Fusion) dan Sesi 3.2 (SAR SITREP).

### 5.5 OPSEC Review
Setiap kali tambah skenario baru, double-check Section 1.2 — generic callsigns, fictional locations di mana perlu, no real data sensitif.

---

## Next Steps

1. **Review oleh user:** baca Section 2 (Skenario Bank) — apakah 5 domain × 3-4 skenario sudah representatif? Ada yang mau ditambah/diubah?
2. **Pilih priority order:** default suggestion = HIGH → MEDIUM → LOW. User boleh reorder.
3. **Mulai implementasi sesi-per-sesi:** setiap sesi akan di-handle sebagai plan mode task terpisah, dengan dokumen ini sebagai reference context.
4. **Update checklist** di Section 4 setiap sesi selesai.
