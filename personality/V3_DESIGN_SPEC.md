# Pickleball Personality Quiz V3 — Design Spec

> Drafting working spec. Updated as research lands. Do not deploy this file with the quiz; this is the design memo.

## What V3 must beat

- **V2 weakness 1:** Single-item dimensions are psychometrically unreliable. Need 2-3 items per axis. So 5 dims × 3 items = 15 items minimum.
- **V2 weakness 2:** "Dial-down" framed as a deficit. Reframe as a strength axis: **Composure / Court Awareness**.
- **V2 weakness 3:** No reliability/conscientiousness signal. Matchmaking-grade output needs it.
- **V2 weakness 4:** No wing mechanic, no stress archetype. 8 archetypes is fine — but Enneagram-style nuance brings 8 → 64+ effective profiles without adding items.
- **V2 weakness 5:** No radar chart on result. The single most "premium-looking" data viz for 5-7 dimensions.
- **V2 weakness 6:** No 64-cell compatibility matrix. This is the highest-traffic surface on 16Personalities. We have an 8-cell grid — needs to expand to per-pair narratives.
- **V2 weakness 7:** No Likert-resistant items. Forced-choice between two attractive options resists social-desirability bias by ~30%.
- **V2 weakness 8:** No manipulation check. Can't filter careless responses.
- **V2 weakness 9:** Generic share-card. Needs commissioned archetype hero illustration + screenshot-optimized framing.
- **V2 weakness 10:** No "send this to your group chat" trigger.

## Dimensions (V3) — 6 axes, 18 items (3 per axis)

The literature converges on these for social-sport compatibility:

1. **Vibes / Social Energy** (-2 Quiet ↔ +2 Bringer)
   - Replaces V2's "Vibes." Adds an extraversion dimension validated in racquet-sport research.
2. **Style / Risk Preference** (-2 Power ↔ +2 Touch)
   - Sport-specific. Cratty (1989), Allen-Greenlees-Jones (2013).
3. **Mode / Competitiveness** (-2 Lethal ↔ +2 Festival)
   - Gill & Deeter Sport Orientation Q. Mismatch is #1 source of partner conflict.
4. **Warmth / Agreeableness** (-2 Stone-faced ↔ +2 Beaming)
   - Strongest single predictor of "want to play again." Graziano & Eisenberg.
5. **Composure / Court Awareness** (-2 One Gear ↔ +2 Reads Room)
   - Renamed from "Dial-Down." Frames as strength. Captures emotional regulation + intensity-control.
6. **Reliability / Conscientiousness** (NEW, -2 Flaky ↔ +2 Iron)
   - Boring but load-bearing for league/round play. Surfaced in matchmaking output, not in archetype reveal.

## 8 archetypes (player-facing, 4×2 grid Vibes × Mode)

```
                     COMPETITIVE        SOCIAL
BRINGER (loud):      THE HYPE CANNON    THE FESTIVAL
STEADY-BRINGER:      THE CAPTAIN        THE ANCHOR
STEADY:              THE HAMMER         THE CRAFTSMAN
QUIET:               THE ASSASSIN       THE MONK
```

Each archetype has:
- Code (HC, FE, CT, AN, HM, CR, AS, MK)
- Name + tagline
- Hero color (from 4DP token palette)
- SVG hero icon (commissioned per archetype)
- 200-word narrative description (mad-libbed against actual scores)
- **Wing** mechanic — your primary archetype + adjacent secondary tilt, e.g. "The Festival with a Captain wing"
- **Stress archetype** — under pressure you tilt toward [adjacent type]
- **Compatibility** with each of 7 other archetypes (one paragraph each = 56 paragraphs total)
- **Internal tier** (Energizer / Amplifier / Player) computed from full vector — never shown to player

## 18 items (3 per dimension)

[Will draft after culture research lands. Mix of:
- 50% forced-choice (two attractive options, scored ipsatively)
- 30% scenario-based behavioral
- 10% slider (style preference, intensity)
- 10% multi-select (triggers, event-fit)
- 1 manipulation check ("I have flown to Mars" filter)]

