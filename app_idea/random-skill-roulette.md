# Random Skill Roulette

> Can't decide what to learn? Let the app pick a random micro-skill for you -- an Excel trick, a guitar chord, a magic card move -- delivered daily as a focused card with a video and practice timer.

## Overview

Learning new skills is overwhelming. Most people want to improve themselves but freeze at the starting line -- there are too many options, no clear next step, and the effort to "just start" feels bigger than it should be. Random Skill Roulette solves this by removing the decision entirely. Instead of scrolling through endless course catalogs or YouTube tutorials wondering what to learn next, you hit "spin" and the app hands you a single, bite-sized skill to learn right now.

The target user is the curious adult who has too many interests and not enough structure. Bangkok commuters, digital nomads, expats in new cities, busy professionals who want to feel like they're growing but can't commit to a 40-hour course. The app works on the principle that small, daily actions beat grand plans -- 10 minutes a day of deliberate practice compounds into real capability over months.

The market for micro-learning apps is growing but mostly dominated by language apps (Duolingo) and corporate training tools (Skillshare, LinkedIn Learning). The gap is in casual, lifestyle micro-skills -- the kind of things you learn because they're fun, not because they're career-critical. Think guitar chords, magic tricks, mental math shortcuts, photography hacks, origami, cocktail recipes. This is the uncaptured whitespace.

## Core Problem

Decision fatigue kills learning before it starts. When someone decides they want to "learn something new this week," they spend more time researching options than actually learning. The average learner spends 23 minutes choosing a course on Udemy before starting it. Random Skill Roulette eliminates that 23-minute trap by making the choice for you.

The second problem is accountability. Micro-skills are easy to abandon because each one feels insignificant. "I learned one guitar chord this week" sounds like failure compared to "I completed a Python course." The app reframes this by tracking every skill attempted, practiced, and mastered -- turning a fragmented learning journey into a visible collection.

## Target Users

- Primary: Adults 22-40 who want to develop new hobbies and practical skills but lack structure or time for long courses.
- Secondary: Bangkok commuters and travelers who want productive use of 10-15 minute idle pockets of time.
- Niche: Expats looking to learn Thai-specific skills (cooking, language survival phrases, Muay Thai basics).

## Feature List

### Must Have (MVP)
- Daily skill card: one random micro-skill with short text explanation, embedded YouTube video, and a built-in practice timer (5/10/15 min options).
- Spin button: randomize a new skill instantly, limited to 3 per day on free tier.
- Skill library: browsable catalog of all available micro-skills organized by category (music, cooking, tech, magic, fitness, language, art).
- Progress tracking: mark skills as "wanted to try," "practiced," or "mastered."
- Skill tree view: visual node graph showing attempted vs. mastered skills.

### Should Have (v1.1)
- Community submissions: users can submit new micro-skills with text + YouTube link for peer review.
- Skill-of-the-day notification: push notification at a user-set time (e.g., 8am) as a daily habit trigger.
- Thai local pack: curated micro-skills relevant to Bangkok life -- Thai cooking, basic phrases, local etiquette.

### Nice to Have (future)
- Expert skill packs: premium curated packs from actual experts (e.g., "5 Magic Tricks from a Street Performer," "Photography Hacks from a Pro").
- Skill certification badges: complete all skills in a category to earn a badge.
- Social sharing: generate a nice card of your "skill of the day" to share on social media.

## Tech Stack

### Frontend
- Framework: React Native (iOS + Android cross-platform)
- Language: TypeScript
- Key libraries: react-native-video (YouTube embeds), @react-native-push-notification (daily reminders), react-navigation (tab-based UI), AsyncStorage (local progress persistence)

### Backend
- Framework: Firebase (Auth, Firestore, Cloud Functions)
- Language: TypeScript
- Database: Firestore for skill library, user progress, community submissions
- Auth: Firebase Anonymous auth (let users try before signing up) + Google Sign-In for full features
- Hosting: Firebase Hosting + Cloud Functions for API

### AI / ML (if applicable)
- Model/Service: None required for MVP. Future version could use GPT-4 to auto-generate skill descriptions from YouTube video transcripts.
- Use case: Auto-summarize YouTube videos into 3-bullet skill cards.

### Infrastructure
- Cloud provider: Firebase (GCP under the hood)
- CDN: Firebase Hosting global CDN
- Analytics: Firebase Analytics + Mixpanel for funnel analysis

## Monetisation

### Model
Freemium + Marketplace cut.

The app itself is mostly free. Revenue comes from:
1. Premium skill packs (one-time purchase or subscription)
2. Expert certifications (paid badge unlocks)
3. Marketplace cut on community-submitted skill packs (10%)

### Pricing Tiers
| Tier | Price | Features |
|------|-------|---------|
| Free | $0 | 3 spins/day, access to free skill library, basic progress tracking |
| Pro | $2.99/mo or $19.99/yr | Unlimited spins, all free skill packs, advanced analytics, no ads |
| Expert Packs | $0.99-$4.99/pack | Curated packs from real experts, certification badges |

### Revenue Projection
Conservative estimate: 50K downloads in Year 1, 3% paid conversion = 1,500 paying users x $24/year = ~$36K ARR. If even 0.5% upgrade to Expert Packs, add another $10-15K. Thai market alone (high smartphone penetration, growing English-learning app adoption) could drive 10K+ downloads in first 6 months.

