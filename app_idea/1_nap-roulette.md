# Nap Roulette

> Set a timer, hit sleep, let the app roll the dice on your ambient soundscape and wake you at the perfect moment in your sleep cycle.

## Overview

Nap Roulette is a power nap app with a twist — every session is a random discovery. Set your timer, hit sleep, and the app generates a unique ambient sound mix (rain + train, jungle + fan, cafe noise) while tracking your sleep phases to wake you within a 10-minute window aligned to light sleep. No two naps sound the same.

The target user is anyone who naps regularly — remote workers, students, parents, Bangkok commuters catching a break between meetings. The Thai market context is relevant here: Bangkok is hot, exhausting, and people are always looking for quick reset buttons. Power naps are culturally normalized and the app speaks to that lifestyle.

## Core Problem

Most nap apps are boring and repetitive. You pick one soundscape, you hear the same thing every time, you get bored, you stop using it. Users also struggle to wake up at the right time — either they wake up groggy because they're in deep sleep, or they oversleep and miss their window. Nap Roulette solves both: randomization keeps it fresh, and smart wake-up timing keeps it effective.

## Target Users

- **Primary:** Remote workers, freelancers, Bangkok office workers who nap between meetings or after lunch
- **Secondary:** Students during exam season, parents with irregular schedules, gym-goers who nap post-workout
- **Niche:** Digital nomads operating across time zones who need quick, effective power naps

## Feature List

### Must Have (MVP)
- Timer with customizable duration (5, 10, 15, 20, 25, 30 min)
- Random ambient sound mixer — combines two sounds from a curated library
- Smart alarm — wakes within a 10-min window based on sleep cycle estimation
- Sleep score — tracks duration vs. target and consistency over time

### Should Have (v1.1)
- Curated sound library with 10+ ambient options (rain, train, jungle, fan, cafe, ocean, forest, thunder, white noise, lo-fi)
- Save favorite mixes as presets
- Sleep history export (CSV)

### Nice to Have (future)
- Community sound mix presets (share your best mixes)
- AI-generated custom soundscapes based on mood input
- Widget for quick nap start
- Dark mode + lock screen support

## Tech Stack

### Frontend
- Framework: Jetpack Compose (Android native)
- Language: Kotlin
- Key libraries: Material 3, Jetpack DataStore (preferences), WorkManager (background alarms)

### Backend
- Framework: None required for MVP (local-only)
- Language: N/A
- Database: Room (sleep history, presets)
- Auth: None (local storage only for MVP)
- Hosting: N/A

### AI / ML
- Model/Service: None for MVP — sleep cycle estimation uses accelerometer + time-based heuristics (standard approach for consumer sleep apps)
- Use case: Sleep phase estimation (light vs. deep sleep window)

### Infrastructure
- Cloud provider: None for MVP
- CDN: N/A
- Analytics: Firebase Analytics (optional, can be added post-MVP)

## Monetisation

### Model
Freemium — free tier is fully functional, premium unlocks advanced features.

### Pricing Tiers
| Tier | Price | Features |
|------|-------|----------|
| Free | $0 | Unlimited naps, all sound mixes, basic sleep score |
| Pro | $1.99 one-time | Unlimited presets, sleep history export, no ads |

### Revenue Projection
Consumer sleep apps with 500K–1M downloads typically convert at 1–3% paid. At 50K downloads (realistic Year 1 goal): 500–1,500 buyers = $1,000–$3,000 one-time revenue. Thailand market is under-served for niche nap apps — potential to grow in Southeast Asia if localized.

## User Acquisition

### Channels
1. Product Hunt launch — tap the "sleep" and "productivity" communities early
2. TikTok/Reels short videos — "I let Nap Roulette pick my sounds for 30 days" authentic content
3. Reddit (r/napp, r/sleep, r/productivity) — genuine posts, not spam

### Launch Strategy
1. Publish to Play Store with free tier only, gather first reviews
2. Post on Product Hunt on launch day
3. Reach out to 3–5 Thai lifestyle micro-influencers for review exchange
4. Iterate based on user feedback

### Viral Mechanics
None built-in for MVP — the product speaks for itself. Future versions could add shareable sleep score cards.

## Competitors

| App | Platform | Strengths | Weaknesses | Price | Downloads |
|-----|----------|-----------|------------|-------|-----------|
| Sleep as Android | Android | Full-featured, wearable support, AI sound recognition, 10M+ users | Complex UI, overwhelming for simple power naps, premium required for best features | Free + $9.99 one-time | 10M+ |
| Naps & Sleep Cycle Alarm | Android | Simple, focused on power naps, lightweight | Very basic features, no sound mixing, ugly UI | Free | 10K+ |
| Pzizz | Android, iOS | Patented "dreamscapes" technology, clinically validated, press coverage (NYT, WIRED) | Expensive ($7.99/week or $59.99/year), complex for quick naps | Free trial + $59.99/year | 500K+ |
| Sleep Cycle | Android, iOS | Huge brand, sleep tracking, smart alarm, 100M+ downloads | Too feature-heavy for simple naps, expensive subscription | Free + $69.99/year | 100M+ |

## Unique Angle

Nap Roulette is not trying to be the most complete sleep app. It's the anti-overwhelm choice: set timer, sleep, wake up better. The random sound mixing is the core hook — it's the casino element. Users don't know what they'll get, so they keep coming back to try "one more roll." The smart alarm is the effectiveness guarantee.

Where Sleep as Android is a tool for sleep nerds and Pzizz is a premium wellness brand, Nap Roulette is for people who want a quick nap without configuring anything.

## Development Plan

### Phase 1 — MVP (Weeks 1–4)
- [ ] Project setup (Kotlin, Compose, Room)
- [ ] Timer with preset durations (5, 10, 15, 20, 25, 30 min)
- [ ] Sound mixer with 6 ambient options (rain, train, jungle, fan, cafe, ocean)
- [ ] Random pair generator (two sounds, mixed)
- [ ] Smart alarm — wake within light sleep window
- [ ] Basic sleep score (duration vs. target)
- [ ] Play Store listing + screenshots

### Phase 2 — Polish (Weeks 5–6)
- [ ] 4 additional sound options (lo-fi, thunder, white noise, forest)
- [ ] Favorite presets (save up to 5)
- [ ] Sleep history screen (last 7 days)
- [ ] Dark mode
- [ ] Bug fixes + performance

### Phase 3 — Launch (Week 7–8)
- [ ] Product Hunt submission
- [ ] Thailand-focused social push (Twitter/X, local subreddits)
- [ ] First 50 reviews outreach
- [ ] Analytics review

## Notes

- The random sound mixer is the core differentiator — don't make it a settings option, make it the default behavior
- Keep UI extremely simple: one screen with timer + nap button, second screen for history/presets
- Thai localization not needed immediately but consider Thai language support in v1.1 (large tourist/expat market in Bangkok)
- Competitor research shows "free with one-time purchase" outperforms subscription for this category (users hate recurring fees for simple utilities)