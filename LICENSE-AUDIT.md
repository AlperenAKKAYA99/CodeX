# CodeX — Comprehensive License & Compliance Audit Report

**Product:** CodeX (`v1.148.0`)  
**Developer & Copyright Holder:** Alperen AKKAYA (`https://github.com/AlperenAKKAYA99/CodeX`)  
**Audit Date:** 2026-11-25  
**Target Business Model:** Closed-source proprietary commercial distribution (Individual Subscription, Enterprise License, Lifetime License)

> **Important Legal Disclaimer:** This audit is a technical and compliance engineering assessment based on direct inspection of repository manifests, `pnpm-lock.yaml`, built `node_modules.asar`, `cli/Cargo.lock`, binary artifacts, and license files. **It does not constitute certified legal advice or formal legal clearance.** Flagged items require review by qualified IP and commercial software licensing counsel before public commercial distribution.

---

## 1. Audit Methodology & Empirical Scope

| Inspection Target | Observed Count / Facts |
|---|---|
| Workspace `package.json` Manifests | **77** manifests audited (root, `remote/`, `remote/web/`, `build/*`, `extensions/*`, internal mocks) |
| Installed `pnpm` Dependency Store + Scopes | **1960** unique `package@version` installations across root, `build/`, `remote/`, `.pnpm`, and `extensions/*/node_modules` |
| Shipped App Runtime Modules (`node_modules.asar` + `app/node_modules`) | **195** packaged runtime modules (`191` inside ASAR + `4` unpacked in `resources/app/node_modules`) |
| Direct Runtime Dependencies (`package.json` + `remote/package.json`) | **91** direct runtime `name@version` entries |
| Root `ThirdPartyNotices.txt` | **82** upstream component notice blocks preserved |
| Rust CLI (`cli/Cargo.toml`, `cli/Cargo.lock`, `cli/ThirdPartyNotices.txt`) | **419** Cargo lockfile packages / **382** entries in `cli/ThirdPartyNotices.txt` *(not bundled in current Windows staging `bin/`)* |
| Native Desktop Runtime (`CodeX.exe` `process.versions`) | Electron `43.8.9` (`MIT`), Chromium `150.0.7871.250` (`BSD-3-Clause`), Node.js `24.22.1` (`MIT`), V8 `15.0.245.31-electron.0`, `ffmpeg.dll` (`LGPL-2.1+`) |
| Bundled Tools (`resources/tools/`) | `xtool` CLI & bridge, `darwin.xtoolsdk` (`691 MB`), `xtool/linux/xtool` AppImage (`54 MB`) + `squashfs-root` (23 Debian/Ubuntu lib docs) |

---

## 2. Installed Package License Distribution (`1,960` Installed `pkg@ver`)

| Declared / Verified SPDX / License String | Installed `pkg@ver` Count |
|---|---:|
| `MIT` | 1599 |
| `ISC` | 124 |
| `Apache-2.0` | 97 |
| `BSD-3-Clause` | 55 |
| `BSD-2-Clause` | 31 |
| `BlueOak-1.0.0` | 16 |
| `MPL-2.0` | 4 |
| `CC-BY-4.0` | 3 |
| `MISSING` | 3 |
| `SEE LICENSE IN LICENSE.md` | 3 |
| `INFERRED:MIT (from file)` | 3 |
| `0BSD` | 2 |
| `SEE LICENSE IN README.md` | 1 |
| `SEE LICENSE` | 1 |
| `Open Source` | 1 |
| `LGPL-2.1+` | 1 |
| `(Unlicense OR Apache-2.0)` | 1 |
| `BSD` | 1 |
| `(MIT OR GPL-3.0-or-later)` | 1 |
| `Python-2.0` | 1 |
| `(MIT OR Apache-2.0)` | 1 |
| `Unlicense` | 1 |
| `(MPL-2.0 OR Apache-2.0)` | 1 |
| `["MIT","Apache2"]` | 1 |
| `(MIT OR WTFPL)` | 1 |
| `(MIT OR CC0-1.0)` | 1 |
| `WTFPL` | 1 |
| `(MIT AND Zlib)` | 1 |
| `(BSD-3-Clause OR GPL-2.0)` | 1 |
| `(BSD-2-Clause OR MIT OR Apache-2.0)` | 1 |
| `CC0-1.0` | 1 |
| `CC-BY-3.0` | 1 |

