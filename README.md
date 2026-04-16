# CareRing (케어링)

> AI가 매일 어르신께 전화하고, 가족에게 건강 리포트를 보내드립니다.

**CareRing** is an AI-powered wellness call platform that makes regular phone calls to elderly parents on behalf of their adult children, analyzes voice and speech patterns for health signals, and delivers weekly health reports to the family.

---

## The Problem

Korea entered super-aged society in 2025 (20%+ of the population over 65). Over 2.2 million elderly people live alone, and roughly 3,600 lonely deaths (고독사) occur each year — with an average of 4.2 days before discovery. Yet existing solutions are either locked behind government programs (with no family visibility) or too expensive and device-dependent for most families.

---

## How It Works

```
보호자 설정              AI 발신 전화             음성 분석              리포트 전송
Guardian sets  →  AI calls elderly  →  Voice health  →  Weekly report
call schedule      parent (any phone)     analysis         to guardian
```

1. The guardian sets call frequency and preferred time window in the app
2. The AI calls the elderly parent on any existing phone — no device needed
3. Each call is analyzed for physical indicators (response latency, speech rate, pause frequency) and emotional/cognitive trends
4. The guardian receives a weekly natural-language health report

---

## Key Features

| Feature | Description |
|---|---|
| AI 발신 통화 | Scheduled outbound calls in natural Korean conversation |
| 음성 건강 분석 | Physical + emotional trend tracking across 30/90-day windows |
| 주간 리포트 | Plain-language weekly report delivered to guardian |
| 응급 키워드 감지 | Instant push alert when distress keywords are detected mid-call |
| 수신 통화 (Premium) | Elderly parent can call the AI anytime |
| 가족 공유 | Share reports with up to 5 family members |

---

## Pricing

| Plan | Price | Includes |
|---|---|---|
| 베이직 | ₩9,900/mo | 주 3회 AI 통화, 주간 텍스트 요약 |
| 스탠다드 | ₩19,900/mo | 매일 통화, 그래프 리포트, 이상 징후 알림 |
| 프리미엄 | ₩34,900/mo | 매일 통화 + 어르신 발신 무제한, 월간 PDF, 5인 공유 |

---

## Technology

- **AI Call Engine**: LLM (GPT-4o / Claude API) + TTS/STT for real-time Korean conversation
- **Voice Health Pipeline**: Response latency, speech rate (WPM), pause frequency, emotional embedding vectors
- **Report Generation**: LLM-generated natural language summaries — wellness framing, no medical diagnostic language
- **Security**: End-to-end voice data encryption, 개인정보보호법 compliant by design

---

## Market

- **TAM**: ₩1.2T (domestic digital care market)
- **SAM**: ₩360B (households with elderly solo-living parent, ages 40–60)
- **SOM**: 50,000 households in 3 years → ~₩12B annual revenue

**Key differentiator vs. 클로바 케어콜 (Naver/LINE):** CareRing is B2C — families sign up directly and receive reports. Clova Care Call is B2G only (municipalities choose recipients; families get no reports).

---

## Team

| Role | Name | Background |
|---|---|---|
| 팀장 / AI & Architecture | 정의서 | CMU CS; AI researcher at QCRI; built emotion analysis system for video interviews |
| Web Platform | 최지현 | SW engineer; national R&D government website development |
| Security Architecture | 조성윤 | 정보보호병; 정보보안기사 certified; prior security firm experience |
| App & Server | 홍준서 | Fullstack SW engineer; app, web, and server real-service deployment experience |

---

## Status

This project was submitted to the **공군창업경진대회 (Air Force Startup Competition)** — 2026.

---

*Positioning: "내가 매일 전화드릴 수 없을 때, 케어링이 대신합니다."*