## User Acquisition

### Channels
1. TikTok / Short-form video -- "Watch me learn a random skill in 10 minutes" content. Low-cost UGC loop where users film themselves completing a skill from the app and tag it. Viral potential because the content is inherently entertaining.
2. Product Hunt launch -- early adopter tech audience looking for novel productivity tools.
3. Reddit communities (r/IWantToLearn, r/SkillBuilding) -- organic posts with demo videos.

### Launch Strategy
1. Build MVP with 100 seed micro-skills across 8 categories.
2. Submit to Product Hunt on a Tuesday.
3. Post demo video on TikTok day-of-launch.
4. Reach out to 5 micro-influencers (5K-20K followers) in productivity/lifestyle space for free pro accounts in exchange for one post.
5. Monitor App Store reviews, iterate fast.

### Viral Mechanics
- Skill share card: auto-generates a clean image saying "I just learned [SKILL] from Random Skill Roulette" with app branding. Users share this naturally.
- Referral: invite a friend, both get +1 extra spin per day (encourages daily habit building).

## Competitors
> Search Google Play and App Store before writing this. Find 3-5 real apps that do something similar.

| App | Platform | Strengths | Weaknesses | Price | Downloads |
|-----|----------|-----------|------------|-------|-----------|
| Micro-Skills (now-here) | Android | Focused on workplace micro-skills, clean UI, 100+ downloads | Corporate/B2B feel, no random spin mechanic, no community | Free | 100+ |
| Skillshare | iOS/Android | Massive catalog (35K+ classes), strong brand, high-quality production | Not micro at all -- full courses, subscription only, overwhelming | $13.99/mo | 10M+ |
| Headway | iOS/Android | Beautiful design, daily micro-lessons, strong gamification | Books-only content, no community, no video | Free + $69.99/yr | 10M+ |
| SmartyMe | Android | Micro learning bursts, workplace skills | Corporate feel, no randomness, no community | Free | 100K+ |
| Duolingo | iOS/Android | Daily streak mechanic, gamification perfected | Language-only, no casual/hobby skills | Free + $12.99/mo | 100M+ |

## Unique Angle

Skillshare teaches you everything but requires commitment. Duolingo gamifies one domain obsessively. Headway turns books into daily bites. Random Skill Roulette is the only app that:

1. **Embraces randomness** -- the spin mechanic is the core experience, not a bug. It makes learning feel like a game of curiosity rather than a task list.
2. **Focuses on lifestyle/hobby micro-skills** -- not career skills or language (already dominated), but the fun stuff: magic, guitar, cooking, photography.
3. **Has zero commitment** -- one skill, one timer, done. No courses, no curriculum, no progress bars that make you feel guilty for missing a day.
4. **Community-built library** -- users submit skills, creating an ever-growing, eclectic catalog no single company could build alone.

## Development Plan

### Phase 1 -- MVP (Weeks 1-4)
- [ ] Build React Native skeleton with Firebase setup
- [ ] Seed database with 100 micro-skills across 8 categories
- [ ] Implement spin mechanic and daily skill card UI
- [ ] Build practice timer with notification
- [ ] Basic skill tree view (local state)
- [ ] Anonymous auth + Google Sign-In
- [ ] Local progress tracking (AsyncStorage)

### Phase 2 -- Polish (Weeks 5-6)
- [ ] Refine skill card design (YouTube embed, timer, progress buttons)
- [ ] Push notification system for daily reminder
- [ ] Skill library browsable search
- [ ] Firebase Firestore integration for cloud sync of progress
- [ ] Share card generation (canvas-based image export)

### Phase 3 -- Launch (Week 7-8)
- [ ] App Store + Google Play submission
- [ ] Product Hunt launch
- [ ] TikTok content drop
- [ ] Influencer outreach (10 micro-influencers)
- [ ] Monitor crash reports, fix critical bugs

### Phase 4 -- Community (Weeks 9-12)
- [ ] Community submission form
- [ ] Peer review workflow for submissions
- [ ] Thai local skill pack (launch as v1.1)

## Notes

**Risks:**
- Skill library can feel shallow if not enough high-quality entries. Seed with at least 100 genuinely interesting skills -- not generic ones users can find on YouTube in 2 seconds.
- YouTube embeds add dependency. If a video goes private, the skill card breaks. Consider using video previews/thumbnails instead of full embeds.
- Randomness can feel frustrating if users get skills they already know. Add "I already know this -- show me another" button (costs 1 spin).

**Open questions:**
- Should the app have social features beyond sharing? Friends lists? Competing on streaks? Start lean -- share card is enough for launch.
- How to handle skill quality from community submissions? Needs a curation layer (upvotes + admin review) before going live in the library.
- Monetisation through Expert Packs requires actually recruiting experts. This is a post-launch problem -- seed with editorial packs initially.

**Thai market notes:**
- Bangkok commuters have 1-2 hours of idle time daily on BTS/MRT. This is the perfect use case.
- Thai food/cooking skills should be a core category from day one.
- Payment via LINE Pay / TrueMoney wallet would boost conversion vs. credit card alone.