> **Resolution of Prior `UNKNOWN` (`MISSING`) `package.json` License Fields:** All 3 packages flagged without a `license` field in `package.json` were manually inspected on disk: `gulp-buffer@0.0.2` declares `# Licence MIT` in `Readme.md` (dev/build-only); `map-stream@0.1.0` ships an MIT `LICENCE` file (`Copyright (c) 2011 Dominic Tarr`, dev/build-only); `keytar@7.9.0` at `extensions/microsoft-authentication/packageMocks/keytar` is an empty internal mock stub (`OVERRIDE Keytar since we don't need the feature`). **Remaining truly unknown npm licenses: 0.**

---

## 3. Classification Summary Matrix

### 3.1 `PERMITTED` (Compatible with Commercial Distribution Subject to Notice Preservation)
- **Core Base & Platform:** Microsoft Visual Studio Code `1.148.0` (`MIT`), Electron `43.8.9` (`MIT`), Chromium `150.0.7871.250` (`BSD-3-Clause`), Node.js `24.22.1` (`MIT`), xTool core Swift source (`xtool/LICENSE.md`, `MIT`, `Copyright (c) 2024 Kabir Oberai`), and CodeX-authored extensions (`extensions/arm64`, `extensions/codex-language-pack-*`, original CodeX modules).
- **Shipped Runtime Modules (`193` of `195`):** `MIT` (`159`), `ISC` (`15`), `Apache-2.0` (`7`), `BSD-3-Clause` (`3`), `BlueOak-1.0.0` (`3`), `CC-BY-4.0` (`1`, `@vscode/codicons`), `BSD` (`1`), `(MIT OR WTFPL)` (`1`), `(BSD-2-Clause OR MIT OR Apache-2.0)` (`1`), `0BSD` (`1`), `Unlicense` (`1`).
- **Workspace Development & Build Dependencies (`1,939` + `2` MIT-resolved = `1,941` of `1,960`):** Permissive `MIT`, `ISC`, `Apache-2.0`, `BSD-2/3-Clause`, `BlueOak-1.0.0`, `0BSD`, `Unlicense`, `CC0-1.0`, `CC-BY-4.0`, `Python-2.0`.

### 3.2 `RESTRICTED` (Must NOT Be Distributed Commercially Without Removal or Written Third-Party License)

| Component / Artifact | Location / Version | Governing Terms Observed | Why Restricted | Required Action |
|---|---|---|---|---|
| **`darwin.xtoolsdk`** (`691 MB` tar.gz) | `resources/tools/darwin.xtoolsdk` (`iPhoneOS.sdk`, `MacOSX27.2.sdk`, `iPhoneSimulator27.2.sdk`, `StoreKitTest.framework`, `XCTest.framework`, LLVM `ld64.lld`) | Proprietary Apple Xcode / Apple SDK Agreement (+ LLVM `Apache-2.0 WITH LLVM-exception` for toolset binaries) | Apple proprietary SDK frameworks and headers extracted from Xcode generally prohibit commercial third-party redistribution inside another vendor's product installer. | **CRITICAL:** Remove pre-bundled Apple SDK payloads from public commercial releases; prompt end users to obtain `Xcode.xip` directly from Apple (`developer.apple.com`) or obtain written authorization from Apple Inc. |
| **`@vscode/copilot-api`** | `0.5.2` (direct dep in `package.json`, `remote/package.json`, `extensions/copilot`, `extensions/copilot/chat-lib`; bundled in `node_modules.asar`) | Proprietary GitHub, Inc. / Microsoft NPM Module Terms | Clause 1 allows use **only** with Microsoft VS Code or Code-OSS (dev-only) and Clause 3(f) **prohibits** combining into your application for third parties without permission. | **CRITICAL:** Remove dependency / refactor Copilot integration out of commercial builds unless written licensing permission is obtained from GitHub / Microsoft. |
| **`@anthropic-ai/claude-agent-sdk`** (`& -win32-x64`) | `0.3.304` (`devDependencies`, `build/agent-sdk/agents/claude`) | `© Anthropic PBC. All rights reserved.` (`https://code.claude.com/docs/en/legal-and-compliance`) | Proprietary Anthropic commercial software; currently `devDependencies` / agent SDK tooling, not in `node_modules.asar`. | Keep excluded from shipped product packages or obtain written Anthropic redistribution consent. |

