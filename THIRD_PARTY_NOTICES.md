# Third-Party Notices

本项目**没有复制任何第三方仓库的源代码**。下表列出通过 npm 依赖使用的库，以及仅作为格式参考/学习的资料（roadmap v2 §58）。License 在引入时按具体版本核对；发布前需要再核一次。

## 运行时依赖（随应用分发）

| Project | URL | License | Version | What we use | Copied code? | Modified? | Attribution required? |
|---|---|---|---|---|---|---|---|
| demoparser2 (`@laihoe/demoparser2` + `-win32-x64-msvc`) | https://github.com/LaihoE/demoparser | MIT | 0.42.0（npm 的 JS 外壳）+ 自己编译的原生模块：tag v0.42.0 + PR #363 + PR #361（ADR-0028） | 解析 CS2 `.dem`：事件、tick 数据、玩家状态 | 否（只挑入上游 PR，没有自己写的解析代码） | 是：修复 14 位实体句柄，见 `vendor/demoparser2/README.md` | 是：`vendor/demoparser2/LICENSE-demoparser.txt` 随应用分发 |
| Anthropic TypeScript SDK (`@anthropic-ai/sdk`) | https://github.com/anthropics/anthropic-sdk-typescript | MIT | 0.128.0 | 可选的 Claude AI 教练调用 | 否 | 否 | 是：随应用保留 License 文本 |
| json-schema-to-ts / @babel/runtime / ts-algebra / standardwebhooks / @stablelib/base64 | (SDK 传递依赖) | MIT | 见 package-lock.json | SDK 内部 | 否 | 否 | 是：随应用保留 License 文本 |
| fast-sha256 | https://github.com/dchest/fast-sha256-js | Unlicense | 1.3.0 | SDK 内部 | 否 | 否 | 否（Unlicense） |
| Electron | https://github.com/electron/electron | MIT（Chromium 等组件见 `LICENSES.chromium.html`） | 44.4.5 | 桌面外壳 | 否 | 否 | 是：随应用保留 License 文本 |
| React / React DOM | https://github.com/facebook/react | MIT | 19.3.0 | UI（打包进 renderer） | 否 | 否 | 是：随应用保留 License 文本 |
| three.js | https://github.com/mrdoob/three.js | MIT | 0.186 | 3D 战术重构（含 OrbitControls，打包进 renderer） | 否 | 否 | 是：随应用保留 License 文本 |
| seek-bzip | https://github.com/cscott/seek-bzip | MIT | 2.0.0 | 解压 Valve 官匹 `.dem.bz2` | 否 | 否 | 是：随应用保留 License 文本 |
| csgove（csgo-voice-extractor 的程序） | https://github.com/akiver/csgo-voice-extractor | MIT | v3.1.6（commit dcb37fc，release `win32-x64.zip`） | 从 Demo 里取出录到的语音（ADR-0025），作为独立程序调用 | 否（原样的发布版二进制 `vendor/csgove/csgove.exe`，SHA-256 `57041d72…070db4a8`） | 否 | 是：`vendor/csgove/LICENSE-csgove.txt` 随应用分发 |
| libopus（同一个发布包里的 `opus.dll`） | https://github.com/xiph/opus | BSD-3-Clause | csgove v3.1.6 构建时的 xiph/opus | csgove 用它解码 Opus 语音 | 否（原样二进制，SHA-256 `f81646ea…1d817ed76d8`） | 否 | 是：`vendor/csgove/COPYING-opus.txt` 随应用分发 |
| csgove 静态链接的 Go 库 | 见 csgove 的 go.mod | demoinfocs-golang / hraban/opus / markus-wa 的 gobitread、go-unassert、godispatch、ice-cipher-go、quickhull-go：MIT；go-audio/wav、audio、riff，golang/geo，oklog/ulid：Apache-2.0；youpy/go-wav、go-riff：ISC；golang/snappy、protobuf-go、zaf/g711、Go 标准库：BSD-3-Clause；pkg/errors：BSD-2-Clause | 同上 | csgove 内部 | 否 | 否 | 是：Apache-2.0 全文 `vendor/csgove/LICENSE-Apache-2.0.txt` 随应用分发 |

## 构建工具（不随应用分发）

| Project | License | Version |
|---|---|---|
| electron-vite | MIT | 5.0.0 |
| Vite | MIT | 7.3.6 |
| @vitejs/plugin-react | MIT | 5.2.0 |
| TypeScript | Apache-2.0 | 7.0.2 |
| electron-builder | MIT | 26.15.3 |

## 仅作为资料参考（未复制代码）

