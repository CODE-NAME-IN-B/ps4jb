# alnafar | PS4 Exploit Host

<div align="center">

![alnafar](background.png)

**PS4 Jailbreak Host — FW 7.00 - 13.00**

[![GitHub Pages](https://img.shields.io/badge/GitHub-Pages-blue)](https://code-name-in-b.github.io/ps4jb/)
[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)

</div>

---

## About

**alnafar** is a PS4 exploit host that supports firmware versions **7.00 through 13.00**. It automatically detects your PS4's firmware via User-Agent and routes to the appropriate exploit chain.

### Supported Firmwares

| FW | Exploit | Chain |
|----|---------|-------|
| 7.00 - 8.52 | PSFree + Lapse | `g2all/700/` |
| 9.00 - 9.60 | PSFree + Lapse | `g2all/900/` |
| 10.00 - 11.02 | CSSFontFace | `g2all/css/` |
| 11.50 - 12.02 | SLOP + Lapse | `g2all/slopkit/` |
| 12.50 - 13.00 | SLOP + Poopsploit | `g2all/slopkit/` |

### Unsupported

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
| **GamerHack** | Exploit host framework, firmware detection, AppCache routing |
| **GoldHEN Team** | GoldHEN homebrew enabler payload (v2.4b18.10) |
| **sleirsgoevy** | PS4 jailbreak reference project (ps4jb) |
| **owendswang** | Vue After Free Lite reference project |

### Special Thanks

- **Al-Sharada Electronics** — Partnership and support
- **ps4-dev** and **PS5 R&D** Discord communities

---

## Sources

- [PSFree-Lapse](https://github.com/Al-Azif/psfree-lapse) — AGPL-3.0-or-later
- [GamerHack](https://github.com/GamerHack/GamerHack.github.io)
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