### 3.3 `REVIEW REQUIRED` (Copyleft, File-Level Copyleft, Non-Modifiable Binaries, & Attribution Checks)

| Component / Artifact | Location / Version | License Observed | Obligation / Risk | Recommended Mitigation |
|---|---|---|---|---|
| **`jschardet`** | `3.1.4` (`package.json`, `remote/package.json`, `remote/web/package.json`; bundled in `node_modules.asar` & JS bundle) | `LGPL-2.1+` | Bundled via esbuild into minified JS rather than cleanly dynamically replaced; triggers LGPL Section 6 obligations (user modification, relinking/object access, & debugging reverse-engineering exception). | Preserve LGPL carve-out in EULA Section 6 **and** strongly consider replacing `jschardet` with a permissive `MIT` / `Apache-2.0` encoding detector. |
| **`FFmpeg` (`ffmpeg.dll`)** | Dynamically linked in Electron `43.8.9` | `LGPL-2.1+` | Dynamically linked shared library; requires preserving notices, source URL, user replacement capability, and LGPL reverse-engineering-for-debugging carve-out. | Satisfied via dynamic linking + `EULA.md` Section 6 + `THIRD-PARTY-NOTICES.md`, subject to counsel check. |
| **Linux `xtool` AppImage & `squashfs-root`** | `resources/tools/xtool/linux/xtool` (`54 MB`) & `squashfs-root/usr/share/doc/*/copyright` (`23` packages) | Mixed: `LGPL-2.1+` (`libgnutls30`, `librtmp1`, `libssh-4`, `libtasn1-6`, `libp11-kit0`), `LGPL-3.0+ OR GPL-2.0+` (`libhogweed6`, `libnettle8`, `libidn2-0`, `libunistring2`), `BSD-3-Clause OR GPL-2` (`libzstd1`), `Apache-2.0`/`Artistic`/`GPL` (`libssl3`), `ICU`/`GPL-3` (`libicu70`) | Redistributing compiled GNU LGPL/GPL binary `.so` shared libraries inside Windows installers triggers written source-offer / corresponding-source duties even if unused directly as Windows binaries. | For Windows builds, avoid shipping `resources/tools/xtool/linux/` inside Windows installers if WSL/Ubuntu installs or fetches `xtool` inside WSL directly; otherwise comply with GPL/LGPL corresponding source offers. |
| **`@github/copilot` (`& -win32-x64`)** | `1.0.73` (`extensions/copilot`, shipped with native binary shim) | GitHub Copilot CLI License | Permits unmodified redistribution within an application providing material functionality beyond it, requires retaining `LICENSE.md`, prohibits standalone distribution or GitHub trademark misuse. | Retain verbatim notice (done in `THIRD-PARTY-NOTICES.md` & `extensions/copilot`); ensure end users connect only via authorized GitHub Copilot subscriptions/terms. |
| **`extensions/copilot` (`copilot-chat`)** | `0.76.0` (`extensions/copilot/package.json`) | `SEE LICENSE IN LICENSE.txt` (`MIT` Microsoft Corp.), depends on `@vscode/copilot-api` & `@github/copilot` | Contains Microsoft/GitHub Copilot marketplace references (`pricing: Trial`, GitHub repo links) and `@vscode/copilot-api`. | Review whether commercial CodeX should disable/unbundle built-in Copilot Chat extension prior to commercial sale. |
| **`dompurify`** | `3.4.16` (`extensions/markdown-language-features`) | `(MPL-2.0 OR Apache-2.0)` | Dual-licensed; file-level copyleft avoided cleanly by selecting `Apache-2.0`. | Document `Apache-2.0` election (done in `THIRD-PARTY-NOTICES.md`). |
| **`axe-core` (`4.10.3`, `4.11.1`) & `lightningcss` (`1.32.0`)** | Dev/test (`axe-html-reporter`, `test/automation`, tooling) | `MPL-2.0` | Weak file-level copyleft (`MPL-2.0`). Confirmed **not** shipped inside `node_modules.asar`. | Keep excluded from shipped runtime bundles. |
| **`jszip` (`3.10.1`) & `node-forge` (`1.4.0`)** | Dev/test (`extensions/vscode-api-tests` / tooling) | `(MIT OR GPL-3.0-or-later)` & `(BSD-3-Clause OR GPL-2.0)` | Dual-licensed; confirmed **not** shipped inside `node_modules.asar`. | Elect `MIT` / `BSD-3-Clause` if ever used. |
| **`innosetup` (`6.4.1`)** | `devDependencies` (Windows installer build tool) | Inno Setup License (`Open Source` — Jordan Russell / Martijn Laan) | Free commercial packaging permitted; setup stub notices apply cleanly when unmodified. | Retain attribution cleanly. |
| **Upstream Source Headers (`src/`, `extensions/swift*`)** | Throughout forked VS Code files | `MIT License (Copyright Microsoft Corporation)` | Must remain preserved verbatim in all copied/forked VS Code source files and extension templates. Note `extensions/swift-language-features/src/swiftMain.ts` previously carried an outdated `MIT` header (`Copyright (c) CodeX`). | Preserve all Microsoft MIT headers untouched; align CodeX-authored file headers carefully with copyright counsel guidance. |