## Result-page architecture (the jaw-dropping reveal)

1. **Pre-reveal animation** — pulsing court, "Reading your court DNA..." (2.5 sec, audio chime optional)
2. **Hero reveal** — SVG archetype illustration scales in, archetype name in Instrument Serif italic with gold glow, primary tagline
3. **Wing announcement** — "with a [secondary] wing" — adds nuance
4. **Radar chart** — 6 axes, animated draw-in, percentile labels per axis ("Top 12% on Warmth")
5. **Narrative paragraph** — 200 words, mad-libbed against your actual scores
6. **Stress archetype reveal** — "Under pressure, you tilt toward [X]"
7. **8-cell archetype grid** — your cell highlighted, vibes-with cells in blue, clash cells in red
8. **Top 3 compatible archetypes** — full one-paragraph compatibility narrative each (3 of 7 paragraphs surfaced; rest behind a "see all matches" expansion)
9. **Triggers acknowledged** — your trigger picks restated as "what dampens YOUR fun"
10. **Event-fit ranking** — your enjoyment per NEPC event type, ranked
11. **The canon insight quote** — "Skill rating tells you who's good. The invitation graph tells you who makes the night."
12. **Share-card moment** — auto-generated 1080×1920 PNG, share-to-X / share-to-IG buttons, "tag your group chat" prompt
13. **CTA** — "Get your group's results," "Compare with a partner" (multi-player mode)
14. **Footer** — Give 'n Receive ecosystem lockup, "Give freely, get back naturally"

## Share card spec (1080×1920 — Instagram Story format)

