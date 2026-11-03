# Morphe Quarantine — Broken Patch Sets

Patch sets quarantined from the main bundle ([mwbra130/Retro-Bowl-College](https://github.com/mwbra130/Retro-Bowl-College)) on 2026-11-03.

**These patch sets are known NOT working on device.** They are kept here for reference and possible revival only. Do **not** add this repo as a patch source — the patches below do not work, which is exactly why they were moved out of the main bundle so they no longer show in its patch list.

| App | Package | Why it's here |
|---|---|---|
| DiskWala | `com.diskwalaapp` | PairIP native wall: the patched build is blocked by PairIP's native license layer ("Get this app from Play"); no dex patch surface remains. Closed. |
| Yin Yang Launcher | `com.yinyang.launcher` | Premium does not unlock on device despite two Desktop-verified pin strategies; parked unresolved. |
| X-plore | `com.lonelycatgames.Xplore` | PairIP native wall: the patched build hits the "Get this app from Play" block at startup. Closed. |
| Vehico | `com.optimageeks.vehico_app` | The "Remove ads" patch failed on device; parked. (Premium is server-gated and was never shipped.) |
| RainViewer | `com.lucky_apps.RainViewer` | Premium unlocks locally, but the server withholds all weather data from re-signed builds (error code 81), so the patched app is unusable. |
| Web Video Caster | `com.instantbits.cast.webvideo` | The Play wall fires even with every dex PairIP chokepoint stubbed; no in-app patch surface remains. |
| BusinessX | `com.shrey_businessx.android` | Moved to quarantine at Matsen's instruction 2026-11-03; on-device result was not reported in the chat that shipped it. (Shipped in main bundle v1.59.0, Desktop-verified; its BusinessX Cloud backup/multi-device sync was server-claim-limited by design — premium there is authorized by a server-set Firebase claim no local patch can mint. Local features — export, full history, trends, no ads, Google Drive backup — were fully granted by the pin.) |
| Strava | `com.strava` | Isolated at owner's request (2026-11-03). Premium features are server-gated (a local patch cannot unlock them), so this custom set is not part of the working bundle. |

## Layout

This repo mirrors the main bundle's build scaffolding (Gradle wrapper, settings, patches module) with only the quarantined patch sets under `patches/src/main/kotlin/app/zdrgon/patches/`, copied exactly as they were in the main bundle — including their experimental flags and defaults — at the time of the move (main bundle v1.59.0, 2026-11-03). BusinessX was added later the same day, copied from main bundle v1.60.0. The Strava set (patch package, `extensions/strava` module and design docs) was added later the same day, copied from main bundle v1.60.0.

Release workflows are intentionally not committed here; this repo is storage/quarantine, not a distribution source.
