# PS4 Exploit Host

## Product Description

A self-hosted web application that delivers PS4 jailbreak exploit chains to PlayStation 4 browsers. The host detects the PS4's firmware version via User-Agent, selects the appropriate exploit chain, and executes it to install GoldHEN (homebrew enabler).

## Target Users

- PS4 owners running firmware 7.00 through 13.00
- Users who want to jailbreak their PS4 for homebrew, custom firmware, or game backups
- Typically accessed via the PS4's built-in web browser after setting DNS to point to the host

## Core Functionality

1. **Auto-detection**: Reads PS4 User-Agent to determine firmware version
2. **Firmware routing**: Selects the correct exploit chain based on firmware range
3. **AppCache**: Caches exploit files for offline/repeated use
4. **Exploit execution**: Loads WebKit exploit -> Kernel exploit -> GoldHEN payload
5. **Manual fallback**: Grid of firmware buttons for manual selection

## Supported Firmware Ranges

| Range | Exploit Chain | Method |
|-------|--------------|--------|
| 7.00 – 8.52 | PSFree + Lapse | WebKit UAF + aio_multi_delete race |
| 9.00 – 9.60 | PSFree + Lapse | WebKit UAF + aio_multi_delete race |
| 10.00 – 11.02 | CSSFontFace | CSS font loading exploit |
| 11.50 – 12.02 | SLOP + Lapse | Double-free + Lapse kernel |
| 12.50 – 13.00 | SLOP + Poopsploit | Double-free + Poopsploit kernel |

## Technical Stack

- Pure HTML/CSS/JS (no frameworks)
- HTML5 Application Cache (AppCache) for offline support
- ES modules for modern exploit chains
- Vanilla JS for firmware detection and routing

## Design Principles

- Dark theme (PS4 browser optimized)
- Touch-friendly (PS4 browser has no cursor)
- Minimal file size (PS4 browser has limited resources)
- Clear status feedback (loading, success, error states)
- Works on PS4 WebKit browser and modern desktop browsers

## Source

Based on GamerHack (gamerhack.github.io) exploit host structure.
