<div align="center">

# RoundSense

**A post-match coach for CS2: not just what happened, but which part of the round you lost, what you could have chosen instead, and the one thing to watch next game.**

[简体中文](README.md) | **English**

Windows desktop app · parsed locally · free · Perfect World / 5E / CS2 matchmaking / FACEIT demos

[![Download](https://img.shields.io/github/v/release/dylanx1996/roundsense?label=download&style=flat-square&color=1ed4b3)](https://github.com/dylanx1996/roundsense/releases/latest)
![Platform](https://img.shields.io/badge/platform-Windows%2010%2F11-0f161d?style=flat-square)
![Anti-cheat](https://img.shields.io/badge/anti--cheat-reads%20demos%20only-22c55e?style=flat-square)

> **Language note:** RoundSense is fully available in English (pick it in the first-run guide or in Settings → Language & look). Callouts are the names English-speaking players use on each map. The screenshots below show the Chinese interface.

![Replay review](images/replay-review.png)

</div>

## Why RoundSense

Watching demos is tiring: twenty-odd rounds, dragging the timeline around looking for what you did wrong, and in the end you remember "lost the aim duel".

RoundSense turns it around: **it first tells you which part of the round lost it, then asks you about every decision in that part.**

- **On point.** Lost after the plant? The first card is the post-plant review: where the retake came from, who walked out into a long duel, how much time was left on the bomb when the last T fell, how many more seconds would have beaten the defuse. It won't tell you about a missing entry flash while you were already holding the bomb.
- **Fair.** Every call lists what it checked first: going out to stop a defuse, peeking together with a teammate, saving in a lost round… none of these are called mistakes. What was only known after the round (where enemies really were, how it ended) is marked *hindsight*: it explains, it isn't what the decision is judged on.
- **You think first.** *Coach questions* take you back to just before a decision with only what you knew then: unseen enemies, the round result and later kills are hidden. Pick what you would do, then see the coach's view.
- **Progress you can see.** Every decision counts as an opportunity, whatever the result. The progress page says "peeking while a man up: 51 chances, 32% could be better, fewer than in your earlier matches" — not "you made the mistake 3 more times".
- **Evidence for everything.** Every call comes from the demo data and deterministic rules; one click jumps to the moment. No AI and no internet needed.

## Coach questions: judge first, then see the coach's view

| Back to just before the decision, with only what you knew | After you answer: every option rated, your pick, what was done in the match |
|---|---|
| ![Coach question](images/quiz.png) | ![Answer](images/quiz-answer.png) |

11 kinds of decisions are checked, counted and asked:

| When | Question |
|---|---|
| After the plant (T holding) | Did this fight have to happen? · When the CT started defusing, did you use your molotov? |
| After the plant (CT retake) | Did you go in together? · Utility before going in? · Did the retake start early enough? |
| Any time | When a teammate went down, did you trade? · A man up, did you need to take this fight? · He just saw you — did you go out from the same spot again? · Utility before peeking an angle you knew was held? · In a round you can't win, did you keep the gun? |
| Attack | Going onto the site first, was there a flash for you? |

## Progress as a rate, not a mistake count

![Decisions](images/decisions.png)

- One row per question: how many chances, and how many could be better, were risky, were good, or weren't judged.
- A square per match; click it to jump to that match's first improvable moment.
- Earlier matches against recent ones: *improved / worse* at a glance; how often your answers agree with the coach shows too.

## Replay: the whole round on one screen

- **The side panel is ordered by the phase that decided the round**: that phase comes first, marked "decided here"; the others fold into one line.
- **A pinned player list**: health as the row background, armour / helmet, gun, the grenades still on each player, money; dead players struck through.
- **A phased timeline**: early → attack → after the plant, deaths and highlights above, the turning point and your problems below.
- **2D / 3D** from your CS2 install's radar and 1:1 map models: view cones, grenades, kill lines, smokes in their real shape (smoke putting out fires, HE blowing smokes open), flash white-out, the bomb; first person for you, the victim or the killer.
- **Three views**: the real truth / what your team knew / what you knew; hold a button for the truth.
- **The demo's in-game voice** plays in sync; your side or the enemy's only.
- **Open the moment in CS2** with one click.

## Death review: why did I die?

Every death's last duel is taken apart: who was ready first, how far off the crosshair was, reaction time, counter-strafing, hits, and whether a teammate could have traded (by how long he'd actually need to run, walls included). It ends with one main cause and what to do next time — and if the decision was fine and only the aim lost, it says so: keep playing like this, practise the aim.

## Learn how to play it

| Utility academy | Tactical academy |
|---|---|
| ![Utility academy](images/lineup.png) | ![Tactical academy](images/academy.png) |

- **Utility academy**: smokes, flashes, molotovs and HEs on all 9 competitive maps. The map shows the landing spots; click one for every throw that reaches it.
  - Each lineup: aim shot, landing, throw video (being added), overview; throw type, mouse button, extra keys, difficulty.
  - **Practice steps, one click each**: open the map, practice settings (the round never ends, buy anywhere, grenade trails, unlimited grenades), go to the throw spot, rethrow.
  - Sources: lineups the author tested in game, the game's own map guides, and common community spots.
- **Tactical academy**: 63 tactics on 9 maps — the goal, each position's job, the grenades — shown with real rounds from Major matches, explained step by step beside the replay.
- **Tactical board**: place players and grenades, draw routes, in steps; make one from any moment of a replay and share it.

| 3D replay (your CS2 install's map models) | Map library in free 3D |
|---|---|
| ![3D replay](images/replay-3d.png) | ![Map](images/map-3d.png) |

## More

| Feature | What it does |
|---|---|
| Auto import | Watches the Perfect World demo folder, CS2's `replays` and folders you add; or drag files in; a notification after each match |
| Match at a glance | Result, Rating, MVP, the one thing to fix, the round worth rewatching, the clip worth recording; copy it as an image |
| Round situation / defence | All 9 maps: what the attack was doing and missing, your better role; how the CTs set up, which area opened, who should have filled it |
| Map analysis | Death / kill heat maps, common angles, attack routes |
| Highlights | 3K+, clutches, knife kills, with the clip marked and opened in CS2 in one click |
| Training goals | Up to 3 goals, updated after every match |
| "This is wrong" | Disagree with a call? Mark it with a reason and it leaves every count; export it as an anonymous test case for the author, so the rule can't make that mistake again |

## Download

1. Get the latest `RoundSense-vX.Y.Z-win-x64-EN.zip` from [Releases](https://github.com/dylanx1996/roundsense/releases/latest) (`-CN.zip` is the same program starting in Chinese).
2. Unzip anywhere and run **`RoundSense.exe`** — no installer.
3. The first-run guide shows how to get your demos on each platform.

**Requirements**: Windows 10 / 11 (64-bit). Steam CS2 installed is recommended: radar images, map pictures and 3D maps are read from your own install; RoundSense ships no game assets. Without CS2 the analysis still works, without those pictures.

**Updating**: About → Check for updates, download the new zip and unzip it over the old folder. Your data lives in `%APPDATA%\RoundSense` and stays.

## Getting your demos

| Platform | How to download | Import |
|---|---|---|
| **Perfect World** | Client → match history → download demo | Automatic (`%APPDATA%\Wmpvp\demo` is watched) |
| **5E** | Client / website → match history → download demo | Add the download folder once; automatic after that |
| **CS2 matchmaking** | In game: Watch → Your matches → download | Automatic |
| **FACEIT / others** | Download `.dem` / `.dem.zst` / `.dem.gz` / `.zip` | Drag into the window, or put it in a watched folder |

## Safety and privacy

- **Never touches the game**: it reads demo files and the map assets in your CS2 folder. No memory reading, no injection, no packet capture, nothing shown during a match — nothing to do with VAC or anti-cheat.
- **Offline by default**: demos, analyses and history stay on your PC. Only "check for updates" (or the daily check you can turn on) asks GitHub for the latest version number, sending nothing.
- **AI is optional**: nothing needs it. Turned on, it gets only the structured data of the analysis — no demo, file paths or account data.

## Feedback and support

- Problems or ideas: About → Report a problem opens a filled-in issue in your browser, or [open an issue](https://github.com/dylanx1996/roundsense/issues/new).
- About → Support the author. Everything stays free whether you support or not; supporters get a purely cosmetic pack: their own CT / T player models in the 3D replay, a holographic supporter card, 4 limited themes, a glowing title-bar name and a share-image frame.

## Licence

RoundSense is free to download and use; the source is not published. Terms in [LICENSE.md](LICENSE.md), third-party components in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

© 2026 dylan su. Counter-Strike and CS2 are trademarks of Valve Corporation. Not affiliated with Valve, Perfect World or 5EPlay.
