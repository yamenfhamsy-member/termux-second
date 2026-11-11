# Termux Second (`com.yamen.termux.second`)

Standalone, independently installable Android fork of official [Termux](https://github.com/termux/termux-app) (`GPLv3`) engineered to coexist safely alongside official `com.termux` on the same Android device without UID, authority, permission, or filesystem prefix collisions.

## Key Isolation Architecture
- **Application Name:** `Termux Second`
- **Android `applicationId`:** `com.yamen.termux.second` (Java namespace `com.termux` cleanly preserved)
- **Dedicated Linux UID:** `android:sharedUserId` removed for full kernel UID sandbox isolation
- **Private Data Root:** `/data/data/com.yamen.termux.second`
- **Custom `$PREFIX`:** `/data/data/com.yamen.termux.second/files/usr` (compiled from source across all bootstrap packages, ELF `DT_RUNPATH`, shared libraries, scripts, shebangs, and `dpkg`/`apt` metadata)
- **Custom `$HOME`:** `/data/data/com.yamen.termux.second/files/home`
- **Plugin Compatibility:** Official `com.termux.*` plugins are intentionally not shared or claimed compatible.

## License
Preserves all upstream Termux (`GPL-3.0`) and package licenses (`LICENSE.md`).
