# Portfolio README Rewrite — Design Spec

**Date:** 2026-06-07
**Status:** Approved by user

## Goal

Rewrite `README.md` so the repo reads as a portfolio case study (for recruiters/personal-site visitors), centered on the user's individual contribution as **팀장 / AI & Architecture** lead on the CareRing competition entry (공군창업경진대회, 2026), rather than as a generic startup pitch deck.

## Decisions (from brainstorming)

- **Format:** Rewrite `README.md` in place (no separate CASE_STUDY.md / no standalone webpage).
- **Framing:** Center on the user's individual contribution — designing the AI/voice analysis architecture and product concept, drawing on CMU CS background and prior emotion-analysis work at QCRI — within the team project context. Other team members credited in the team section as before.
- **Visuals:** Embed the 5 existing SVG figures in `figures/` (currently unreferenced anywhere in the repo): `market_size.svg`, `service_flow.svg`, `competitive_matrix.svg`, `tech_architecture.svg`, `roadmap.svg`. No new screenshot capture.
- **Tone:** Factual/portfolio register ("I designed...", "I led...") for the role section; descriptive register for product/market/team sections (not sales-pitch language).

## New README structure

1. **Header** — project name, one-liner, context line (공군창업경진대회 2026 · Team Lead, AI & Architecture)
2. **The problem** — 고독사 stats + market context; embeds `market_size.svg` (TAM/SAM/SOM) with caption
3. **The idea** — one-liner + 4-step flow; embeds `service_flow.svg` with caption
4. **My role: designing the AI/voice architecture** (new section) — explains the voice-health pipeline design (response latency, speech rate, pause frequency, emotion embeddings) and how it's grounded in the user's QCRI emotion-analysis work; embeds `tech_architecture.svg` with caption
5. **Product** — feature table + pricing tiers (trimmed from existing README)
6. **Market & competition** — TAM/SAM/SOM figures + differentiation vs 클로바 케어콜; embeds `competitive_matrix.svg` with caption
7. **Roadmap** — embeds `roadmap.svg` with caption
8. **Team** — kept from existing README, user's entry framed as 팀장
9. **Outcome / status** — submission context (공군창업경진대회), link to live demo (`demo/app.html`)

## Constraints

- Korean product terms/names stay in Korean (per project convention); narrative prose in English (portfolio audience).
- Reuse existing factual content (pricing, market figures, team bios, tech stack) — this is a reformat + visual upgrade, not new research.
- All 5 SVGs must get a one-line caption explaining what the figure shows.
- Keep the "Status" framing honest: this was a competition entry, not a shipped product.

## Out of scope

- No changes to `application_v1.md`, demo HTML, landing pages, or figures themselves.
- No new screenshots/images beyond the existing SVGs.
- No standalone portfolio webpage.