- Top 25%: archetype name (huge italic), wing tag
- Middle 35%: archetype hero illustration (centered, glowing)
- Below middle 25%: radar chart mini, top 2 dimensions called out as percentile
- Bottom 15%: brand mark (4D Pickleball + Give 'n Receive lockup), URL `4dpickleball.com/personality`, single quotable line per archetype

## Audio reveal (differentiator no other quiz has)

ElevenLabs voice reads 30-second archetype description aloud. Optional, opt-in. Massively differentiates because every other quiz is text-only.

## PARTNER MODE — the centerpiece, not a feature (promoted from V4 to V3)

Pickleball is the only sport where doubles is the default. Every existing pickleball personality quiz is single-player. **The unowned slot in the entire category is the Partnership Compatibility quiz.**

**Flow:**
1. Player takes 90-sec solo quiz → gets archetype + 3-letter code (e.g., **DPS** = Dinker · Patient · Stalker).
2. Result page CTA: **"Send to your partner. We'll pair your results."** (top of page, primary action.)
3. Partner clicks the share-link → takes the same quiz.
4. **Joint result page:** Team archetype name (e.g., "The Crossfire Duo"), dual character share card, predicted strengths, predicted blind spots, drill recommendations specific to this pair.
5. Premium gate AFTER emotional payoff: "Unlock your team's full doubles playbook — drills + sub recommendations — $9."

**Why this is the 10x move:**
- Built-in viral loop — every solo take recruits one friend.
- Defensibility — paddle brands cannot clone Partnership matrix without real doubles outcome data. GnT/NEPC has the data.
- Premium-justifying artifact — single-player results can't credibly charge $9, team playbooks can.
- Pickleball-native — exploits the one thing pickleball uniquely has.
- Feeds the GnT engine — every team-take is training data for Krista's matching AI.

**The Team Archetype catalog (8×8 = 64 pairings, but reduced to 16 named team types based on dimension overlap):**
- The Crossfire Duo (Bringer + Bringer)
- The Pulse and the Anchor (Bringer + Steady)
- The Hammer Pair (Power + Power)
- The Dinkstorm (Touch + Touch)
- The Generator (Festival + Festival — pure social)
- The Closers (Lethal + Lethal — pure competitive)
- The Disagreement (Festival + Lethal — predicted friction!)
- ...etc — full catalog in archetypes-team.md

## The result-copy formula (locked from differentiation research)

Every solo result must hit five beats:
1. **Verdict in ≤3 words.** "You're a Stalker." (period.) Fits a screenshot caption.
2. **Rarity %.** "3.4% of players." Drives the brag.
3. **One specific compliment.** "patience of a sniper." The flattering line they'll quote.
4. **One specific roast.** "but kitchen-line creep on the third shot." The line their partner laughs at and forwards.
5. **Relational hook.** "Pair you with a Catalyst, top-10% team. Pair you with another Stalker, the rally dies of boredom." Gives the receiver a reason to take it themselves.

This is the BuzzFeed formula upgraded with Enneagram depth + Wordle screenshot logic.

## 3-letter bio codes

Each archetype gets a 3-letter shorthand that fits a Twitter bio. Example mapping:
- The Festival → **FBT** (Festival · Bringer · Touch)
- The Hammer → **HSP** (Hammer · Steady · Power)
- The Captain → **CBM** (Captain · Bringer · Mixer)
- The Monk → **MQT** (Monk · Quiet · Touch)
- ...

The code becomes the meme. People put it in club rosters, Discord names, group-chat handles.

## Rarity calculation

Cold-start: seed with theoretical distribution from 5-axis vector (assume normal distribution per axis). Display "X.X% of players are [Y]" rounded.
Live: as real takes accumulate, replace with empirical percentages. Cron job daily refresh from Sheet → archetype-stats.json → frontend reads.

## SEO sprawl architecture

Every archetype × archetype combination = a URL:
- `/personality/festival` — type page (long-form 800-1200 word description)
- `/personality/festival-x-hammer` — partnership page (compatibility narrative)
- `/personality/festival/3.5` — DUPR-band variant page
- `/personality/team/the-crossfire-duo` — team type page

Long-tail SEO. 16Personalities has 81K+ ranking keywords; we can have 8 archetypes × 8 partnerships × 7 DUPR bands ≈ 450+ pages with shared template.

## Annual "Pickleball Personality Wrapped"

Year-end card: "You played 142 games. You leveled from Dinker to Stalker. Your most-compatible partner was [X]. Your kryptonite type was [Y]." Spotify mechanic for retention.

## Couples mode (DEPRECATED in spec — Partner Mode replaces)

## Multi-language (V3.1)

Spanish first (large pickleball Latam audience). Then maybe Mandarin. V3 ships English only.

## Data layer changes

Schema gains:
- `composure_score` (renamed from dialdown_score)
- `reliability_score` (NEW)
- `wing_archetype_code`
- `stress_archetype_code`
- `manipulation_check_passed` (boolean)
- `share_card_url` (URL of generated share image)
- `audio_listen_count` (engagement signal)

## Brand voice rules (locked, from BRAND.md)

- "DUPR rates how well you hit the ball. We rate who's worth playing with."
- "Skill rating tells you who's good. The invitation graph tells you who makes the night."
- "Give freely, get back naturally."
- KILL: synergy, leverage (verb), holistic, superpower, master, godspeed, "AI-powered," consultant speak, "it's worth noting"
- Behavior framing: "What does your game look like?" not "What's your personality type?"

## Tech stack (locked)

- Single-file HTML, vanilla JS (no framework), inline SVG, Web Animations API for transitions
- Backend: same Google Apps Script pattern (zero-cost, 5min deploy)
- Share-card: client-side canvas rendering for the PNG

## V3 micro-interaction spec (from viral UX research)

### The 3.8-second reveal — frame-by-frame
| Time | What happens | Sound | Haptic |
|------|---|---|---|
| 0.0s | User taps last answer. Screen fades to brand-dark. | Soft whoosh-down | Single tap pulse |
| 0.0–0.6s | "Reading your game…" low-contrast type. Pickleball ball traces arc across screen — the ball IS the loader. | Ball-bounce ×2 | — |
| 0.6–1.8s | Ball lands center, ripples out. Background gradient shifts to YOUR archetype's palette. Type fades: "you play like…" | Low rumble building | — |
| 1.8–2.2s | Type clears. Quick black flash 50ms. | Drop | Triple-pulse [30,60,30] |
| 2.2–2.6s | Archetype name SNAPS IN — large italic, bottom-aligned. NO "your archetype is" — just **"The Festival."** with the period. Custom illustration fades behind it 40%. | Swell + chime | — |
| 2.6–3.8s | One-line oracle: "You bring the party. The game follows." Share buttons slide up from bottom. | Ambient bed continues | — |

### Mobile-first non-negotiables
- `100dvh` not `100vh` (mobile Safari URL bar collapse)
- Tap targets ≥56pt
- Bottom-anchored answers (thumb zone), top-anchored question
- Touch feedback on press (40ms scale-down), not release
- No keyboard mid-quiz — name capture AFTER reveal only
- No-scroll questions (each fits 100dvh on iPhone SE)
- Image tiles 16:9, object-fit: cover
- Swipe right = back; tap = forward (no swipe-forward, ever)
- `navigator.vibrate(8)` on every answer tap

### Visual primitives to use
- **Kitchen line / NVZ** — universal, use as divider/frame/progress
- **Paddle silhouette** — 1px outline as bullet/loader
- **Wiffle ball with holes** — NEVER a tennis ball
- **0-0-2 score format** — meme motif, never explained
- **Top-down court diagram** — underlay for archetype grid; each archetype lives in a court region

### Visuals to skip
- Third-shot-drop arc (too inside)
- Erne / ATP terminology (intermediates only)
- Kitchen-line argument meme (negative energy — off-brand)

### Anti-patterns to KILL
- "Congratulations!" / trophy emojis on reveal — never
- "Share to see your result" gate — never
- **Email-gate before result** — V2 had this, KILL
- Wall of text above the share button on result page
- Generic stock illustrations
- BuzzFeed snark (we're Co-Star + Wrapped + earnest hand-drawn editorial)
- Auto-playing music
- Truncated archetype names (max 3 words)

### Share-card spec (1080×1920)
```
0–220px      DEAD ZONE (IG username overlay)
220–520px    Brand mark + "PICKLEBALL ARCHETYPE" eyebrow
520–1100px   Hero archetype illustration (580px tall, centered, glowing)
1100–1280px  "The Festival." 120pt italic serif, white-on-color
1280–1480px  Oracle line, 32pt sans, 70% opacity
1480–1700px  Mini 8-cell archetype grid, your cell highlighted
1700–1920px  DEAD ZONE (IG reply bar) — URL footer at 1720px
```

Each archetype owns ONE 2-stop gradient. Background = 12% saturation, hero = full saturation. Personalize: if user enters name, eyebrow becomes "MIKE'S ARCHETYPE" (caps, letter-spaced) — drives 2-3x share rate.

### The "send to group chat" trigger
Compatibility reveal as second-screen post-archetype. Your cell glowing + your matches lit at 60% + opposites at 20%. Tap or drag a cell to see "play together verdict." Drives tagged shares (highest quality).

## Reconciling the conflicting research

Academic agent: 15 items minimum for reliability.
Viral agent: 6-8 questions or drop-off rises ~40%+.

**Resolution:** **10 questions perceived; 12-15 items scored.** Some screens carry 2 forced-choice items in one visual. Triggers (multi-select) and event-fit matrix do NOT count toward "question count" perceived by user (they're separate phases).

## What we're explicitly NOT doing in V3

- No login/account
- No paid tier yet (free-only V3, paid couples mode V4)
- No real-time matchmaking integration (just data capture for now)
- No video archetypes (audio reveal yes, video V4)
- No Spanish (V3.1)
- No commissioned illustrations day 1 (use SVG primitives we can ship today; commission illustrations sprint 2)
