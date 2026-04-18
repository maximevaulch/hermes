# Thammasook

> Your Buddhist calendar, merit guide, and temple compass — all in one.

## Overview

Thailand runs on a dual calendar: the Gregorian for government and business, but the Buddhist lunar calendar for the spiritual life that actually structures most Thai people's year. Buddhist holidays, uposatha days, temple festivals, and merit-making seasons come and go according to a calendar most people have to manually check or just... miss. Thammasook bridges that gap — it knows what's happening spiritually in Thailand this week, points you to the nearest place to participate, and keeps a personal log of your own dharma practice so the habit compounds.

The user is a working Thai person who wants to make merit regularly but needs a nudge and a map. They might want to know if today is an uposatha day (bi-monthly observance), when Songkran's religious rites fall vs. the water-throwing days, which nearby temples have upcoming bunwatthanakhi (ordination anniversary) celebrations, or simply a reminder to put a candle on the home shrine each morning. Thammasook treats Buddhist practice as a living, daily discipline — not a once-a-year temple visit.

## Core Problem

Thai Buddhist practice is rich but poorly served by technology. The Buddhist lunar calendar is genuinely complex — uposatha days fall on different Gregorian dates each month, major festivals shift by a week or more year to year — and most people either don't know when observance days are until the day-of, or they rely on word-of-mouth. Existing apps show the calendar but don't help you *act* on it: no temple finder with real crowd data, no personal merit log that makes consistency visible, and no education layer explaining what each festival actually means. The result is a disconnected practice — people want to engage more but lack the frictionless tools to do so.

## Target Users

- **Primary**: Working Thai adults (25-50) who identify as Buddhist and want to maintain regular merit-making habits but need reminders and structure
- **Secondary**: Older Thai adults (50+) who follow Buddhist calendar closely but aren't tech-native — need simplicity and large-text support
- **Niche**: Bangkok commuters who pass temples daily but never stop, and would benefit from a "nearby temple of the day" nudge; Thai diaspora who want to stay connected to Thai Buddhist practice from abroad

## Feature List

### Must Have (MVP)
- **Buddhist lunar calendar**: Automatically highlights Buddhist holidays, uposatha days, and temple festival dates. Shows both Gregorian and lunar date side-by-side. Uses Thai Buddhist Institute data for accuracy. Supports offline cached data with monthly sync.
- **Today in dharma**: Daily home screen widget/card showing the spiritual significance of today's date — what merit-making activity is traditionally recommended, which Bodhisattva or Buddha aspect is honored, and a short translated reading from Pali or Thai tradition.
- **Merit journal**: Log dharma activities — alms-giving, temple visits, candle offerings, Pali chanting, animal releases, Dhamma book donations. Each entry is one tap. Shows practice history as a streak-calendar heatmap so consistency becomes visible. Basic free tier: 30 entries/month.
- **Temple finder (static)**: Map layer of temples within configurable radius, showing temple name, type (forest, city, royal), and user check-in count. Manual "I visited" check-in button.

### Should Have (v1.1)
- **Temple crowd signals**: Users can check in and set current activity level (quiet / medium / festival) when at a temple, building real-time crowd signal data visible on the map layer
- **Festival deep-dive cards**: When a major festival approaches (Songkran, Kathina, Makha Bucha, Visakha Bucha), surfaces a card explaining the religious meaning, historical origin, and specific rites recommended for that day — not just "it's a holiday"
- **Smart reminders**: Set recurring daily reminders (morning shrine, evening reflection) or one-time alerts for upcoming observance days. Option to remind *before* a holy day rather than on it.
- **Practice streak analytics**: Heatmap + streak counter for consecutive days of logged merit activity. Streak protection: earn bonus "shield" entries by over-performing.

