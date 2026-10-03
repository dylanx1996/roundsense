<div align="center">

# RoundSense

**A post-match coach for CS2: turns your match demo into evidence, and the evidence into one thing to fix next game.**

[简体中文](README.md) | **English**

Windows desktop app · parsed locally · free · Perfect World / 5E / CS2 matchmaking / FACEIT demos

[![Download](https://img.shields.io/github/v/release/dylanx1996/roundsense?label=download&style=flat-square&color=1ed4b3)](https://github.com/dylanx1996/roundsense/releases/latest)
![Platform](https://img.shields.io/badge/platform-Windows%2010%2F11-0f161d?style=flat-square)
![Anti-cheat](https://img.shields.io/badge/anti--cheat-reads%20demos%20only-22c55e?style=flat-square)

> **Language note:** the interface is in Simplified Chinese for now. English, Japanese and Russian are planned.

![Overview](images/overview.png)

</div>

## What it does

After a match, give it the demo. It answers:

1. **How did it go?** A one-glance match summary: score, Rating, MVP, the one thing to fix, the round worth rewatching, the clip worth recording.
2. **Why did I die?** Every death's last duel is taken apart:
   - who was ready first;
   - how far off the crosshair was;
   - reaction time;
   - counter-strafing;
   - whether anyone could have traded, counted as the time a teammate needs to run there, not through walls.

   You get one main cause and what to do next time.
3. **What should I have been doing?** On all eight competitive maps (Mirage, Dust2, Inferno, Nuke, Overpass, Ancient, Anubis, Train), round situations and CT setups show:
   - what the team was executing and what was missing;
   - which role made sense for you, and what you actually did.
4. **How is a tactic played?** The tactical academy (57 tactics on eight maps) explains each tactic and plays a pro round of it beside the text: Budapest Major 2025 and Cologne Major 2026 games.
5. **What keeps going wrong?** Across matches, compared with the other nine players in each lobby, split into aim, duels, teamwork, utility and survival. Training goals track your progress every match.

Every conclusion comes from demo data and a deterministic rule engine, with evidence you can click to jump to that moment. Mark a finding as wrong and it leaves your stats. The AI coach is optional; everything works without an API key.

| Tactic walkthrough (pro example) | 3D replay (your local CS2 map model) |
|---|---|
| ![Replay](images/replay-lesson.png) | ![3D replay](images/replay-3d.png) |

| Tactical academy | Tactical board |
|---|---|
| ![Academy](images/academy.png) | ![Board](images/board.png) |

| Map library: free 3D camera, with the 3D skybox |
|---|
| ![Map](images/map-3d.png) |

## Download

1. Get the latest `RoundSense-vX.Y.Z-win-x64.zip` from [Releases](https://github.com/dylanx1996/roundsense/releases/latest).
2. Unzip anywhere and run **`RoundSense.exe`**; no installer needed.

**Requirements:** Windows 10 / 11 (64-bit). A Steam CS2 install is recommended: radar images, map pictures and 3D maps are read from it, and no game assets are distributed with this app.

## Safety and privacy

- **Never touches the game process.** It reads demo files and map assets from your CS2 folder only. It doesn't read memory, inject anything or capture traffic, and it shows nothing during a match.
- **Offline by default.** Everything stays on your PC. It only asks GitHub for the latest version number when you click "check for updates" or turn on the daily check.
- **AI is optional.** If enabled, only the structured facts of the analysis are sent, never the demo, file paths or account info.

## Feedback

[Open an issue](https://github.com/dylanx1996/roundsense/issues/new), or use 关于 → 反馈问题 in the app.

## License

RoundSense is free to download and use. The source code is not public. See [LICENSE.md](LICENSE.md) and [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

© 2026 dylan su. Counter-Strike and CS2 are trademarks of Valve Corporation. This project is not affiliated with Valve, Perfect World or 5EPlay.