| Source | License | 用途 |
|---|---|---|
| Valve Developer Wiki — VPK File Format | 公开文档 | `src/core/cs2assets.ts` 中的 VPK v2 目录读取按公开格式说明自行实现 |
| ValveResourceFormat (https://github.com/ValveResourceFormat/ValveResourceFormat) | MIT | 参考了 `.vtex_c` 头部字段与 `VTexFormat` 枚举值（BGRA8888=28）、二进制 KV3 v5 的块布局（`BinaryKV3`）以及 Rubikon 物理数据的字段名（`PhysAggregateData`：`m_parts / m_rnShape / m_hulls / m_meshes`）。解码代码为自行编写 |
| cs2-phys-extractor / Awpy (https://github.com/pnxenopoulos/awpy) | MIT | 只学习了"从 world_physics 提取碰撞三角形做可见性"的思路，未复制代码 |
| ValveResourceFormat NavMesh（commit `b20af38`，`ValveResourceFormat/NavMesh/*.cs`） | MIT | 参考了 `.nav` 第 31–36 版的字段顺序（多边形表、可移动网格、第 36 版内嵌 KV3 块、区域连接）。`src/core/nav.ts` 的解析代码为自行编写 |
| Awpy `awpy/nav.py`（commit `94f3571`） | MIT | 对照参考 `.nav` 区域布局（第 30–35 版），未复制代码 |
| Mikko Mononen, "Simple Stupid Funnel Algorithm"（Recast/Detour 作者的公开文章） | 公开文章 | `nav.ts` 的路线拉直按文章描述的算法自行实现 |
| 《CS2地图点位报点大全》V4.0（B 站慕容灬小飛，bilibili.com/opus/962952275040403475） | 原作者保留权利，禁止转载 | 只参考了报点名和它们在图上的位置（换算成游戏坐标写在 `maps.ts` 的 `SPOTS`）；图片没有复制、保存或分发（ADR-0022） |
| meshoptimizer（Arseny Kapoulkine，随 three.js 0.186 的 `examples/jsm/libs/meshopt_decoder` / `meshopt_simplifier`） | MIT | `worldmesh.ts` 用它解码地图渲染网格（CS2 用 meshoptimizer 压缩顶点/索引）并简化三角形；随 three.js 一起打包，License 同 three.js |
| ValveResourceFormat：网格（MDAT/CTRL）、世界节点（vwnod）、材质（KV3 v2–v4）、贴图 mip 布局 | MIT | 参考了字段名和布局，`worldmesh.ts` / `kv3.ts` 自行实现 |
| BC1 / BC7 块压缩格式（Microsoft Direct3D 11 规范） | 公开规范 | `worldmesh.ts` 只解码贴图最小一级 mip 的颜色，自行实现 |
| MurmurHash2（Austin Appleby） | 公有领域 | `mapgeo.ts` 自行实现，用来匹配碰撞模型里表面材质名的哈希（Source 2 用种子 0x31415926，做法参考 ValveResourceFormat，MIT） |
| `@cs2dak/core` 2.0.2 `mechanics.ts`（npm） | MIT | 参考了急停成功率、反应时间、预瞄三个指标的**定义**（射击串切分、跑动前速度、反应时间的剔除条件）。实现为自行编写，见 ADR-0007 补充 |
| LZ4 Block Format 规范 (https://github.com/lz4/lz4) | BSD-2-Clause（规范文档） | `lz4Block()` 按公开规范自行实现 |
| CS Demo Manager / cs2-demo-opener / cs2-demo-viewer / Awpy / CounterStrafe | MIT | 只学习了产品与架构思路（按回合分块、视野锥、击杀线等），未复制代码 |
| CS-Demo-Downloader (https://github.com/WangChuDi/CS-Demo-Downloader) | MIT（但完美平台取数依赖其闭源签名模块） | 只调研，未使用。见 docs/decisions/ADR-0006 |
| CS2 Meta Engine / PerfectWorld-API-Collection | 无明确 License | 未使用、未参考代码 |

## 评估过、暂未使用（见 docs/decisions/ADR-0007）

| Project | Version（npm, 2026-09-29） | License | 结论 |
|---|---|---|---|
| cs2-demo-format | 3.1.0 | MIT | 暂不采用；Phase 2 做对照试验 |
| @cs2dak/contract / @cs2dak/core / @cs2dak/maps | 1.1.0 / 2.0.2 / 1.0.0 | MIT | 暂不采用；`@cs2dak/core` 依赖 `@rivalhub/rival-rating`（License 未核），`@cs2dak/maps` 可能包含 Valve 地图图片（需核授权） |
| DAK Studio（apps/dak-studio） | — | AGPL-3.0-only | 只能学习，不复制代码 |

## Valve 资产

- 3D 地图在**运行时从用户本机的 CS2 安装目录只读读取** `maps/<map>.vpk` 中的 `world_physics.vmdl_c`（碰撞模型），解码后只在内存中使用，不写盘、不随应用分发。颜色来自同一份碰撞模型里每个面的表面材质（混凝土、木头……），调色板是我们自己定的，不用游戏贴图。
- 队友跑动距离用同一个 VPK 里的导航网格 `maps/<map>.nav`，同样运行时只读读取、只在内存中使用，不随应用分发。
- 雷达图与地图坐标变换（`resource/overviews/*.txt`、`panorama/images/overheadmaps/*_radar_psd.vtex_c`）在**运行时从用户本机的 CS2 安装目录只读读取**，不随应用分发。
- 比赛列表里的地图图片是游戏自己的地图预览图（`panorama/images/map_icons/screenshots/360p/<map>_png.vtex_c`，内嵌 PNG），同样运行时只读读取、只在内存中使用，不随应用分发。
- `src/core/maps.ts` 中的 Mirage 备用坐标（`pos_x -3230 / pos_y 1713 / scale 5`）是数值事实，仅在找不到 CS2 安装时使用。
- 道具学院（`src/core/lineups.ts`）的起点/角度/落点来自一场完美平台 Demo 中玩家的真实投掷记录（数值），文字说明为自行撰写。
- csgove 的发布包里还有 Valve 的 `tier0.dll`、`vaudio_celt.dll`（CS:GO 旧语音格式用的），我们**不复制、不分发**：CS2 的 Opus 语音用不到它们，csgove 只检查文件存在，运行时放两个空文件代替（ADR-0025）。
- 上线/商业化前需要单独做 IP / 商标审查（roadmap §11.3）。

## 职业比赛范例数据（data/pro）

从公开的比赛 Demo 提取的位置和事件数据（不含 Demo 文件和任何游戏资源），用于战术学院的范例（ADR-0039）：

- BLAST.tv Austin Major 2025 半决赛 MOUZ vs Vitality，Train 的若干回合。来源：https://www.hltv.org/matches/2382618/mouz-vs-vitality-blasttv-austin-major-2025
- StarLadder Budapest Major 2025 第三阶段 Passion UA vs Liquid，Train 的若干回合。来源：https://www.hltv.org/matches/2388112/passion-ua-vs-liquid-starladder-budapest-major-2025
- StarLadder Budapest Major 2025 半决赛 Spirit vs Vitality，Dust2 与 Mirage 的若干回合。来源：https://www.hltv.org/matches/2388128/spirit-vs-vitality-starladder-budapest-major-2025
- IEM Cologne Major 2026 第三阶段 Spirit vs 9z，Overpass 的若干回合。来源：https://www.hltv.org/matches/2394986/spirit-vs-9z-iem-cologne-major-2026
- IEM Cologne Major 2026 半决赛 Spirit vs Falcons，Anubis 的若干回合。来源：https://www.hltv.org/matches/2395001/iem-cologne-major-2026-semi-final-2-iem-cologne-major-2026
- PGL CS2 Major Copenhagen 2024 四分之一决赛 Spirit vs FaZe，Vertigo 的若干回合。来源：https://www.hltv.org/matches/2370722/spirit-vs-faze-pgl-cs2-major-copenhagen-2024
- IEM Cologne Major 2026 决赛 Falcons vs FURIA，Anubis 的若干回合。来源：https://www.hltv.org/matches/2395002/iem-cologne-major-2026-grand-final-iem-cologne-major-2026
- StarLadder Budapest Major 2025 半决赛 FaZe vs NAVI，Ancient 与 Nuke 的若干回合。来源：https://www.hltv.org/matches/2388129/starladder-budapest-major-2025-semi-final-2-starladder-budapest-major-2025
- StarLadder Budapest Major 2025 四分之一决赛 NAVI vs FURIA，Train 的若干回合。来源：https://www.hltv.org/matches/2388127/furia-vs-natus-vincere-starladder-budapest-major-2025
- IEM Cologne Major 2026 四分之一决赛 G2 vs Spirit，Overpass 的若干回合。来源：https://www.hltv.org/matches/2394998/match
- StarLadder Budapest Major 2025 决赛 Vitality vs FaZe，Inferno 的若干回合。来源：https://www.hltv.org/matches/2388130/vitality-vs-faze-starladder-budapest-major-2025