### Nice to Have (future)
- **Uposatha day widget**: Persistent home screen widget showing "Nearest uposatha day: X days" with countdown
- **Export merit record as shareable card**: Generate a visually formatted image of your monthly merit summary to share on social media
- **Buddhist calendar widget**: Home screen widget showing today's lunar date and significance
- **Online merit portal**: Partner with temples to allow digital alms-giving, candle offering, or donation through the app (revenue share)

## Tech Stack

### Frontend
- **Framework**: Jetpack Compose (Android native Kotlin)
- **Language**: Kotlin 1.9+
- **Key libraries**:
  - Room (local database for journal entries and cached calendar data)
  - Hilt (dependency injection)
  - Coil (image loading for temple photos)
  - DataStore (preferences)
  - WorkManager (reliable background sync and reminders)
  - Google Maps SDK (temple map layer)
  - Firebase Analytics

### Backend
- **Framework**: Kotlin + Spring Boot 3 (or Firebase Cloud Functions for faster MVP)
- **Language**: Kotlin
- **Database**: Firestore (temple data, user journal backup) + PostgreSQL (temple master data, crowd signal aggregation)
- **Auth**: Firebase Auth (Google Sign-In, phone number)
- **Hosting**: Firebase App Hosting or Cloud Run

### AI / ML (future)
- Model/Service: Gemini Nano (on-device) for generating personalized practice suggestions based on journal patterns
- Use case: "Based on your last 30 days, you tend to miss weekends. Try a Sunday morning shrine routine?"

### Infrastructure
- Cloud provider: Google Cloud (Firebase-native)
- CDN: Firebase Hosting
- Analytics: Firebase Analytics + Crashlytics

## Monetisation

### Model
Freemium subscription with physical merchandise tie-in potential.

### Pricing Tiers
| Tier | Price | Features |
|------|-------|---------|
| Free | 0 | Full Buddhist calendar, temple finder, basic merit journal (30 entries/month), 3 festival deep-dives/week, today-in-dharma card |
| Pro | ฿149/year | Unlimited journal entries, all festival deep-dives unlocked, practice streak analytics, nearest uposatha day widget, export merit record as shareable card, ad-free |

### Revenue Projection
Thailand has ~60M smartphone users, ~53M Buddhists (Buddhist majority by constitution). Conservative estimate: 100K downloads in year 1, 3% paid conversion = 3,000 subscribers x ฿149 = ~฿447,000/year (~$13K USD). At 500K downloads with 5% conversion: ~฿3.7M/year. The real leverage is Thai Buddhist temples as distribution partners — temples can endorse the app to their congregations, dramatically lowering CAC.

## User Acquisition

### Channels
1. **Temple partnerships**: Approach temple abodes (phra bodhirak) in Bangkok first — offer free Pro accounts for monks and temple staff in exchange for word-of-mouth endorsement to congregation. Bangkok has 400+ registered temples.
2. **TikTok/Instagram**: "What merit should I make today?" — short, educational content explaining Buddhist practice. Thai creator economy is massive; partner with Buddhist content creators.
3. **Facebook communities**: Thai Buddhist Facebook groups (millions of members) are highly active. Organic posting + targeted ads.
4. **App Store optimization**: "Buddhist calendar Thailand," "uposatha day reminder," "merit journal Thailand" — low competition keywords.

### Launch Strategy
- **Month 1**: Build temple database (scrapable from Department of Religious Affairs), build calendar engine with Thai Buddhist Institute data validation
- **Month 2**: Soft launch in Bangkok — 500 beta users from temple communities. Iterate on journal UX.
- **Month 3**: Public launch. Seed 50 temples with QR codes linking to Play Store.
- **Month 6**: Add crowd signals. Add Pro tier.

### Viral Mechanics
- Merit record shareable card (export as image) — users share their monthly practice summary
- "Nearest uposatha day" widget — passive daily brand exposure
- Temple check-in streak — social proof within the app

## Competitors

