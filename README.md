# alnafar | PS4 Exploit Host

<div align="center">

![alnafar](background.jpg)

**PS4 Jailbreak Host — FW 5.05 / 6.72 – 13.52**

[![GitHub Pages](https://img.shields.io/badge/GitHub-Pages-blue)](https://code-name-in-b.github.io/ps4jb/)
[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)

</div>

---

## About

**alnafar** is a PS4 exploit host that supports firmware **5.05, 6.72, and 7.00 through 13.52**. The root page is a firmware menu (like a TV launcher); every firmware range lives in its own **self-contained host directory** that installs and serves its own offline cache, modeled on the battle-tested [PSPulse](https://github.com/psx8/psx8.github.io) architecture. Ships **GoldHEN v2.4b18.12**.

### Layout — psx8-style split hosts

| Path | Role |
|------|------|
| `/index.html` + `navigation.manifest` | Menu only — plain links, no auto-forwarding |
| `/505/`, `/672/` | Single-page hosts (manifest on `index.html`, cache + run from one page) |
| `/700/`, `/900/`, `/css/`, `/slopkit/` | Two-page hosts: cache-less `index.html` + `cache.html` installer with its own `cache.manifest` |
| `/tools/gen_manifests.py` | Regenerates every `cache.manifest` from the files that actually exist (forward slashes only — a backslash entry 404s and kills the whole install on the PS4) |

Cache rules baked into the design:

- Every cache manifest lists **only files that exist**, with **forward slashes**, and ends with `NETWORK: *`.
- `cache.html` runs `history.replaceState('index.html')` and **always continues on its own** (`openHost`) once the cache is ready — nobody gets parked on the installer.
- The host index never bounces back: a failed first install escapes with `?skipcache=1` and runs from the network instead of ping-ponging.
- GoldHEN lives inside each host directory, so every `fetch()` in the chains is directory-local.

### Supported Firmwares

| FW | Exploit | Host |
|----|---------|-------|
| 5.05 – 5.07 | WebKit + BPF | `505/` |
| 6.72 | WebKit + jb | `672/` |
| 7.00 – 8.52 | PSFree + Lapse | `700/` |
| 9.00 – 9.60 | PSFree + Lapse | `900/` |
| 10.00 – 11.02 | CSSFontFace | `css/` |
| 11.50 – 12.02 | SLOP + Lapse | `slopkit/` |
| 12.50 – 13.00 | SLOP + Poops | `slopkit/` |
| 13.02 – 13.52 | SLOP + jb | `slopkit/` |

### Unsupported

- FW 5.00 - 5.04
- FW 6.00 - 6.71
- FW 8.53 - 8.99 / 9.61 - 9.99
- FW 11.03 - 11.49
- FW 12.03 - 12.49

---

## Credits

This project would not exist without the incredible work of these developers and researchers:

### Exploit Developers

| Contributor | Contribution |
|-------------|-------------|
| **anonymous** | PSFree WebKit exploit (CVE-2022-22620), Lapse kernel exploit, PS4 kernel dumps |
| **Al-Azif** | PSFree-Lapse repository maintainer |
| **ChendoChap** | pOOBs4 helper functions, vtable offset technique, kernel exploit research |
| **CelesteBlue** | SerializedScriptValue offsets, vulnerable firmware range identification |
| **janisslsm (John)** | ArrayBufferContents offsets, ROP chains for FW 9.00/9.50 (based on Chain803) |
| **Kameleonre** | PSFree tester, exploit research |
| **SlidyBat** | ArrayBufferContents offsets (PS5) |
| **SiSTR0** | Exploit research and development |
| **Abc** | Exploit research |

### Host & Tools

| Contributor | Contribution |
|-------------|-------------|
| **GamerHack** | Exploit host framework, firmware detection, AppCache routing, FW 5.05/6.72/13.02-13.52 chains |
| **psx8 / BlackArch (PSPulse)** | The stable split-host AppCache architecture this rebuild follows |
| **GoldHEN Team** | GoldHEN homebrew enabler payload (v2.4b18.12) |
| **sleirsgoevy** | PS4 jailbreak reference project (ps4jb) |
| **owendswang** | Vue After Free Lite reference project |

### Special Thanks

- **Al-Sharada Electronics** — Partnership and support
- **ps4-dev** and **PS5 R&D** Discord communities

---

## Sources

- [PSFree-Lapse](https://github.com/Al-Azif/psfree-lapse) — AGPL-3.0-or-later
- [GamerHack](https://github.com/GamerHack/GamerHack.github.io)
- [psx8/psx8.github.io](https://github.com/psx8/psx8.github.io) — the stable host architecture
- [GoldHEN](https://github.com/GoldHEN/GoldHEN/releases)
- [sleirsgoevy/ps4jb](https://github.com/sleirsgoevy/ps4jb)
- [owendswang/vue-after-free-lite](https://github.com/owendswang/vue-after-free-lite)

---

## Disclaimer

This project is for **educational purposes only**. The authors are not responsible for any damage caused by misuse of this software. Use at your own risk.

---

<div align="center">

**Developed by [CODE-NAME-IN-B](https://github.com/CODE-NAME-IN-B)**

</div>
