# CareRing — Demo Screen Prompts

> Prompts for generating the CareRing guardian-facing web app demo screens.
> Style reference: Cloudflare dashboard — minimal, clean, data-forward.
> Default parent persona: 김순자 (age 74). Adjust as needed.

---

## Design Direction

- **Style**: Cloudflare-inspired — minimal, no decorative flourishes, data is the hero
- **Typography**: Clean sans-serif, strong hierarchy between labels and values
- **Colors**: Neutral base with semantic color for status (green = normal, amber = watch, red = alert)
- **Language**: Korean primary labels, English secondary/technical labels acceptable
- **Layout**: Card-based, generous whitespace, metric cards at top, charts below

---

## Core Screens

### 1. Guardian Dashboard

**Purpose**: Home view. At-a-glance wellness status for the parent, recent call activity, and trend summary.

**Key data to show**:
- Wellness status badge (e.g. 정상 범위 / 관심 필요 / 주의)
- Last call timestamp and duration
- Call streak counter (e.g. 22일 연속)
- 4 metric cards: avg response latency (s), avg speech rate (WPM), emotional score (/100), calls completed this month (e.g. 28/30)
- 14-day sparkline trend for emotional score
- Recent calls list (date, duration, score, status)

**Prompt**:
```
Generate the Guardian Dashboard screen for CareRing, an AI elder care calling platform.
Style: Cloudflare-inspired — minimal, clean, data-forward. No decorative elements.

Parent profile: 김순자, age 74.

Include:
- A wellness status badge showing 정상 범위 (green)
- Last call: today 10:24am, 8m 42s
- Call streak: 22 days
- 4 metric cards: avg response latency 1.8s, avg speech rate 112 WPM, emotional score 78/100, calls completed 28/30
- A 14-day sparkline chart of emotional score (values roughly 72–83, slight upward trend)
- A recent calls list showing the last 5 calls with date, duration, and score

Korean labels for all UI elements. Keep it clean and minimal.
```

---

### 2. Weekly Health Report

**Purpose**: The flagship feature. Shows the four core health indicators as charts for the past 7 days, plus an AI-generated narrative summary in Korean.

**Key data to show**:
- Response latency per call (line or bar chart, 7 days)
- Speech rate in WPM (line chart, 7 days)
- Pause frequency per call (bar chart, 7 days)
- Emotional embedding score (line chart, 7 days)
- Week-over-week comparison badge for each metric (e.g. ▲ 3% vs last week)
- AI-generated natural language summary paragraph in Korean

**Prompt**:
```
Generate the Weekly Health Report screen for CareRing, an AI elder care calling platform.
Style: Cloudflare-inspired — minimal, clean, data-forward.

Parent profile: 김순자 / Week: June 9–15, 2025.

Include:
- 4 charts arranged in a 2x2 grid:
  1. Response latency (avg seconds per call, values ~1.6–2.1s over 7 days)
  2. Speech rate in WPM (values ~105–118 WPM)
  3. Pause frequency (pauses per call, values ~3–7)
  4. Emotional score (values ~74–83 out of 100)
- Each chart has a week-over-week delta badge (e.g. ▲2% / ▼1%)
- Below the charts: an AI-generated Korean narrative summary paragraph, e.g.:
  "이번 주 순자님의 통화 패턴은 전반적으로 안정적이었습니다. 응답 속도와 발화 속도 모두 정상 범위를 유지하였으며, 감정 점수는 소폭 상승하여 긍정적인 변화를 보였습니다. 특히 목요일 통화에서 밝은 목소리와 활발한 대화가 관찰되었습니다."

Korean labels for all UI elements.
```

---

### 3. Call Settings

**Purpose**: Guardian configures the call schedule, preferred time window, and the parent's interest/personality profile that the AI uses for personalization.

**Key data to show**:
- Call frequency selector (매일 / 주 3회 / 주 1회)
- Preferred call time window (e.g. 오전 9시–11시)
- Parent profile: name, age, phone number (유선전화 or 휴대폰)
- Interest tags (e.g. 뜨개질, 트로트, 손주, 드라마)
- Health notes free-text field
- Save / update button

**Prompt**:
```
Generate the Call Settings screen for CareRing, an AI elder care calling platform.
Style: Cloudflare-inspired — minimal, clean, form-based.

Show a settings page with two sections:

Section 1 — Call schedule:
- Frequency toggle: 매일 (selected), 주 3회, 주 1회
- Preferred time window: 오전 9시 to 오전 11시 (shown as a time range selector or dropdown)

Section 2 — Parent profile (used for AI personalization):
- Name: 김순자
- Age: 74
- Phone: 유선전화 02-XXX-XXXX
- Interest tags (pill-style, editable): 뜨개질, 트로트, 손주, 드라마
- Health notes text area (placeholder: 관절염으로 거동이 불편하신 편입니다)

Include a Save changes button at the bottom.
Korean labels. Clean card layout per section.
```

---

### 4. Single Call Detail