| App | Platform | Strengths | Weaknesses | Price | Downloads |
|-----|----------|-----------|------------|-------|-----------|
| Thailand Buddhist Calendar (TungYaaApp) | Android | Clean calendar UI, dual language (TH/EN), uposatha bell notification, 4.9 stars | No merit journal, no temple finder, no education layer, looks dated | Free + ฿60/year ad removal | 1M+ |
| Thai Calendar: Holiday & Event (Paraga Mobile) | Android | Full Buddhist + public holiday calendar, date range 2443-2643 BE | No merit log, no temple features, poor EN translations, calendar accuracy issues | Free + ads | 500K+ |
| Thai Merit (Lucky Heng Heng) | Android | Online merit portal (digital alms, bird release), temple collection | No calendar integration, no personal journal, no education, dated UI, 4.3 stars | Free | 10K+ |
| Buddhist Sun (Dhamma Development) | Android | Solar noon calculator for monks, precise timing | Extremely niche (monks only), no calendar, no journal | Free | 1K+ |

## Unique Angle

Existing Buddhist calendar apps are calendars first, nothing else. Thai Merit is a temple directory with a commercial layer (online donations). Nobody has built the *practice* layer — a personal merit journal that makes your spiritual consistency visible, combined with a calendar that actually tells you *what to do today* and *where to do it*. Thammasook's wedge is treating Buddhist practice as a habit with data — streak counters, heatmaps, reminders — borrowed from fitness app psychology but applied to dharma.

## Development Plan

### Phase 1 — MVP (Weeks 1-4)
- [ ] Set up Kotlin/Android project with Jetpack Compose, Hilt, Room, DataStore
- [ ] Build Buddhist lunar calendar engine with Thai Buddhist Institute data (BE/CE conversion, uposatha calculation, public holiday overlay)
- [ ] Implement "Today in dharma" daily card with curated content
- [ ] Basic merit journal with local Room database (add entry, view history, streak heatmap)
- [ ] Static temple map layer (pre-seeded database of Bangkok temples via Google Maps API)
- [ ] Push notification system for uposatha day reminders

### Phase 2 — Polish (Weeks 5-6)
- [ ] Practice streak analytics — streak counter, heatmap visualization, shield system
- [ ] Festival deep-dive cards for 4 major festivals (Songkran, Makha Bucha, Visakha Bucha, Asalha Bucha)
- [ ] Smart reminder system with pre-holy-day nudges
- [ ] Firebase Auth + cloud backup of journal data
- [ ] Pro/ Free tier gate implementation

### Phase 3 — Launch (Week 7-8)
- [ ] Play Store listing with screenshots and EN/TH descriptions
- [ ] ASO: keyword targeting for "Buddhist calendar Thailand," "uposatha reminder," "merit journal"
- [ ] Submit to Thai tech media (TechSauce, The Standard) for launch coverage
- [ ] Initial temple partnership outreach (10 temples in Bangkok)

## Notes

- **Thai Buddhist Institute API**: The Thai government maintains the Buddhist calendar data — validate that it's available as an open API or scrape+cache from official sources. Accuracy is non-negotiable.
- **Battery impact**: Buddhist users will want the uposatha reminder even overnight. Aggressive battery optimization on Xiaomi/Oppo/Realme devices (common in Thailand) will kill background notifications. Need to test on real Thai phones and guide users to whitelist the app.
- **EN/TH localization**: Default to Thai with full English translation. Buddhist terminology has no good EN equivalent (e.g., "บุญ" is both "merit" and "goodness" and "spiritual credit") — use "merit" consistently and provide glossary tooltips.
- **Naming**: "Thammasook" (ธรรมะสูك) means "saffron robed" / monastic — evocative but verify no trademark conflict on App Store before committing.
- **Temple crowd signals risk**: User-generated crowd data requires liquidity — if no one is checking in, the signals are useless. Solved in v1.1 by launching with static "popular temples" pre-tagged with typical activity levels, then enabling user signals as the user base grows.
