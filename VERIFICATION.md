# Tap distribution verification

## Checked on 2026-10-04

The original [Molaway 2.2.5 Apple Silicon ZIP](https://github.com/boorkymoorky/molaway/releases/download/v2.2.5/Molaway-2.2.5-macOS-arm64.zip) was downloaded again. GitHub asset ID `591372855`, size 1,809,628 bytes, and SHA256 `f1430159bdc05ebf141cd6ff583412784b572a0766c90b61254cb942f8bd5882` agree with the release checksum file and GitHub asset digest. These are same-publisher integrity checks, not independent authentication or malware analysis.

The cask was published through [PR #1](https://github.com/boorkymoorky/homebrew-molaway/pull/1), with native Homebrew style and strict audit CI passing. Main is protected by PRs and a required up-to-date `verify` check, including administrators. The published cask matches Molaway PR #19’s candidate byte-for-byte.

Native Homebrew 7.0.7 style and full strict online cask audit passed locally. A fresh disposable Homebrew environment resolved the complete public cask reference, automatically tapped this repository’s main branch, downloaded the real asset, enforced SHA256 and installed the original app in a disposable destination. The environment used its own prefix/Caskroom/cache/tap and an isolated app destination; this nonstandard prefix is Homebrew Tier 3, not evidence for every standard-prefix/OS combination.

Fetch, same-version reinstallation and uninstall succeeded. Reinstallation preserved quarantine and passed original signature verification. Upgrade correctly reported that 2.2.5 is current; no cross-version upgrade is claimed because no newer app release exists. Uninstall removed the disposable app/cask metadata while synthetic settings and summary fixtures remained byte-identical. A synthetic existing-app conflict refused replacement without force/adopt and preserved the fixture. Native requirement checks accepted Apple Silicon/macOS 15 and rejected Intel/macOS 14 under simulated limits; physical older-OS/Intel coverage is unclaimed.

Gatekeeper stayed enabled. The installed original bundle retained normal Homebrew quarantine and passed `codesign --verify --deep --strict`. `gktool scan` reported the expected distributor-signing failure: the app is ad hoc signed and unnotarized. The third-party strict audit is not proof of notarization acceptance. There is no audit skiplist, quarantine removal, installer hook, privileged action, dependency or `zap` deletion. Personal Molaway app/data/login items were not test targets; the released app was never launched or re-signed.

## Remaining gate

The original app’s first launch following [Apple’s normal per-app approval flow](https://support.apple.com/en-us/102445) remains unverified and deferred at the maintainer’s request. Complete this in a separate macOS user or Mac to preserve personal data under the original bundle identity. Keep quarantine/Gatekeeper enabled; stop on malware, damaged-app or organization-policy warnings. After a successful first launch, publish the tested end-user install/update/removal instructions in this README and Molaway’s installation guide.

This tap distributes the existing 2.2.5 app. M1–M9 development changes are absent; no new app version or release, M11 or M6 physical checklist is part of this work. Molaway stays offline and manually updated; Homebrew’s GitHub downloads are external tooling. See [Molaway’s full M10 record](https://github.com/boorkymoorky/molaway/blob/main/docs/M10_DISTRIBUTION.md).
