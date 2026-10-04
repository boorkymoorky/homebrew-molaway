# Molaway Homebrew tap

Maintainer-owned distribution of [Molaway](https://github.com/boorkymoorky/molaway), a personal, non-commercial, privacy-first macOS break reminder by Burak Yelkenci, derived from [Offscreen](https://github.com/dayo/Offscreen). Both copyright notices are retained under the [MIT license](LICENSE). Prepared with ChatGPT/Codex assistance and reviewed with targeted checks.

## Availability

This tap pins the existing **2.2.5** Apple Silicon download. It requires **macOS 15 or later**. M1–M9 development changes on Molaway's main branch are absent from this download. This tap is maintained by Molaway; it is not the official `homebrew/cask` repository or a Homebrew endorsement.

Public tap installation verification is in progress. Use the [verified direct download guide](https://github.com/boorkymoorky/molaway/blob/main/docs/INSTALL.md) until the complete tap command and lifecycle checks pass.

## Signing and privacy

The app is ad hoc signed and **not Developer ID signed or notarized**. Homebrew does not provide publisher authentication or Apple review. Keep Gatekeeper enabled and follow [Apple's per-app approval instructions](https://support.apple.com/en-us/102445) only if you trust the download. Do not override malware, damaged-app or organization-policy blocks.

Homebrew contacts GitHub to fetch the tap and ZIP. Molaway itself stays local, account-free and telemetry-free; it does not check for updates. Updates remain manual. This cask contains no installer hooks, privilege escalation, security overrides, dependencies or `zap` stanza. Removing the cask preserves local settings and summaries.

## Maintenance

Cask changes require a pull request and the `verify` check before merging. Pin an actually published app ZIP, download it again, and compare SHA256 with both its release checksum file and GitHub asset digest. A matching checksum is a same-publisher integrity check, not a malware guarantee. Never use an unreleased main build. The canonical candidate and verification record are maintained in [Molaway's M10 report](https://github.com/boorkymoorky/molaway/blob/main/docs/M10_DISTRIBUTION.md).
