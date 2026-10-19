# Third-Party Notices

**English** | [简体中文](THIRD_PARTY_NOTICES.zh-CN.md)

RoundSense (Copyright © 2026 Dylan Su. All rights reserved.) **does not copy source code from any third-party repository**. The tables below list the libraries used as npm dependencies or shipped as programs, and the material used only as a format reference or for study. Licences are checked against the exact version when a component is added, and again before each release.

Supplied with the application (in `resources/legal/` in the installation folder, and under About → Agreements & privacy): this notice, its Chinese version `THIRD_PARTY_NOTICES.zh-CN.md`, and `THIRD_PARTY_LICENSES.txt`, which contains the full licence texts of every component shipped with the application or bundled into its interface and is generated from the installed packages at every build. The Electron and Chromium licences are `LICENSE.electron.txt` and `LICENSES.chromium.html` in the installation folder. Third-party components are licensed under their own terms; the RoundSense End User Licence Agreement does not restrict the rights those licences grant.

## Runtime components (shipped with the application)

| Project | URL | Licence | Version | What it is used for | Code copied? | Modified? | Attribution required? |
|---|---|---|---|---|---|---|---|
| demoparser2 (`@laihoe/demoparser2` + `-win32-x64-msvc`) | https://github.com/LaihoE/demoparser | MIT | 0.42.0 (the npm JavaScript wrapper) + a native module we build ourselves from tag v0.42.0 with upstream PRs #363 and #361 | Parsing CS2 `.dem` files: events, tick data, player state | No (only upstream pull requests are applied; no parsing code of our own) | Yes: a fix for 14-bit entity handles, see `vendor/demoparser2/README.md` | Yes: full licence text in `THIRD_PARTY_LICENSES.txt` (the upstream text, from `vendor/demoparser2/LICENSE-demoparser.txt`) |
| Anthropic TypeScript SDK (`@anthropic-ai/sdk`) | https://github.com/anthropics/anthropic-sdk-typescript | MIT | 0.128.0 | Optional Claude AI coaching requests | No | No | Yes: licence text supplied with the application |
| json-schema-to-ts / @babel/runtime / ts-algebra / standardwebhooks / @stablelib/base64 | (dependencies of the SDK) | MIT | See package-lock.json | Used inside the SDK | No | No | Yes: licence text supplied with the application |
| fast-sha256 | https://github.com/dchest/fast-sha256-js | Unlicense | 1.3.0 | Used inside the SDK | No | No | No (Unlicense) |
| Electron | https://github.com/electron/electron | MIT (Chromium and its components: see `LICENSES.chromium.html`) | 44.4.5 | Desktop shell | No | No | Yes: licence text supplied with the application |
| React / React DOM | https://github.com/facebook/react | MIT | 19.3.0 | User interface (bundled into the renderer) | No | No | Yes: licence text supplied with the application |
| three.js | https://github.com/mrdoob/three.js | MIT | 0.186 | 3D replay (including OrbitControls; bundled into the renderer) | No | No | Yes: licence text supplied with the application |
| electron-updater | https://github.com/electron-userland/electron-builder | MIT | 6.8.9 | In-place updates of the installed version: downloads the new installer from the public releases page, checks its SHA-512 and installs it on restart | No | No | Yes: licence text supplied with the application |
| builder-util-runtime / lazy-val / lodash.escaperegexp / lodash.isequal / fs-extra / jsonfile / universalify / tiny-typed-emitter / debug / ms / js-yaml | (dependencies of electron-updater) | MIT | 9.7.0 / 1.0.5 / 4.1.2 / 4.5.0 / 10.1.0 / 6.2.1 / 2.0.1 / 2.1.0 / 4.4.3 / 2.1.3 / 4.3.2 | Used inside electron-updater | No | No | Yes: licence text supplied with the application |
| semver / graceful-fs | (dependencies of electron-updater) | ISC | 7.7.4 / 4.2.11 | Used inside electron-updater | No | No | Yes: licence text supplied with the application |
| sax | (dependency of electron-updater) | BlueOak-1.0.0 | 1.6.1 | Used inside electron-updater | No | No | Yes: licence text supplied with the application |
| argparse | (dependency of js-yaml) | Python-2.0 | 2.0.1 | Used inside js-yaml | No | No | Yes: licence text supplied with the application |
| seek-bzip | https://github.com/cscott/seek-bzip | MIT | 2.0.0 | Decompressing Valve matchmaking `.dem.bz2` files | No | No | Yes: licence text supplied with the application |
| Node.js built-in `zlib` (with zlib and Zstandard; part of Electron, not a separate dependency) | https://github.com/nodejs/node | Node.js: MIT; zlib: zlib License; Zstandard: BSD-3-Clause | Node 24.21.0 in Electron 44.4.5 (zlib 1.3.2.1-motley, zstd 1.6.0) | Decompressing `.zip`, `.dem.gz` and FACEIT `.dem.zst` files | No | No | Yes: supplied with Electron's licence files |
| csgove (the csgo-voice-extractor program) | https://github.com/akiver/csgo-voice-extractor | MIT | v3.1.6 (commit dcb37fc, release `win32-x64.zip`) | Extracting the recorded voice from demos, run as a separate program | No (the unmodified release binary `vendor/csgove/csgove.exe`, SHA-256 `57041d72…070db4a8`) | No | Yes: `vendor/csgove/LICENSE-csgove.txt` shipped with the application |
| libopus (`opus.dll` from the same release) | https://github.com/xiph/opus | BSD-3-Clause | xiph/opus as built for csgove v3.1.6 | Used by csgove to decode Opus voice | No (unmodified binary, SHA-256 `f81646ea…1d817ed76d8`) | No | Yes: `vendor/csgove/COPYING-opus.txt` shipped with the application |
| Go libraries statically linked into csgove | See csgove's go.mod | demoinfocs-golang, hraban/opus, and markus-wa's gobitread, go-unassert, godispatch, ice-cipher-go and quickhull-go: MIT; go-audio/wav, audio and riff, golang/geo, oklog/ulid: Apache-2.0; youpy/go-wav and go-riff: ISC; golang/snappy, protobuf-go, zaf/g711 and the Go standard library: BSD-3-Clause; pkg/errors: BSD-2-Clause | As above | Used inside csgove | No | No | Yes: the full Apache-2.0 text `vendor/csgove/LICENSE-Apache-2.0.txt` is shipped with the application |

