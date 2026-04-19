# Khon Dek (คนเด็ก) — The "I'm Okay" Check-In App

> One tap to say "I'm alive and well" every morning. Radical simplicity for elderly Thais living alone, with peace of mind built for the whole family.

## Overview

Thailand is aging at speed. Over 20% of the population will be 60+ by 2030, and millions of elderly live in separate households from their adult children who work in the city. The daily phone call to check "are you okay?" is a source of anxiety for both sides: the elder feels pressure to answer promptly; the adult child worries if the call goes unanswered. Khon Dek (literally "child person" — the affectionate Thai term for elders) solves this with radical simplicity: one button, one second, daily reassurance. Done properly, it could be the go-to elder safety app for Thai families the way no existing app has managed to capture this market.

The app is positioned between pure button-check-in apps and full medical alert systems — cheaper and simpler than Life Alert, more intentional and culturally Thai than global competitors like I Am Fine. The Thai-language-first interface and voice check-in feature make it genuinely accessible to elderly users who cannot read or navigate a smartphone.

## Core Problem

The daily "are you okay?" phone call is a broken experience for Thai families separated by geography. Adult children living in Bangkok or working abroad call aging parents in Isan or the north every morning — missing a call triggers immediate panic, and calling too late means anxiety has already built up. There is no middle ground: the parent either answers (reassurance) or doesn't (crisis). Current workarounds are LINE group chats with read receipts (dismissive and awkward for elders) or relying on neighbors to physically check in (unreliable and undignified).

## Target Users

- **Primary:** Thai elderly aged 65+ living alone or with a spouse, adult children living in a different city
- **Secondary:** Adult children (25-45) supporting aging parents remotely, caregivers managing multiple elderly family members
- **Niche:** Thai diaspora families — adult children abroad who can't call daily but need a reliable signal when something is wrong

## Feature List

