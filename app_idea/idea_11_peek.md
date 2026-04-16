# Peek — App Idea #11

**Date:** 2026-04-16
**Status:** Brief

---

## Concept

A social photo-sharing app where images start blurred and gradually sharpen as friends react. The more love a photo gets, the more it reveals. Reactions are literal currency of visibility.

---

## Core Mechanic

- **Post a photo** at 80% gaussian blur
- **Each reaction** (like, comment, share) chips away blur
- **Fully unblurred** at ~50 total reactions
- **Auto-unblur** after 24 hours regardless of reactions
- **Custom unlock countdown** available at post time

---

## Features

### Feed
- **Peek Feed** — main timeline showing all photos in your circle at their current blur level
- Photos appear in real-time as friends post
- Tapping a blurred photo opens it in a focus view where you can react
- Progress bar under each photo shows % to full clarity
- Live blur updates as reactions come in

### Reactions & Engagement
- Standard reactions: ❤️, 😂, 🔥, 😮, 👏 (5 types)
- Each reaction type removes a different amount of blur (fire and love remove the most)
- Comments also contribute to unblurring
- Share accelerates blur removal more than any other action

### Posting
- Camera or gallery import
- Adjustable starting blur level (60% to 95%)
- Optional countdown timer (1h, 6h, 12h, 24h, custom)
- Tag friends to add them to the view pool

### Profile
- Posted photos with final reveal stats
- Total reactions received, average time to unblur
- Boosted photos

---

## Monetization

| Feature | Free | Pro (~$2.99/mo) |
|---|---|---|
| Photos per day | 3 | Unlimited |
| Max starting blur | 80% | 95% |
| Custom countdown | No | Yes |
| Blur patterns | Solid only | Gradient, pixelated, puzzle |
| Analytics | Basic | Full breakdown by reaction type |
| Boost button | No | Yes (pay to instantly remove 20% blur) |
| Ad-free | No | Yes |

---

## Tech Stack

- **Framework**: Expo (React Native)
- **Backend**: Firebase (Firestore, Storage, Cloud Functions, FCM)
- **Auth**: Firebase Auth (phone or social)
- **Real-time**: Firestore listeners + Cloud Messaging
- **Image Processing**: Blur calculated client-side at display time based on reaction count; original stored at full resolution

---

## Key UX Flows

### Posting a photo
1. Tap + → choose camera or gallery
2. Adjust blur level with slider
3. Set optional countdown timer
4. Tag friends (optional)
5. Post → immediately appears in friends' feeds at chosen blur

### Reacting to a friend's photo
1. See blurred thumbnail in feed
2. Tap to open full focus view
3. See current reaction count and blur %
4. Tap reaction → blur animates down in real-time
5. Leave a comment → more blur removed

### Watching your own photo unblur
1. Feed shows photo with shrinking blur in real-time
2. Notifications when someone reacts
3. At 100% unblur, photo "locks in" permanently visible

---

## Use Cases

- Teaser product launches
- Birthday surprise photos
- "Guess where this is" location games
- Anonymous confessions with reveal mechanics
- Event countdowns

---

## Strengths

- Unique mechanic — no direct competitor does this
- Strong social loop — posting creates natural curiosity for friends to react
- Simple to understand, hard to put down
- High engagement through anticipation

## Weaknesses

- Photos are less usable for real documentation (they start blurry)
- No value without an existing social graph
- Novel interaction requires user education
- Blur removal is irreversible — poor photos can't be "undone"

---

## Competitive Edge

Traditional social apps reward posting with instant likes. Peek inverts this — it rewards engagement bait and social capital. The blur mechanic turns every photo into a mini-game and every reaction into a tangible contribution.