## Build tools (not shipped with the application)

| Project | Licence | Version |
|---|---|---|
| electron-vite | MIT | 5.0.0 |
| Vite | MIT | 7.3.6 |
| @vitejs/plugin-react | MIT | 5.2.0 |
| TypeScript | Apache-2.0 | 7.0.2 |
| electron-builder | MIT | 26.15.3 |

## Used only as reference (no code copied)

| Source | Licence | How it was used |
|---|---|---|
| Valve Developer Wiki — VPK File Format | Public documentation | The VPK v2 directory reader in `src/core/cs2assets.ts` is our own implementation of the published format |
| ValveResourceFormat (https://github.com/ValveResourceFormat/ValveResourceFormat) | MIT | Consulted for the `.vtex_c` header fields and `VTexFormat` values (BGRA8888 = 28), the block layout of binary KV3 v5 (`BinaryKV3`) and the field names of Rubikon physics data (`PhysAggregateData`: `m_parts / m_rnShape / m_hulls / m_meshes`). The decoding code is our own |
| cs2-phys-extractor / Awpy (https://github.com/pnxenopoulos/awpy) | MIT | Only the idea of extracting collision triangles from world_physics for visibility; no code copied |
| ValveResourceFormat NavMesh (commit `b20af38`, `ValveResourceFormat/NavMesh/*.cs`) | MIT | Consulted for the field order of `.nav` versions 31–36 (polygon table, movable meshes, the KV3 block embedded in version 36, area connections). The parser in `src/core/nav.ts` is our own |
| Awpy `awpy/nav.py` (commit `94f3571`) | MIT | Cross-checked against for the `.nav` area layout (versions 30–35); no code copied |
| Mikko Mononen, "Simple Stupid Funnel Algorithm" (a public article by the author of Recast/Detour) | Public article | The path straightening in `nav.ts` is our own implementation of the algorithm described |
| "CS2 Map Callouts" V4.0 (Bilibili user 慕容灬小飛, bilibili.com/opus/962952275040403475) | All rights reserved by the author; no reposting | Only the callout names and their positions on the maps were consulted (converted into game coordinates in `SPOTS` in `maps.ts`); the images were not copied, stored or distributed |
| meshoptimizer (Arseny Kapoulkine; `examples/jsm/libs/meshopt_decoder` / `meshopt_simplifier` shipped with three.js 0.186) | MIT | `worldmesh.ts` uses it to decode map render meshes (CS2 compresses vertices and indices with meshoptimizer) and to simplify triangles; bundled together with three.js under the same licence |
| ValveResourceFormat: meshes (MDAT/CTRL), world nodes (vwnod), materials (KV3 v2–v4), texture mip layout | MIT | Consulted for field names and layout; `worldmesh.ts` / `kv3.ts` are our own implementations |
| BC1 / BC7 block compression formats (Microsoft Direct3D 11 specification) | Public specification | `worldmesh.ts` decodes only the colour of a texture's smallest mip; our own implementation |
| MurmurHash2 (Austin Appleby) | Public domain | Implemented in `mapgeo.ts` to match the hashed surface material names in collision models (Source 2 uses the seed 0x31415926, as documented by ValveResourceFormat, MIT) |
| `@cs2dak/core` 2.0.2 `mechanics.ts` (npm) | MIT | Consulted for the **definitions** of three metrics — counter-strafe success, reaction time and pre-aim (how shot strings are split, the speed before running, the exclusion rules for reaction time). The implementation is our own |
| LZ4 Block Format specification (https://github.com/lz4/lz4) | BSD-2-Clause (the specification) | `lz4Block()` is our own implementation of the published specification |
| CS Demo Manager / cs2-demo-opener / cs2-demo-viewer / Awpy / CounterStrafe | MIT | Only product and architecture ideas (per-round chunks, view cones, kill lines and the like); no code copied |
| CS-Demo-Downloader (https://github.com/WangChuDi/CS-Demo-Downloader) | MIT (but fetching from Perfect World depends on its closed-source signing module) | Researched only, not used |
| CS2 Meta Engine / PerfectWorld-API-Collection | No clear licence | Not used; no code consulted |

## Evaluated, not used

| Project | Version (npm, 2026-09-29) | Licence | Outcome |
|---|---|---|---|
| cs2-demo-format | 3.1.0 | MIT | Not adopted for now |
| @cs2dak/contract / @cs2dak/core / @cs2dak/maps | 1.1.0 / 2.0.2 / 1.0.0 | MIT | Not adopted: `@cs2dak/core` depends on `@rivalhub/rival-rating`, whose licence was not checked, and `@cs2dak/maps` may contain Valve map images |
| DAK Studio (apps/dak-studio) | — | AGPL-3.0-only | Studied only; no code copied |

## Valve content

RoundSense is independently developed third-party review software and has no affiliation with, sponsorship by, licence from or endorsement by Valve Corporation. Counter-Strike and the related names, trademarks and game assets belong to their respective owners. "Read at run time and not distributed with the application" below describes only **how** this content is used; it **does not mean** that Valve has licensed that use. Users are responsible for obtaining and using CS2 and its assets lawfully.

- The 3D maps are built from `world_physics.vmdl_c` (the collision model) in `maps/<map>.vpk`, **read at run time, read-only, from the user's own CS2 installation**; once decoded it is used only in memory, never written to disk and not distributed with the application. Colours come from the surface material of each face in the same collision model (concrete, wood and so on), with a palette of our own; no game textures are used.
- Teammates' running distances use the navigation mesh `maps/<map>.nav` from the same VPK, likewise read at run time, used only in memory and not distributed.
- Radar images and the map coordinate transforms (`resource/overviews/*.txt`, `panorama/images/overheadmaps/*_radar_psd.vtex_c`) are **read at run time, read-only, from the user's own CS2 installation** and are not distributed.
- The map pictures in the match list are the game's own map previews (`panorama/images/map_icons/screenshots/360p/<map>_png.vtex_c`, embedded PNG), likewise read at run time, used only in memory and not distributed.
- The fallback Mirage coordinates in `src/core/maps.ts` (`pos_x -3230 / pos_y 1713 / scale 5`) are numerical facts, used only when no CS2 installation is found.
- The positions, angles and landing points in the Utility Academy (`src/core/lineups*.ts`) are numerical facts: for Mirage they are the author's own measurements in the game, for the other maps real throws taken from professional match demos; the descriptions are our own.
- The "official" lineups in the Utility Academy come from the map guides built into the game (`annotations/official/<map>/` in `pak01_dir.vpk`), **read at run time, read-only, from the user's own CS2 installation**, used only in memory and not distributed; their text is Valve's original wording, shown unchanged.
- The lineup screenshots shipped with the application (`data/lineup-shots/`) were taken by the author in the author's own copy of the game; they are not resources extracted from the game files.
- The csgove release also contains Valve's `tier0.dll` and `vaudio_celt.dll` (used for the old CS:GO voice format). We **do not copy or distribute** them: CS2's Opus voice does not need them, and since csgove only checks that the files exist, two empty files take their place at run time.

## Professional match example data (data/pro)

Position and event data extracted from publicly available match demos (no demo files and no game assets), used for the examples in the Tactics Academy:

- BLAST.tv Austin Major 2025, semi-final MOUZ vs Vitality: several rounds on Train. Source: https://www.hltv.org/matches/2382618/mouz-vs-vitality-blasttv-austin-major-2025
- StarLadder Budapest Major 2025, stage 3 Passion UA vs Liquid: several rounds on Train. Source: https://www.hltv.org/matches/2388112/passion-ua-vs-liquid-starladder-budapest-major-2025
- StarLadder Budapest Major 2025, semi-final Spirit vs Vitality: several rounds on Dust2 and Mirage. Source: https://www.hltv.org/matches/2388128/spirit-vs-vitality-starladder-budapest-major-2025
- IEM Cologne Major 2026, stage 3 Spirit vs 9z: several rounds on Overpass. Source: https://www.hltv.org/matches/2394986/spirit-vs-9z-iem-cologne-major-2026
- IEM Cologne Major 2026, semi-final Spirit vs Falcons: several rounds on Anubis. Source: https://www.hltv.org/matches/2395001/iem-cologne-major-2026-semi-final-2-iem-cologne-major-2026
- PGL CS2 Major Copenhagen 2024, quarter-final Spirit vs FaZe: several rounds on Vertigo. Source: https://www.hltv.org/matches/2370722/spirit-vs-faze-pgl-cs2-major-copenhagen-2024
- IEM Cologne Major 2026, grand final Falcons vs FURIA: several rounds on Anubis. Source: https://www.hltv.org/matches/2395002/iem-cologne-major-2026-grand-final-iem-cologne-major-2026
- StarLadder Budapest Major 2025, semi-final FaZe vs NAVI: several rounds on Ancient and Nuke. Source: https://www.hltv.org/matches/2388129/starladder-budapest-major-2025-semi-final-2-starladder-budapest-major-2025
- StarLadder Budapest Major 2025, quarter-final NAVI vs FURIA: several rounds on Train. Source: https://www.hltv.org/matches/2388127/furia-vs-natus-vincere-starladder-budapest-major-2025
- IEM Cologne Major 2026, quarter-final G2 vs Spirit: several rounds on Overpass. Source: https://www.hltv.org/matches/2394998/match
- StarLadder Budapest Major 2025, grand final Vitality vs FaZe: several rounds on Inferno. Source: https://www.hltv.org/matches/2388130/vitality-vs-faze-starladder-budapest-major-2025

## Community lineup positions (src/core/lineups-community.ts)

- **GO NADE** (https://gonade.app), collected on 10 October 2026: each lineup's position (setpos), aim angles (setang), throw technique, mouse button, extra keys, side and difficulty, and the landing point on the radar (converted into game coordinates). These are factual data, for players to verify in the game themselves.
- Its images, videos, lineup names and descriptions were **not copied**; the names, callouts and descriptions in the application are generated by us, and screenshots are taken by players in their own game.
- The application no longer labels these lineups "community" or shows their source; each description says what the lineup does, and lineups without a throw video are marked "to be verified". If GO NADE does not agree to this use, the data will be removed.
