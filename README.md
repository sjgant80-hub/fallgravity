# FallGravity

**LinkedIn algorithm strategy tool. The algorithm is blind to quality — so play by its rules and flip the game.**

One HTML file. Opens on your phone. No LinkedIn API. No automation. No bot. Just the playbook.

**Live:** https://sjgant80-hub.github.io/fallgravity/

---

## What it does

| Feature | What it does | Why it matters |
|---------|-------------|----------------|
| **α post scorer** | 8-dimension live score /80 as you type | Catches algo-killers before you publish |
| **Hook generator** | 5 hook types per topic (story · reveal · problem · question · paradox) | Only the first 2 lines show in the feed |
| **Format advisor** | Recommends text · carousel · document · poll · image · video | Carousel = +20-40% reach vs text-only |
| **Carousel builder** | Draft → 5/7/10 slides | One-tap conversion |
| **β timing windows** | Tue–Thu 07:00–08:30 GMT · 14:00–15:00 GMT | Optimal slots for UK/US professional audience |
| **γ boost coordinator** | 90-minute window countdown + engagement targets | The 90 minutes that decide whether you reach 500 or 50,000 |
| **δ comment responder** | 3 reply suggestions per comment (depth · casual · technical) | Your replies count more than reactions |
| **ε analytics** | Manual log + auto-detected insights | Learns what works for *your* audience |
| **Guild** | Roster of mutual supporters with topic affinity | γ only alerts members whose affinity matches the post |

---

## The rules it plays by

```
FIRST 60 MINUTES = the kill zone
  engagement velocity in first hour determines whether you reach 500 or 50,000

DWELL TIME
  pattern interrupts, line breaks, lists, em-dashes force the scroll to stop

COMMENTS > REACTIONS
  long comments (50+ words) count more
  your replies count MOST (signals conversation)
  3+ deep threads trigger "show more" which = more views

SAVES = highest quality signal
  LinkedIn shows saved posts to similar audiences

PENALTIES
  external links in body         -30% to -50%
  editing within 10 mins         distribution reset
  hashtag spam (>5)              slight
  posting 2× in 24h              cannibalisation

REWARDS
  carousel/document              +20-40% reach
  polls                          massive reach (low quality)
  video                          rewarded if >50% watched
  "see more" clicks              the post was compelling enough to expand
  native images > link previews
```

---

## How to use (Simon's workflow)

1. **Draft on Compose** — the score updates live as you type
2. **Run hook generator** — pick from 5 types (story · reveal · problem · question · paradox)
3. **Check format advice** — if it suggests carousel, tap "Convert to carousel"
4. **Check anti-pattern flags** — external link warning, hashtag count, etc.
5. **Publish on LinkedIn** (FallGravity doesn't post for you — that violates ToS and kills accounts)
6. **Paste post URL into Boost view** — starts 90-min countdown
7. **Tap "Alert guild"** — broadcasts via `fall-signal` to guild members whose affinity matches your post topic
8. **As comments come in** — paste each into the Comment Responder, get 3 reply suggestions, ship the best one
9. **Track engagement targets live** — comments / reactions / threads against minimum/good/great thresholds
10. **After the 90 minutes** — log the post in Analytics → ε starts learning what works

---

## What FallGravity will NEVER do

- ❌ Auto-post or schedule (LinkedIn ToS violation → account ban)
- ❌ Auto-comment with fake engagement
- ❌ Like-for-like / engagement pods
- ❌ Tag people who didn't ask
- ❌ Edit your post for you
- ❌ Hit the LinkedIn API

This is a **strategy tool**, not an automation tool. You publish. You engage. FallGravity tells you *when*, *how*, and *what* — so you don't burn reach on avoidable mistakes.

---

## Sovereignty

- All data on your device (localStorage)
- Post history, guild roster, analytics, drafts — never leave your phone
- Export JSON anytime · restore anytime
- No telemetry · no signup · no subscription
- Works fully offline (T0 templates always available)
- Optional AI keys for sharper output (T3 cascade) — direct from your device to provider, no middleman

---

## How it's built (for developers)

### Architecture

- **Single HTML file** — ~80 KB, no build step, no deps
- **Vanilla JS** — no framework
- **localStorage** for persistence
- **BroadcastChannel** `fall-signal` for guild alerts + mesh interop (prime 199)
- **Konomi licence shim** baked in (sovereign tier)
- **Cascade** — T0 templates → T1 WebLLM → T2 Ollama local → T3 (Claude / GPT / Gemini / OpenRouter)

### 7-layer breakdown (v19 spec)

| Ring | Role | Implementation |
|------|------|----------------|
| L1 FACE | 5 views | Compose · Boost · Carousel · Analytics · Guild |
| L2 SWARM | Ω + 5 agents | α scorer/hooks · β timing · γ boost · δ replies · ε analytics |
| L3 CASCADE | T0 always | scoring + templates · T3 optional for AI |
| L4 BLOOM | routing | topic keywords → guild affinity matching |
| L5 PERSIST | localStorage | posts · guild · boost state · carousels · KCC |
| L6 SKIN | mobile-first | dark `#1a1a17` + gold `#d4a017` · one-thumb |
| L7 ASS | helpful empty | "Paste a draft to get scored" — no setup wizard |

### postMessage API (for other Fall* tools)

```js
window.postMessage({ target: 'fallgravity', action: 'score', text: '...' }, '*');
// → {data: {total, breakdown[], flags}}

window.postMessage({ target: 'fallgravity', action: 'hooks', topic: '...' }, '*');
// → {data: [{type, text}, ...]}
```

### Fork & rebrand

```bash
gh repo fork sjgant80-hub/fallgravity --clone=true
cd fallgravity
# Update state.settings defaults in index.html for your name/profile
gh repo edit --enable-pages --pages-branch main
```

---

## Roadmap

- ✅ Live post scorer (8 dimensions)
- ✅ Hook generator (5 types, T0 + T3)
- ✅ Format advisor
- ✅ Carousel builder (text → slides, T0 + T3)
- ✅ Boost window with engagement targets
- ✅ Comment responder
- ✅ Timing windows (UK/US)
- ✅ Guild roster + topic-matched alerts via fall-signal
- ✅ Manual analytics + ε insights
- ⬜ Slide → PNG export (Canvas rendering)
- ⬜ A/B hook testing (track which hook type converts best for you)
- ⬜ Comment thread depth visualisation
- ⬜ Browser extension for in-LinkedIn-feed scoring (paste-free)

---

## Licence

MIT — see [LICENSE](LICENSE). Use it, fork it, customise the templates for your voice.

---

## Credit

- **Architecture & build:** Simon Gant · [@sjgant80-hub](https://github.com/sjgant80-hub) · [LinkedIn](https://www.linkedin.com/in/simon-gant-295b56180/)

◊·κ=1 · the algorithm is blind to quality · exploit the blindness · 90 minutes is the kill zone · the hook is everything · the reply outperforms the reaction · the link goes in the comment · the tool that games the game · sovereign · one file
