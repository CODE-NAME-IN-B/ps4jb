# Source verification

- The official GoldHEN repository release page is available at https://github.com/GoldHEN/GoldHEN/releases and lists GoldHEN v2.4b18 as a pre-release.
- The attachment cites https://github.com/sleirsgoevy/ps4-jb-900, but that URL currently returns GitHub 404 / Page not found.
- The ConsoleMods PS4 Exploit Chart was reviewed at https://consolemods.org/wiki/PS4:Exploit_Chart. It documents public support by firmware range and does not list a public exploit entry for firmware 13.00; it also distinguishes theoretical Poopsploit support from released, recommended paths.
- Therefore, the missing webkit/*.js, kexploit/*.js, common/*.js, and payload .bin files cannot be safely populated from the attachment alone. No exploit source or binary was downloaded or executed.

## Downloaded source archives

- `vendor/psfree-lapse-v1.5.1.zip` from https://github.com/Al-Azif/psfree-lapse, verified as a readable ZIP archive.
- `vendor/ps4jb.zip` from https://github.com/sleirsgoevy/ps4jb, verified as a readable ZIP archive.
- `vendor/vue-after-free-lite.zip` from https://github.com/owendswang/vue-after-free-lite, verified as a readable ZIP archive.

The archives were downloaded for source inspection only. They were not executed and were not renamed into the numbered exploit slots because their entrypoints, firmware assumptions, and loading contracts do not directly match the custom `index.html` loader.
