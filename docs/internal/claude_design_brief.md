# CareRing — Claude Design Brief

## What We Are Building

CareRing (케어링) is a B2C SaaS mobile/web app for adult children (guardians, ages 40–60) whose elderly parents live alone. The service makes daily AI phone calls to the elderly parent, analyzes their voice for health and emotional signals, and sends structured health reports to the guardian.

The design system needs two surfaces:
1. **Guardian App** — the primary product interface where guardians monitor their parent's health trends, view call history, and manage settings. Mobile-first, also works on desktop.
2. **Marketing Landing Page** — public-facing page to explain the service and convert visitors to subscribers.

Design direction: clean, trustworthy, medical-adjacent but warm. Light mode primary. Think Linear or Cloudflare dashboard meets healthcare. Strong data hierarchy — numbers and trends are the core content. Korean language throughout.

Target feel: a real SaaS product a busy 50-year-old would trust with their parent's health data. Not a prototype. Not AI-generated looking.

---

## Screen Inventory

### Guardian App — Core Tabs (SPA, 3 tabs)

#### Tab 1: 홈 (Home / Dashboard)
- Parent health status card: parent name, age, status badge (정상 / 관심 / 주의)
- 4 KPI metric tiles in a grid:
  - Response latency (seconds) — lower = better
  - Speech rate (WPM)
  - Emotion score (/100)
  - Monthly call completion rate (%)
  - Each tile shows current value + delta vs last week (up/down/neutral indicator)
- 14-day emotion trend sparkline chart
- Recent calls list: date/time, duration, emotion score badge, status tag

#### Tab 2: 분석 (Analysis)
- Period switcher: 이번 주 / 이번 달 / 3개월 — all charts update on switch
- 4 metric charts:
  - Emotion score — line chart
  - Response latency — line chart
  - Speech rate — line chart
  - Pause frequency — bar chart
- AI insight text summary below charts (natural language paragraph)

#### Tab 3: 통화기록 (Call History)
- Table: date/time, duration, emotion score badge, status (정상 / 관심 / 주의 / 미연결), link to call detail

---

### Guardian App — Detail Screens

#### Call Detail
- Emotion arc line chart (x = time within call, y = emotion score, 0–100)
- Waveform bar chart with annotated segments (highlighted keyword moments)
- Conversation transcript excerpts with timestamps

#### Weekly Report
- 4 metric charts (7-day bar or line, one per metric)
- Week-over-week delta summary row
- AI narrative summary paragraph

#### 30-Day Trend
- Call completion bar chart (4 weeks side by side)
- 4 mini sparklines (one per metric, compact)
- Auto-highlighted anomaly callout block

#### Emergency Alert
- Full-screen red/urgent state
- Trigger keyword excerpt from transcript
- Two CTAs: 바로 전화하기 (call now), 알림 확인 (acknowledge)

#### Call Settings
- Call schedule form: frequency selector, time slot picker
- Parent profile fields: name, age, phone number (landline or mobile), address
- Interest tags (topics for AI conversation)
- Health notes text area

---

### Onboarding Flow (6 screens)

1. **Welcome** — value prop, single CTA: 시작하기
2. **Account Setup** — guardian name, email, password
3. **Parent Profile** — parent name, age, phone number, relationship tag
4. **Call Schedule** — frequency picker (3x/week or daily), preferred time slot, preview of first call date
5. **Plan Selection** — 3 pricing cards (베이직 ₩9,900 / 스탠다드 ₩19,900 / 프리미엄 ₩34,900), select + pay
6. **Success / First Call Confirmation** — confirmation state, countdown to first call, invite family CTA (premium)

---

### Notification States (push alerts)

- Anomaly detected: metric name + delta value, view detail CTA
- Weekly report ready: summary snippet, open report CTA
- Missed call: reason (no answer), retry CTA

---

### Additional Screens

#### Family Sharing (Premium)
- Member list: primary guardian + up to 4 additional members
- Invite via phone or email
- Permission level per member (view-only vs full access)

#### Billing / Subscription
- Current plan badge, renewal date, monthly price
- Usage this month: calls made / calls scheduled
- Upgrade / downgrade CTA
- Payment method display

#### Inbound Call Log Entry (Premium)
- Triggered when elderly parent initiates a call to the AI
- Visual indicator in feed: "어머니께서 전화를 거셨습니다"
- Auto-adds call log entry with mini summary card

#### Account / Settings
- Guardian profile edit
- Notification preferences (push, SMS, email toggles)
- Language / timezone
- Danger zone: cancel subscription, delete account

---

### Marketing Landing Page

Sections in order:
1. Hero — headline, subheadline, live mini-dashboard preview widget, CTA button
2. Stats strip — market numbers (고독사 3,600건/년, 독거노인 220만명, etc.)
3. How it works — 4-step flow: 보호자 설정 → AI 발신 → 음성 분석 → 리포트 전송
4. Feature grid — key capabilities with icons
5. Competitor comparison table — CareRing vs 클로바 케어콜 vs 효돌 vs KT/SKT
6. Pricing cards — 3 tiers
7. Team section — 4 members with role and background
8. Footer with CTA

---

## Chart Types Summary

| Chart | Screen |
|-------|--------|
| Line chart (time series) | Emotion score trend — 홈, 분석, weekly report |
| Bar chart | Pause frequency — 분석 |
| Multi-series line | All 4 metrics — 분석 tab |
| Emotion arc line | Call detail |
| Waveform bar | Call detail |
| Mini sparklines | 30-day trend |
| KPI tile with delta badge | 홈 tab, weekly report |
| Completion % bar | 홈 KPI tile |
| Grouped bar chart | 30-day call completion (4 weeks) |

---

## Personas

- **Guardian:** 정의서, 38세, lives in Seoul, parents in 강북구. Uses app daily on mobile (iPhone).
- **Elderly parent:** 김순자, 74세, lives alone, uses landline 02-XXX-XXXX. Does not use smartphone.

---

## Pricing

| Plan | Price | Calls | Features |
|------|-------|-------|---------|
| 베이직 | ₩9,900/mo | 3x/week | Weekly text summary |
| 스탠다드 | ₩19,900/mo | Daily | Graph reports, anomaly push alerts |
| 프리미엄 | ₩34,900/mo | Daily + unlimited inbound | Monthly PDF report, 5-person family sharing |
