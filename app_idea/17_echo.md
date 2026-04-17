# Echo

> You don't remember what you said six months ago. Echo plays it back -- in your own voice.

## Overview

Echo is a voice-journal app that records your spoken reflections and organizes them into a searchable, revisit-able timeline. Unlike text diaries or voice memos, Echo keeps both the original audio and a transcription, letting you hear your own voice evolve over months and years. The core experience is listening back to yourself -- your word choices, your emotional tone, the things you were worried about, the things you were excited about. It's a memory palace in your own voice.

The Thai market angle is strong: Bangkok's middle class is health-and-wellness focused (meditation apps have done well here), smartphone penetration is high, and the crowded通勤 lifestyle makes voice-first input more practical than typing. Thais are also increasingly interested in mental health and self-reflection -- the mindfulness app market in Thailand grew 40% in 2024. Voice-first journaling sidesteps the friction of typing in Thai (which requires specific keyboards) while tapping into the same wellness trend.

## Core Problem

People journal for a week or two, then stop. The main friction points are:
1. **Typing is slow and interrupts thought flow** -- you lose the thought while you type it
2. **Text journals lose the emotional texture of voice** -- you can't hear how you sounded six months ago
3. **Long journals are overwhelming to revisit** -- scrolling through pages of text is a chore, but listening to a 60-second audio clip is natural
4. **No sense of progress or pattern** -- you write entries but never see the arc of your thinking

Existing apps solve some of these (voice recording apps for audio, text journals for searchability) but none combine audio + transcription + pattern recognition + replay into one cohesive replay experience.

## Target Users

- **Primary:** Professionals 25-45 who want to journal but can't sustain the habit with text. Frequent commuters, gym-goers, people with active lifestyles.
- **Secondary:** Mental health adherents already using meditation/mood apps who want deeper self-insight. People in therapy who want to supplement sessions.
- **Niche:** Expats in Bangkok (language barrier makes voice more natural than Thai text input), new parents wanting to record thoughts without reaching for a keyboard, retirees preserving memories.

## Feature List

### Must Have (MVP)
- **60-second voice recording** -- tap to record, tap to stop. Auto-saves with timestamp.
- **Auto-transcription** -- every recording is transcribed for searchability, original audio always preserved
- **Echo timeline** -- vertical scrollable feed of entries, newest first. Each entry shows: date, duration, transcription preview, mood tag
- **Mood tagging** -- after each recording, tap one of 5 emoji moods (happy, calm, anxious, sad, excited). Quick, no typing.
- **Basic search** -- search across transcriptions by keyword

### Should Have (v1.1)
- **Pattern cards** -- weekly digest showing "You said 'stressed' 4 times this week, here are those moments back-to-back" as a stitched audio reel
- **Audio playback with scrubber** -- listen to old entries with playback speed control
- **Cloud sync** -- entries sync across devices (iOS/Android)
- **Export** -- export individual entries or collections as audio files

### Nice to Have (future)
- **Growth view** -- 3-month rolling view of most-used words, emotional tone trends, word clouds
- **Long-form recording mode** -- extended recording up to 10 minutes for deeper reflections
- **Share reel** -- export a collection of entries as a shareable audio compilation
- **Therapist mode** -- structured weekly summary designed to bring to therapy sessions
- **Reminders** -- gentle daily nudges to record a reflection

## Tech Stack

### Frontend
- Framework: **Expo (React Native)** -- fast iteration, good voice/media support
- Language: **TypeScript**
- Key libraries: expo-av (audio recording/playback), expo-speech (TTS for accessibility), react-native-paper (UI components), AsyncStorage (local persistence)

### Backend
- Framework: **Firebase** -- Firestore for entries, Cloud Functions for transcription triggers, Storage for audio files
- Language: **TypeScript / Node.js**
- Database: **Firestore** (entries: { id, userId, audioUrl, transcript, mood, duration, createdAt })
- Auth: **Firebase Auth** (phone auth works well in Thailand -- no password complexity issues)
- Hosting: **Firebase Hosting** (or Vercel for the web dashboard)

### AI / ML
- Model/Service: **Google Cloud Speech-to-Text API** (accurate, supports Thai, pay-per-character)
- Use case: Real-time transcription of voice entries

### Infrastructure
- Cloud provider: **Firebase / Google Cloud**
- CDN: **Firebase CDN** for audio streaming
- Analytics: **Firebase Analytics** (track retention, mood distribution, recording frequency)

## Monetisation

### Model
Freemium subscription. Free tier is generous enough to build habit, premium unlocks the insight features that make the app truly valuable.

### Pricing Tiers
| Tier | Price | Features |
|------|-------|---------|
| Free | 0 | Unlimited voice entries, auto-transcription, 7-day timeline, basic mood tags |
| Pro | 149 baht/mo (~USD 4.50) | Full history, pattern cards, growth view, cloud sync, export |
| Family | 249 baht/mo (~USD 7.50) | Up to 5 family members, shared family reel, cross-device sync |

### Revenue Projection
Comparable to Headspace Thailand pricing (149-199 baht/mo). Assuming 5,000 MAU at 5% paid conversion = 250 paying users = ~USD 1,125 MRR. Conservative estimate based on Thailand's growing wellness app spending (~USD 40M market, 18% CAGR). More aggressive if cross-platform (iOS launch within 3 months of Android).

## User Acquisition

### Channels
1. **TikTok/Reels** -- "hear yourself from 6 months ago" is a highly shareable emotional hook. Short video demo showing the pattern card feature. Budget: USD 500-1000/mo for boosted posts targeting 25-40 wellness-minded Thais.
2. **App Store search optimization** -- "voice journal", "audio diary", "mood tracker", "self reflection". Already low competition for voice-first journaling in Thai app stores.
3. **Therapist/counselor referrals** -- partner with Thai mental health platforms (e.g., OOCA, Mindful) to recommend Echo as a supplement to therapy. Referral commission or white-label deal.
4. **Cross-promotion with wellness apps** -- ads in Headspace, Calm, Insight Timer partner apps.