### Must Have (MVP)
- **One-Tap Morning Check-In:** Big friendly button displaying "ตอนนี้สบายดี" (I'm doing well). Tap once, done in under 3 seconds. Configurable check-in window (e.g., 7:00 AM - 10:00 AM). No scrolling, no menus, no navigation.
- **Missed Check-In Alerts:** If the window closes without a tap, immediately notify all family circle members via push notification simultaneously — no single person carrying the mental load of responsibility.
- **Family Circle (up to 8 members):** Add family members by phone number. Each receives alerts independently. Distributed alert model prevents caregiver burnout.
- **"All Clear" Notification:** When elder checks in, family members get a calm "Mom checked in at 8:15 AM" notification. No fanfare.

### Should Have (v1.1)
- **Voice Check-In Option:** Long-press (3 seconds) records a 5-second voice note ("ลูกสาวนี่ แม่สบายดีนะ"). AI voice detection confirms it is a human voice (not silence or accidental sound). Eliminates button-pressing entirely for users with tremor or vision issues.
- **Weekly Reassurance Report:** Every Sunday, family circle receives a calm summary: "Mom checked in 7/7 days. Average check-in time: 8:15 AM. Longest streak: 23 days." Delivered as a LINE message or push notification — no app required for recipients.
- **SOS Emergency Button:** Same screen as check-in. Long-hold (5 seconds) triggers simultaneous calls to the nearest family member AND a designated emergency contact. Visual countdown with haptic feedback before call fires.

### Nice to Have (future)
- Integration with Thai hospital systems for medical alert context
- "Wellness score" based on check-in consistency trends
- "Daily prompt" call option — app calls the elder automatically and they pick up to confirm (voice-only, no app needed)

## Tech Stack

### Frontend
- **Framework:** Flutter (Android-first, iOS after)
- **Language:** Dart
- **Key libraries:**
  - `flutter_local_notifications` — daily reminders + missed check-in alerts
  - `shared_preferences` — local elder settings storage
  - `sqflite` — local check-in history (offline-first)
  - `dio` — API calls to backend
  - `opus` / `flutter_sound` — voice recording for voice check-in
  - `provider` — state management (simple, minimal)

### Backend
- **Framework:** FastAPI (Python)
- **Language:** Python 3.11
- **Database:** PostgreSQL (family circles, check-in logs, user accounts)
- **Auth:** Phone number OTP verification (via Thai SMS gateway — Twilio or a local provider like ClickSend or DigiText)
- **Hosting:** Google Cloud Run or AWS Lambda (serverless scales well for this workload)

### AI / ML
- **Voice validation model:** Small on-device model (TensorFlow Lite) to distinguish human voice from silence/noise. Trained on Thai elder voice samples. No server round-trip needed for the voice check-in confirmation.
- **Weekly report generation:** Simple template-based generation — no LLM needed.

### Infrastructure
- **Cloud provider:** Google Cloud (Firebase Cloud Messaging for push notifications, Cloud Run for API)
- **SMS provider:** Thai SMS gateway for OTP (ClickSend or DigiText have good Thailand coverage)
- **Analytics:** Firebase Analytics (track check-in completion rates, missed windows, SOS usage)

## Monetisation

### Model
Freemium with family circle as the core value driver.

### Pricing Tiers
| Tier | Price | Features |
|------|-------|---------|
| Free | 0 THB | 1 elder + 3 family members, daily check-in, missed notification, basic "all clear" |
| Pro | 99 THB/month | Unlimited family circle, voice check-in, weekly report, priority support |
| Family Pack | 199 THB/month | Up to 3 elders under one family account, Pro features for all |

### Revenue Projection
Comparable apps (AllsOK subscription ~300-500 THB/year, Life Alert hardware ~5,000+ THB/month). At 99 THB/month with 50,000 active Pro users: 4.95M THB/month revenue. The addressable market in Thailand: ~3-4 million elderly living alone, targeting the 10% most digitally active families = 300-400K potential users. Realistic 3-year target: 100K Pro subscribers = ~10M THB/month.

## User Acquisition

### Channels
1. **Facebook Ads (Thai language):** Target adult children aged 30-50 in Bangkok, Chiang Mai, Khon Kaen with children aged 65+ parents in outer provinces. Creative: emotional video of daughter receiving mom's morning check-in. Cost: ~15-30 THB/click.
2. **LINE Official Account:** Publish wellness tips, elderly care content. Cross-promote through retirement communities and senior centers in Bangkok condos.
3. **Doctor/clinic referrals:** Partner with geriatric clinics and hospitals. Doctor recommends app after elderly patient assessment.
4. **Death notification testimonials:** Real stories shared by families (with permission) who caught an emergency in time.

### Launch Strategy
1. **Soft launch (Month 1):** Recruit 50 families from personal networks. Get feedback on UI friction, voice check-in accuracy, alert timing.
2. **Beta group (Month 2):** Expand to 500 families. Focus on drop-off analysis — who stops checking in and why.
3. **Public launch (Month 3):** App Store + Google Play. Facebook campaign targeting Thai provinces with highest elderly-alone rates (Isan: Khon Kaen, Nakhon Ratchasima, Udon Thani).
4. **Partnership (Month 6+):** Approach Bangkok Metropolitan Administration and Ministry of Public Health for elderly welfare program integration.

### Viral Mechanics
- Family circle invitation is the core loop — each elder naturally pulls in 3-5 family members who then become potential marketers
- Weekly report shared in family LINE groups (auto-generated image card, not a screenshot)

## Competitors

> Researched via Google Play, App Store, and competitor websites on April 19, 2026.

| App | Platform | Strengths | Weaknesses | Price | Downloads |
|-----|----------|-----------|------------|-------|-----------|
| **I Am Fine** (iamfine.app) | iOS/Android | Automatic motion-based check-in (step counter), no button needed, 28 languages, free, email alerts | Not Thai-focused, no voice check-in, no SOS, very US/Western-centric UX | Free | Not disclosed |
| **Circle Alert** (circlealert.com) | iOS/Android | Strong medical emergency focus, falls/mental health coverage, US press coverage, 100K+ check-ins completed | Complex feature set, no Thai language, no voice option, confusing UX for elderly, subscription required | Free trial, then ~$10-15/month estimated | 100K+ check-ins |
| **AllsOK** (Google Play) | Android | WhatsApp alert integration, very simple setup, 30-day free trial | Button-based (not automatic), no voice check-in, no SOS, no Thai language | ~500 THB/year subscription | 500+ |
| **Circle Alert Wellness Check In** (App Store) | iOS | Family circle monitoring, customizable check-in duration, medical alert focus | Complex UI, no Thai language, generic Western design | Not disclosed | Not disclosed |
| **Life Alert Thailand** | Hardware + App | Brand recognition, 24/7 monitoring center, hospital dispatch | Very expensive (5,000+ THB/month), hardware required, clinical feel, no daily check-in concept | ~5,000+ THB/month | Unknown |

## Unique Angle

Most check-in apps fall into two camps: **button-based** (AllsOK, Circle Alert) — which elderly users forget or find tedious — or **sensor-based** (I Am Fine) — which is passive to the point of feeling uncaring. Khon Dek sits in a third category: **intentional but minimal effort**. The elder actively confirms their wellbeing, which preserves dignity and purpose, but the interaction is so simple (one tap, or one voice note) that cognitive load is near zero.

The specific Thai differentiators:
- Thai-language-first interface, not an afterthought translation
- Voice check-in for illiterate elders or those with vision impairment
- Thai cultural concept embedded in the name — "คนเด็ก" is how Thai children affectionately refer to their elders
- SOS that calls family AND emergency contact simultaneously, adapted to Thai healthcare (local hospital numbers, not just 911)
- Weekly report delivered via LINE message — no additional app needed for family members

## Development Plan

### Phase 1 — MVP (Weeks 1-4)
- [ ] Flutter project setup, Firebase project, FastAPI backend scaffold
- [ ] Phone OTP authentication (Thai SMS gateway)
- [ ] One-tap check-in UI with large Thai text button
- [ ] Check-in window configuration (time picker, duration)
- [ ] Push notification setup (Firebase Cloud Messaging)
- [ ] Family circle: add members by phone number
- [ ] Missed check-in alert dispatch
- [ ] "All clear" notification on successful check-in
- [ ] Basic check-in history log

### Phase 2 — Polish (Weeks 5-6)
- [ ] Voice check-in recording (on-device voice detection with TFLite)
- [ ] Voice confirmation feedback (human voice detected — you're good)
- [ ] SOS: hold-to-trigger countdown, simultaneous call to 2 contacts
- [ ] Weekly report generation and LINE message delivery
- [ ] UI polish for elderly users: large fonts, high contrast, minimal scrolling
- [ ] Offline mode: check-in queued if no connectivity

### Phase 3 — Launch (Week 7-8)
- [ ] App Store + Google Play submission
- [ ] 50-family beta group from personal network
- [ ] Feedback collection and bug fixes
- [ ] Firebase Analytics dashboard setup
- [ ] Prepare Facebook ad creative assets (Thai language, emotional angle)

## Notes

**Risks:**
- Elderly users abandoning the app due to daily reminder fatigue — the check-in window must be configurable and reminders must be gentle, not alarming
- Phone battery optimization killing the background process on Android — need to explicitly guide users to whitelist the app
- Voice check-in accuracy on low-quality Thai elder voices (tremor, soft speech) — requires good training data and testing with real elderly users early
- SMS OTP deliverability in Thailand — Thai carriers sometimes block shortcodes; use a verified long number SMS provider

**Open questions:**
- Should there be a web dashboard for family members? For now, LINE message is sufficient — most Thai family members won't download another app
- Medical history context for SOS — worth building or deferring to a future version?
- What is the right reminder tone for elderly Thai users? Consider using a familiar Thai melody rather than a generic notification sound

**Trademark/name check:**
- "Khon Dek" is a common Thai phrase — conduct a trademark search on the Thai Department of Intellectual Property (DIP) website before committing to the name. Alternative: "DekCheck" or "Sa-bai-dee" (สบายดี — the check-in phrase itself)