**Purpose**: Drill into one specific call. Shows quantitative metrics, an emotional arc across the call timeline, an annotated waveform, and a short transcript excerpt.

**Key data to show**:
- Top metrics bar: call date/time, duration, avg response latency, speech rate, emotion score
- Emotional arc line chart (x = time in minutes, y = emotion score 0–100)
- Simplified waveform (bar chart) with 2–3 annotated moments
- Short transcript excerpt (3–4 turns of AI + 순자님 dialogue)

**Prompt**:
```
Generate the Single Call Detail screen for CareRing, an AI elder care calling platform.
Style: Cloudflare-inspired — minimal, clean, data-forward.

Call details: June 13, 2025 / 10:24am / Duration: 8m 42s / Status: Completed.

Include:
- A top metrics bar with 4 values: duration 8:42, avg response latency 1.9s, speech rate 108 WPM, emotion score 81/100
- An emotional arc line chart from 0:00 to 8:42, showing score starting around 72, rising to 85 around minute 4, then settling at 78. Mark the peak with a dot.
- A waveform visualization (simplified bar chart) with 3 annotated moments:
  - 2:10 — 밝은 목소리
  - 5:30 — 약간 피로감
  - 7:45 — 웃음
- A transcript excerpt showing 3–4 turns:
  AI: "오늘 아침에 밥은 드셨어요, 순자님?"
  순자님: "응, 죽 한 그릇 먹었어. 입맛이 별로 없어서."
  AI: "그러셨군요. 요즘 날씨가 더워서 그런가 봐요. 뜨개질은 요즘도 하고 계세요?"
  순자님: "응, 손녀 것 만들고 있어. 거의 다 됐어."

Korean labels.
```

---

## Supporting Screens

### 5. Emergency Alert

**Purpose**: Full-screen alert shown to the guardian when a distress keyword is detected mid-call. Urgency and one-tap action are the priority.

**Key data to show**:
- Alert severity banner (danger state)
- Detected keyword highlighted in transcript snippet
- Call timestamp and minute-mark of trigger
- Primary CTA: 지금 전화하기
- Secondary CTA: 녹음 듣기

**Prompt**:
```
Generate the Emergency Alert screen for CareRing, an AI elder care calling platform.
Style: Cloudflare-inspired base, but with a clear danger/urgency state. Red is appropriate here.

Alert triggered during call with 김순자 on June 13, 2025 at 10:31am.
Trigger point: 6m 14s into the call.
Detected keyword: 넘어졌어

Include:
- A prominent red alert banner at the top: "긴급 상황이 감지되었습니다"
- The flagged transcript snippet showing context around the keyword, with 넘어졌어 highlighted in red
- Call metadata: date, time, duration at point of trigger
- A large primary button: 지금 전화하기 (with phone icon)
- A smaller secondary button: 녹음 듣기
- A dismiss/false alarm link at the bottom: 오탐으로 처리하기

The alert should feel urgent but not chaotic. Red used purposefully, rest of layout stays clean.
Korean labels.
```

---

### 6. 30-Day Trend Overview

**Purpose**: Monthly long-view for the guardian. Shows whether the parent's indicators are stable, improving, or declining over 4 weeks. Useful for family sharing and care team handoffs.

**Key data to show**:
- Call completion rate (e.g. 28/30, shown as progress bar or donut)
- Four small trend charts, one per indicator, each showing 4-week weekly averages
- A notable week callout card (e.g. week with elevated pause frequency)
- Month summary badge (e.g. 전반적으로 양호)

**Prompt**:
```
Generate the 30-Day Trend Overview screen for CareRing, an AI elder care calling platform.
Style: Cloudflare-inspired — minimal, clean, data-forward.

Parent: 김순자 / Month: June 2025.

Include:
- Call completion rate: 28/30 shown as a progress bar with label (93.3%)
- Month summary badge: 전반적으로 양호 (green)
- Four small weekly trend charts (4 data points each, one per week):
  1. Avg response latency: 2.1 → 1.9 → 1.8 → 1.8s (improving)
  2. Avg speech rate: 108 → 110 → 112 → 111 WPM (stable)
  3. Avg pause frequency: 6 → 5 → 7 → 5 pauses/call (watch week 3)
  4. Avg emotional score: 74 → 76 → 73 → 78 (slight dip week 3, recovery week 4)
- A notable week callout card for week 3: "3주차에 멈춤 빈도가 소폭 상승하였으나, 4주차에 정상 범위로 회복되었습니다."

Korean labels.
```

---

## Customization Notes

| Variable | Default | How to change |
|---|---|---|
| Parent name | 김순자 | Replace in prompt |
| Parent age | 74 | Replace in prompt |
| Phone type | 유선전화 | Change to 휴대폰 if needed |
| Date range | June 2025 | Replace throughout |
| Language | Korean primary | Specify "English only" or "bilingual" |
| Device frame | Browser/web | Add "show as iPhone 15 screen" |
| Color accent | System default | Specify e.g. "use teal as accent color" |