### 3.4 `UNKNOWN`
- **`0` unresolved npm packages** remaining after disk verification (`gulp-buffer` MIT, `map-stream` MIT, `keytar` empty mock).
- **Note on `extensions/swift-language-features` Build Health:** During initial `core-ci` testing, `tsgo` (`@typescript/native`) flagged 3 missing Node built-in imports (`fs`, `cp`) in `extensions/swift-language-features/src/swiftMain.ts` lines 226/229/237; the missing `import * as fs` and `import * as cp` statements were added and verified (`TS7 exit code: 0`, `compile-extension:swift-language-features` 0 errors).

---

## 4. Phase 5 Legal & Turkish Compliance Safeguards Verified

1. **Governing Law & Mandatory Consumer Protection (`Republic of Türkiye`):** `EULA.md` (Section 11), `LICENSE`, `LICENSING.md`, and `DISCLAIMER.md` specify governing law of the **Republic of Türkiye** while explicitly preserving mandatory consumer rules (*Tüketicinin Korunması Hakkında Kanun* No. 6502) and non-waivable statutory liability under Turkish law (avoiding invalid blanket warranty/liability waivers).
2. **LGPL Compatibility:** Added explicit Section 6 carve-out in `LICENSE` and `EULA.md` preserving user modification, shared library replacement (`ffmpeg.dll`), and reverse engineering strictly to debug modifications to LGPL libraries (`jschardet`, `FFmpeg`).
3. **No False Proprietary Relicensing:** Explicitly separated `Alperen AKKAYA` original IP (`COPYRIGHT.md` Section 2) from Microsoft VS Code `Code - OSS` MIT code (`COPYRIGHT.md` Section 3) and third-party notices (`THIRD-PARTY-NOTICES.md`).
4. **Commercial Model Consistency Without Unverified Claims:** Individual Subscription, Enterprise License, and Lifetime License match verbatim terms across `LICENSE`, `EULA.md`, `LICENSING.md`, `README.md`, and in-app UI without inventing pricing, user limits, or fake DRM mechanisms.

---

## 5. Commercial Distribution Readiness & Recommended Next Steps

**Current Readiness Status:** **CONDITIONAL / NOT YET CLEARED FOR UNRESTRICTED COMMERCIAL SALE** until the 3 `RESTRICTED` third-party redistribution blockers above are resolved.

**Recommended Prioritized Action Plan:**
1. **[P0 — Blocker]** Remove `resources/tools/darwin.xtoolsdk` from commercial installers/zips and rely on user-downloaded `Xcode.xip` (or secure written permission from Apple Inc.).
2. **[P0 — Blocker]** Remove or replace `@vscode/copilot-api` (`package.json`, `remote/package.json`, `extensions/copilot`) unless written permission is obtained from GitHub/Microsoft.
3. **[P1 — High]** Exclude Linux shared libraries (`resources/tools/xtool/linux/squashfs-root` / AppImage) from Windows PE installers or attach full GPL/LGPL corresponding source offers.
4. **[P1 — High]** Replace runtime dependency `jschardet@3.1.4` (`LGPL-2.1+`) with a permissive MIT/Apache-2.0 alternative so minified proprietary JS bundles contain zero LGPL code.
5. **[P2 — Legal Counsel Review]** Have Turkish technology/IP counsel review final commercial pricing contracts, KVKK/privacy notices (when paid accounts, telemetry, or online license activation are later introduced), consumer withdrawal notices (*mesafeli satış* / *cayma hakkı* if selling online to Turkish consumers), and trademark registration (`CodeX`).
