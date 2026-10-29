# Source verification

- The official GoldHEN repository release page is available at https://github.com/GoldHEN/GoldHEN/releases and lists GoldHEN v2.4b18 as a pre-release.
- The attachment cites https://github.com/sleirsgoevy/ps4-jb-900, but that URL currently returns GitHub 404 / Page not found.
- The ConsoleMods PS4 Exploit Chart was reviewed at https://consolemods.org/wiki/PS4:Exploit_Chart. It documents public support by firmware range and does not list a public exploit entry for firmware 13.00; it also distinguishes theoretical Poopsploit support from released, recommended paths.
- Therefore, the missing webkit/*.js, kexploit/*.js, common/*.js, and payload .bin files cannot be safely populated from the attachment alone. No exploit source or binary was downloaded or executed.

## Upstream sources (inspected, not shipped)

The local `vendor/` verification archives were removed from the repository to keep the deployment clean — nothing at runtime referenced them. Sources were inspected from upstream before the payloads were localized:

- https://github.com/Al-Azif/psfree-lapse (v1.5.1) — PSFree + Lapse, functional support tested for PS4 7.00 – 9.60.
- https://github.com/sleirsgoevy/ps4jb — PS4 6.72/7.02 jailbreak reference.
- https://github.com/owendswang/vue-after-free-lite — Vue After Free reference.

The archives were downloaded for source inspection only. They were never executed as shipped, and the payloads in the host directories are the localized, path-corrected versions built from them.
