# Portfolio README Rewrite Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Replace `README.md` with a portfolio case-study version centered on the user's role as 팀장 / AI & Architecture lead, embedding the 5 existing SVG figures from `figures/` (currently unreferenced anywhere in the repo).

**Architecture:** Single-file content rewrite. No code changes, no new assets — `figures/*.svg` already exist and just need to be referenced with `<img>` tags and captions. This is a content task, so "tests" are verification that every embedded asset path resolves and the final markdown renders cleanly.

**Tech Stack:** Markdown, existing SVG assets in `figures/`.

---

### Task 1: Verify all figure assets referenced by the new README exist

**Files:**
- Read-only check against: `figures/market_size.svg`, `figures/service_flow.svg`, `figures/tech_architecture.svg`, `figures/competitive_matrix.svg`, `figures/roadmap.svg`

- [ ] **Step 1: Confirm each SVG file exists at the expected path**

Run:
```bash
ls -1 figures/market_size.svg figures/service_flow.svg figures/tech_architecture.svg figures/competitive_matrix.svg figures/roadmap.svg
```
Expected: all five paths printed with no "No such file" errors. (These were confirmed present during brainstorming via `find` — this step re-confirms immediately before the rewrite so the new README never references a missing asset.)

---

### Task 2: Replace README.md with the case-study version

**Files:**
- Modify: `README.md` (full replacement)

- [ ] **Step 1: Write the new README.md content**

Overwrite `README.md` with exactly this content:

```markdown
# CareRing (케어링)

> AI가 매일 어르신께 전화하고, 가족에게 건강 리포트를 보내드립니다.

**Competition entry — 공군창업경진대회 (Air Force Startup Competition), 2026**
**My role: 팀장 · AI & Architecture** — I led the team and designed the AI call / voice-analysis architecture.

CareRing is an AI-powered wellness call platform that places regular phone calls to elderly parents on behalf of their adult children, analyzes voice and speech patterns for health signals, and delivers weekly health reports back to the family.

---

## The problem

Korea entered super-aged society in 2025 — over 20% of the population is now 65+. More than 2.2 million elderly people live alone, and roughly 3,600 lonely deaths (고독사) occur each year, with an average of 4.2 days passing before discovery. Existing solutions are either government-run programs with no family visibility, or expensive, device-dependent products most families won't adopt.

<p align="center"><img src="figures/market_size.svg" width="640" alt="TAM/SAM/SOM market size diagram"></p>

*Domestic digital-care market sizing: TAM ₩1.2T → SAM ₩360B (households with an elderly parent living alone, guardians aged 40–60) → SOM ₩12B (50,000 households within 3 years).*

---

## The idea

**One-liner:** AI가 매일 어르신께 전화하고, 가족에게 건강 리포트를 보내드립니다.
*(The AI calls your elderly parent every day and sends your family a health report.)*

The guardian sets a call schedule, the AI calls the parent on any existing phone (no app or device needed on their end), each call is analyzed for health/emotional signals, and the guardian receives a plain-language report.

<p align="center"><img src="figures/service_flow.svg" width="640" alt="Service flow: guardian setup, AI call, voice analysis, report"></p>

*Four-step service loop: 보호자 설정 (guardian setup) → AI 발신 통화 (AI places the call) → 음성 분석 (voice analysis) → 리포트 전송 (report delivered).*

---

## My role: designing the AI / voice architecture

As team lead, I owned the technical core of CareRing — the part that turns "a phone call" into a health signal. This built directly on my prior work building an emotion-analysis system for video interviews at QCRI (Qatar Computing Research Institute), adapted here from video to voice-only, real-time conversation.

I designed:
- **The voice health pipeline** — extracting physical indicators (response latency, speech rate in WPM, pause frequency) and emotional/cognitive trend signals (embedding-based mood tracking) from each call, without relying on any wearable or app
- **The AI call engine** — real-time Korean conversation via LLM + TTS/STT, tuned to keep an elderly speaker comfortable and talking naturally rather than answering a survey
- **The escalation path** — keyword-based emergency detection mid-call, triggering an immediate push alert to the guardian
- **The "wellness, not diagnosis" framing** — a deliberate constraint: the system tracks *trends* and flags *changes*, and avoids medical/diagnostic language, both for regulatory reasons and to keep the product trustworthy rather than alarming

<p align="center"><img src="figures/tech_architecture.svg" width="640" alt="Three-layer technical architecture: client, backend, AI/data"></p>

*Three-layer architecture: Guardian app (client) → call/report backend → AI call engine and voice-analysis pipeline.*

---

## Product

| Feature | Description |
|---|---|
| AI 발신 통화 | Scheduled outbound calls in natural Korean conversation |
| 음성 건강 분석 | Physical + emotional trend tracking across 30/90-day windows |
| 주간 리포트 | Plain-language weekly report delivered to the guardian |
| 응급 키워드 감지 | Instant push alert when distress keywords are detected mid-call |
| 수신 통화 (Premium) | Elderly parent can call the AI anytime |
| 가족 공유 | Share reports with up to 5 family members |

| Plan | Price | Includes |
|---|---|---|
| 베이직 | ₩9,900/mo | 주 3회 AI 통화, 주간 텍스트 요약 |
| 스탠다드 | ₩19,900/mo | 매일 통화, 그래프 리포트, 이상 징후 알림 |
| 프리미엄 | ₩34,900/mo | 매일 통화 + 어르신 발신 무제한, 월간 PDF, 5인 공유 |

A working demo of the guardian-facing app is in [`demo/app.html`](demo/app.html) — three tabs (홈 / 분석 / 통화 기록) with live charts rendered from sample data, no external dependencies.

---

## Market & competition

- **TAM** ₩1.2T — domestic digital-care market
- **SAM** ₩360B — households with an elderly parent living alone, guardian aged 40–60
- **SOM** ₩12B/yr — 50,000 households within 3 years

The closest existing product is 클로바 케어콜 (Naver/LINE) — but it's B2G only: municipalities choose which elderly residents receive calls, and families get no visibility at all. CareRing is B2C: families sign up directly and are the ones who receive the reports.

<p align="center"><img src="figures/competitive_matrix.svg" width="640" alt="Competitive positioning matrix: family report access vs B2C/B2G"></p>

*Positioning matrix — access model (B2G vs. B2C) × whether the family receives a report. CareRing is the only B2C option with direct family reporting.*

---

## Roadmap

<p align="center"><img src="figures/roadmap.svg" width="720" alt="Four-phase roadmap from MVP to global expansion"></p>

*Planned path: MVP (0–6mo, 200-household beta) → launch (6–12mo) → B2B expansion (1–2yr) → global (3yr).*

---

## Team

| Role | Name | Background |
|---|---|---|
| 팀장 / AI & Architecture | 정의서 | CMU CS; AI researcher at QCRI; built emotion-analysis system for video interviews |
| Web Platform | 최지현 | SW engineer; national R&D government website development |
| Security Architecture | 조성윤 | 정보보호병; 정보보안기사 certified; prior security-firm experience |
| App & Server | 홍준서 | Fullstack SW engineer; app, web, and server real-service deployment experience |

---

## Status

This was our team's entry to the **공군창업경진대회 (Air Force Startup Competition), 2026** — written and designed during my military service. The repo contains the full application document, supporting figures, and a working front-end demo of the guardian app and marketing site.

*Positioning line from the application: "내가 매일 전화드릴 수 없을 때, 케어링이 대신합니다." — "When I can't call every day, CareRing calls for me."*
```

