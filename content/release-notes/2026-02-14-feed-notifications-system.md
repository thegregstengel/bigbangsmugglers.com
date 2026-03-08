---
title: "Feed Notifications - Community Activity Without Surveillance"
date: 2026-02-14
description: "Real-time event feed with privacy-first design and admin broadcast tools"
author: "Dev Team"
---

## The Problem

Players had no awareness of what was happening in their galaxy. Did someone join? Complete a big mission? Buy a capital ship? Claim a planet? No way to know.

The galaxy felt empty and isolated, even with dozens of active players.

## The Vision

**Show community activity without tactical surveillance.**

Players should see:
- ✅ Who's joining/leaving
- ✅ Major achievements (mission complete, ship purchase)
- ✅ Territory changes (planet claims)
- ✅ Combat outcomes (who won/lost)

Players should **not** see:
- ❌ Exact sectors or coordinates
- ❌ Cargo loads or trade routes
- ❌ Ship positions or movements

**Privacy first. Atmosphere over surveillance.**

## The Solution: Feed Notification System

### 6 Event Types

#### 1. Join/Leave (Season Category)
```
"PlayerName joined the galaxy!"
"PlayerName has left the galaxy"
```
- Shows community growth/shrinkage
- Minor severity (doesn't clutter feed)

#### 2. Mission Complete (Mission Category)
```
"PlayerName completed mission: Deliver Medical Supplies"
```
- Shows player achievement
- Minor severity

#### 3. Ship Purchase (Economy Category)
```
"PlayerName purchased a Freighter MK3!"
```
- Shows economic activity
- Minor severity

#### 4. Planet Claim (Planet Category)
```
"PlayerName claimed New Terra in the Outer Rim!"
```
- Shows territory expansion
- Standard severity (important event)

#### 5. Combat (Combat Category)
```
"PlayerName defeated PlayerB in combat"
```
- Shows PvP activity
- Standard severity
- Respects privacy (no sector shown)

#### 6. Admin Announcements (Admin Category)
```
"Server maintenance scheduled for tomorrow at 14:00 UTC"
```
- Admin broadcasts
- Standard severity
- Global or galaxy-specific targeting

### Privacy Principles

**What We Show:**
- Player names
- Event outcomes (win/loss, purchase, claim)
- General locations (region names, not sectors)

**What We Hide:**
- Sector IDs or coordinates
- Ship positions
- Cargo contents
- Trade routes
- Combat tactics (just outcome)

**Why:** You should know **who** is active and **what** they achieved, but not **where** they are or **how** they did it.

## Implementation

### Backend: Fire-and-Forget

```typescript
// In mission complete function
try {
  await postSeasonFeedMessage(
    galaxyId,
    'mission',           // FeedMessageType
    'mission',           // FeedCategory
    `${playerName} completed mission: ${missionName}`,
    'minor',             // Severity
    { title: 'Mission Complete', metadata: {...} }
  );
} catch (feedError) {
  logger.warn('Failed to post feed notification:', feedError);
  // Transaction already completed - just log error
}
```

**Key:** Feed posting never blocks core transactions. If it fails, we log it and move on.

### Frontend: Real-Time Feed

**Feed Screen shows:**
- Recent events (newest first)
- Category badges (season, mission, economy, planet, combat, admin)
- Severity indicators (minor = gray, standard = white)
- Timestamps (relative: "2m ago", "1h ago")

**No refresh needed** - Firestore listeners update in real-time

## Admin Broadcast Feature

### Settings Card

**Admin-only card in Settings screen:**
- Target selector: Global or specific Galaxy
- Galaxy dropdown (auto-populated)
- Multi-line message input
- Post button

### Use Cases

**Global announcements:**
- "Server maintenance scheduled..."
- "New feature released: PvP combat zones"
- "Season 5 starts tomorrow!"

**Galaxy-specific:**
- "Congratulations to PlayerX for reaching Level 50!"
- "Federation-Pirate war begins at midnight"
- "Double XP weekend in this galaxy!"

### Backend Validation

```typescript
export const adminFeedPost = onCall(async (request) => {
  const { uid } = request.auth;
  
  // Verify admin privileges
  const playerDoc = await db.collection("players").doc(uid).get();
  if (!playerDoc.data()?.isAdmin) {
    throw new HttpsError('permission-denied', 'Admin access required');
  }
  
  // Post message
  await postSeasonFeedMessage(...);
});
```

**Security:** Only admins can post. Non-admins get permission denied.

## Statistics

**Files Modified:**
- `functions/src/missions/completeMissionV1.ts` (mission feed post)
- `functions/src/ship/purchaseV1.ts` (ship purchase feed post)
- `functions/src/season/enhancedSeasonManagerV2.ts` (join/leave feed posts)
- `functions/src/feed/adminPostV1.ts` (NEW - admin announcements)
- `functions/src/feed/globalFeedFunctions.ts` (added join/leave types)
- `app/src/screens/SettingsScreenV2.tsx` (admin feed post card)

**Lines of Code:**
- Backend: ~200 lines (admin post + feed helpers)
- Frontend: ~150 lines (admin card + galaxy selector)
- Documentation: 9.7KB (`docs/features/feed-notifications.md`)

**Commits:**
- a24b28d (join/leave notifications)
- 97c1c4e (mission/ship notifications)
- 59c811d (admin feed post card)
- 53651e8 (galaxy selector dropdown)
- 81ae13a (feed notifications docs)

## Event Examples

### Join Event
```typescript
{
  type: 'join',
  category: 'season',
  message: 'PlayerName joined the galaxy!',
  severity: 'minor',
  timestamp: '2026-02-14T22:15:00Z'
}
```

### Mission Complete
```typescript
{
  type: 'mission',
  category: 'mission',
  message: 'PlayerName completed mission: Deliver Medical Supplies',
  severity: 'minor',
  title: 'Mission Complete',
  metadata: { missionId, reward: 500 }
}
```

### Ship Purchase
```typescript
{
  type: 'economy',
  category: 'economy',
  message: 'PlayerName purchased a Freighter MK3!',
  severity: 'minor',
  metadata: { shipClass: 'freighter_mk3', cost: 25000 }
}
```

### Combat Outcome
```typescript
{
  type: 'combat',
  category: 'combat',
  message: 'PlayerName defeated PlayerB in combat',
  severity: 'standard',
  metadata: { winner, loser, outcome: 'victory' }
}
```

### Admin Announcement
```typescript
{
  type: 'admin',
  category: 'admin',
  message: 'New feature: PvP combat zones now live!',
  severity: 'standard',
  title: 'Feature Release',
  metadata: { global: true }
}
```

## Severity Levels

**Minor (Gray):**
- Join/leave
- Mission complete
- Ship purchase
- Background activity

**Standard (White):**
- Planet claim
- Combat
- Admin announcements
- Important events

**Why Two Levels?** Minor events show activity without cluttering. Standard events demand attention.

## Design Decisions

### Fire-and-Forget Pattern

Feed posting uses try/catch with logging only:

```typescript
try {
  await postSeasonFeedMessage(...);
} catch (error) {
  logger.warn('Feed post failed:', error);
  // Transaction already completed - don't fail
}
```

**Why:** Core transactions (mission complete, ship purchase) should never fail because feed posting failed. Feed is nice-to-have, not critical.

### Non-Intrusive Notifications

All feed events use `minor` severity except combat and admin announcements.

**Why:** Feed should feel like ambient awareness, not constant alerts. Players check feed when they want updates, not because they're bombarded.

### Privacy Protection

No sector IDs, coordinates, or tactical intel in feed messages.

**Why:** Feed shows **who** is active, not **where** they are. Prevents stalking while maintaining community feel.

## What's Next

### Potential Future Events

- **Corporation announcements** (corp formed, alliance made)
- **Alliance declarations** (Corp A declares war on Corp B)
- **Territory conquests** (Corp captures sector)
- **Leaderboard milestones** (top 10, top trader, top combatant)
- **Rare discoveries** (wormhole found, ancient artifact discovered)

### Enhanced Admin Tools

- **Scheduled posts** (announce maintenance ahead of time)
- **Post templates** (common announcements pre-written)
- **Player targeting** (send message to specific player's feed)
- **Rich formatting** (bold, links, images)

## Try It Now

**Check your feed:**
1. Open Feed tab
2. See recent activity (joins, missions, purchases)
3. Watch for real-time updates (no refresh needed)

**Admins: Try the broadcast tool:**
1. Open Settings
2. Scroll to Admin Tools → Feed Post
3. Select target (Global or specific Galaxy)
4. Write message
5. Click Post
6. Check feed to confirm

---

**Technical Details:** See `docs/features/feed-notifications.md` for implementation guide (9.7KB, 352 lines).