### Launch Strategy
1. Soft launch on Android in Thailand first (home market, easy feedback loop)
2. Collect 500 beta users via social media DM to friends/early adopters
3. Launch paid promotion on TikTok with emotional "hear yourself" creative
4. Iterate on retention based on day-1, day-7, day-30 cohort analysis
5. iOS launch 2-3 months after Android if Android retention is healthy

### Viral Mechanics
- **"Share your pattern card"** -- users can export their weekly pattern card as a blurred image to share on Instagram/TikTok Stories, driving organic awareness
- **"Listen to your past self"** -- the core emotional hook is inherently shareable ("I recorded this 3 months ago and I sound so different")
- Referral program: unlock extended cloud history for each friend who subscribes

## Competitors

| App | Platform | Strengths | Weaknesses | Price | Downloads |
|-----|----------|-----------|------------|-------|-----------|
| **Echo Journal** (name collision) | Android | AI transcription, mood tracking, word clouds, proven concept | Generic name, 1K downloads, basic UI, no audio playback with scrubber | Free / $3/mo | 1K+ |
| **Rosebud** | iOS/Android | Beautiful AI pattern recognition, therapist-recommended, strong 4.7 rating, CBT-based prompts, 20-language voice | Expensive ($8-15/mo reported), complex UX, text-first design, no audio replay experience | In-app purchases | 100K+ |
| **Day One** | iOS/Android | 1M+ downloads, cross-platform sync, photo integration, IFTTT automation, "On This Day" feature, automatic metadata (weather, location) | Text-first, no voice-native UX, complex for new users, premium required for photos | Free / $34.99/yr | 1M+ |
| **Voice Diary with Lock 2024** | Android | Simple voice recording, PIN/fingerprint lock, photo attachment, reminders | Basic, no AI/transcription, no patterns, no growth view, ad-supported | Free with ads | 100K+ |
| **Murmur** | Android | Voice-first, simple, social sharing | 3.6 rating (UX issues), limited features, no cloud sync | Free with ads | Unknown |

## Unique Angle

The existing market splits into two camps:
1. **Text journals** (Day One, Rosebud, Diarium) -- searchable but lose voice texture
2. **Voice recorders** (built-in voice memos, basic voice diary apps) -- preserve voice but no structure, search, or patterns

Echo sits in a third category that doesn't really exist yet: **voice-native replay**. The app isn't about writing or recording -- it's about *listening back to yourself*. The emotional impact of hearing your own voice from 6 months ago, hearing how your tone changed when you were stressed, noticing you've stopped saying certain things -- that's the core value. The UI should feel like a voice mail from your past self, not a text document with an audio attachment.

The "pattern card" feature (stitching related audio clips into a highlight reel) is the key differentiator. Rosebud shows you a word cloud; Echo plays you a 90-second montage of every time you said you were anxious this month.

**Naming risk:** There is an existing "Echo Journal: AI Voice Diary" on Google Play. The name needs to either (a) differentiate clearly in the store listing (emphasize the replay/audio evolution angle), or (b) consider a slight rebrand (e.g., "Echoes" plural, or "Recall" as the app name). Recommend checking trademark before committing.

## Development Plan

### Phase 1 -- MVP (Weeks 1-4)
- [ ] Set up Expo project with expo-av for audio recording
- [ ] Implement 60-second voice recording UI (tap to record, tap to stop)
- [ ] Integrate Google Cloud Speech-to-Text API for transcription
- [ ] Build local storage (AsyncStorage) for entries
- [ ] Create Echo timeline screen (newest entries, scrollable)
- [ ] Add mood tagging (5 emoji options per entry)
- [ ] Basic search across transcriptions
- [ ] Firebase Auth setup (phone number for Thailand)

### Phase 2 -- Polish (Weeks 5-6)
- [ ] Cloud sync with Firebase Firestore + Storage
- [ ] Audio playback screen with scrubber and speed control
- [ ] App store listing (Android first, Thailand)
- [ ] Referral system (Firebase Dynamic Links)
- [ ] Pattern card generation (find related entries by mood/keywords, stitch audio)

### Phase 3 -- Launch (Week 7-8)
- [ ] Soft launch in Thailand (invite-only beta via social media)
- [ ] Analytics setup: day-1, day-7, day-30 retention cohorts
- [ ] TikTok content: "hear yourself" demo videos
- [ ] Collect first 500 users, gather feedback
- [ ] Iterate on retention based on data

## Notes

**Risks:**
- Google Cloud Speech-to-Text pricing (~$0.006/15 seconds) needs careful monitoring. At 10 entries/day/user, that's ~6 minutes of audio/day = ~$0.0024/day/user = manageable but needs a cap on the free tier.
- The name collision with "Echo Journal" is a moderate risk. Conduct a trademark search before launch.
- Voice journaling habit retention is unproven in Thailand market -- the "hear yourself" hook needs validation with real users early.

**Open questions:**
- Should entries be private-by-default or shareable? (Recommend private-by-default with optional share)
- Thai language transcription accuracy -- Google Speech-to-Text supports Thai but accent/dialect matters. Test extensively with Thai users.
- Cloud storage costs at scale: 60-second audio @ 64kbps = ~480KB/entry. 1,000 users x 10 entries/day x 30 days = 144GB/mo. At Firebase Storage pricing (~$0.02/GB), that's ~$2.88/mo -- negligible at startup.