- [ ] **Step 2: Verify every embedded image path resolves**

Run:
```bash
grep -o 'src="figures/[^"]*"' README.md | sed 's/src="//;s/"$//' | while read -r f; do test -f "$f" && echo "OK: $f" || echo "MISSING: $f"; done
```
Expected: five lines, all prefixed `OK:` — one per `<img src="figures/...">` reference (`market_size.svg`, `service_flow.svg`, `tech_architecture.svg`, `competitive_matrix.svg`, `roadmap.svg`). No `MISSING:` lines.

- [ ] **Step 3: Verify the demo link path resolves**

Run:
```bash
test -f demo/app.html && echo "OK: demo/app.html" || echo "MISSING: demo/app.html"
```
Expected: `OK: demo/app.html`

- [ ] **Step 4: Spot-check rendered structure**

Run:
```bash
grep -c '^## ' README.md
```
Expected: `8` — matches the eight `##` sections in the content above: The problem, The idea, My role: designing the AI / voice architecture, Product, Market & competition, Roadmap, Team, Status.

- [ ] **Step 5: Commit**

```bash
git add README.md
git commit -m "$(cat <<'EOF'
docs: rewrite README as portfolio case study

Reframe the project README around the team-lead/AI-architecture role
(per the brainstormed spec at docs/superpowers/specs/2026-06-07-portfolio-readme-design.md)
and embed the five SVG figures from figures/, which previously existed
but were never referenced anywhere in the repo.
EOF
)"
```
Expected: commit created on `master` with `README.md` staged and committed; `git status` shows a clean tree for `README.md`.

---

## Self-review notes (for the implementer)

- **Spec coverage:** All 9 structure items from the spec (`docs/superpowers/specs/2026-06-07-portfolio-readme-design.md`) map onto the `##`/`#` sections in the new README content above — header, problem (+market_size.svg), idea (+service_flow.svg), my role (+tech_architecture.svg), product, market & competition (+competitive_matrix.svg), roadmap (+roadmap.svg), team, status.
- **Visual scope:** Exactly the 5 approved SVGs are embedded — no new screenshots, matching the "Embed existing SVG figures only" decision.
- **Tone:** Role section uses first-person factual register ("I designed...", "I owned..."); other sections stay descriptive, matching the spec's tone constraint.
- **Out of scope respected:** No edits to `application_v1.md`, demo HTML, landing pages, or the SVGs themselves.
