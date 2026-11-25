# CodeX — Copyright & Intellectual Property Declaration

**Product:** CodeX (v1.148.0)  
**Copyright Holder:** Alperen AKKAYA  
**Repository:** <https://github.com/AlperenAKKAYA99/CodeX>  
**Effective Date:** 2026

---

## 1. Copyright Ownership Statement

**Copyright © 2026 Alperen AKKAYA. All Rights Reserved.**

CodeX is a proprietary, closed-source commercial software product developed and maintained by **Alperen AKKAYA**. All original proprietary CodeX source code, original extensions and modules, visual designs, icons, branding, installer integrations, and original documentation are protected under copyright law, trademark/trade-dress law, and international treaties.

This declaration establishes clear boundaries between:
1. Original proprietary CodeX intellectual property owned by **Alperen AKKAYA**,
2. Derivative adaptations built atop upstream open-source projects, and
3. Unmodified third-party open-source and proprietary components owned by their respective rights holders.

---

## 2. Original Proprietary CodeX Components

The following original creations, modifications, and integrations are claimed as original proprietary works of **Alperen AKKAYA**:

| Component | Description & Scope |
|---|---|
| **CodeX Brand Identity & Trade Dress** | Product name (`CodeX`), application identifiers (`codex-ide`, `com.codex.editor`), logos, product icons, visual assets, and UI branding customizations (`product.json`, installer graphics, documentation assets). |
| **Windows ↔ WSL xTool Bridge & Tooling** | Original bridge and provisioning scripts (`resources/tools/xtool/bin/xtool-bridge.mjs`, `extract-sdk.py`, `xtool.cmd`, `install-wsl.cmd`). |
| **CodeX iOS Simulator & Apple Tooling Additions** | Original `CodeX iOS Simulator` parser/renderer/state engine (`extensions/swift-language-features/src/simulator/*`), xTool project wizard, quick actions, syslog integration, and CodeX-authored Swift workflow modules (`extensions/swift-language-features/src/{ui,runner,device,bsp,apple,debug}/*` where authored for CodeX). |
| **CodeX Language Packs** | `codex-language-pack-de`, `codex-language-pack-es`, `codex-language-pack-fr`, `codex-language-pack-ja`, `codex-language-pack-tr`, `codex-language-pack-zh-cn` translation packages authored for CodeX UI strings. |
| **Build, Packaging & Installer Customizations** | Automated multi-platform packaging scripts (`build/scripts/build.ps1`, `build/scripts/build.sh`), CodeX Inno Setup branding/WSL task extensions (`build/win32/code.iss`), and original legal/user documentation (`README.md`, `docs/*`, `LICENSE`, `EULA.md`, `LICENSING.md`, `DISCLAIMER.md`). |
| **Compiled Commercial Distribution** | The compiled, integrated CodeX distribution and installer packages licensed under [EULA.md](EULA.md). |

---

## 3. Upstream Derivative Base (Microsoft Visual Studio Code / Code - OSS)

CodeX incorporates and is built upon **Microsoft Visual Studio Code (`Code - OSS`) v1.148.0**, developed by **Microsoft Corporation** and licensed under the **MIT License**.

- **Upstream Repository:** <https://github.com/microsoft/vscode>
- **Upstream Copyright:** `Copyright (c) 2015 - present Microsoft Corporation`
- **License Preservation:** All original Microsoft MIT copyright headers in upstream source files (`src/`, `build/`, built-in extensions, and upstream scaffolding—including extension template headers retained in files under `extensions/swift` and `extensions/swift-language-features`) remain preserved intact and continue to be governed by the MIT License.
- **Scope Distinction:** Under the MIT License, Alperen AKKAYA may commercially distribute compiled derivative builds under proprietary terms ([EULA.md](EULA.md)), provided upstream MIT notices remain intact. CodeX asserts **no** claim of original authorship or exclusive copyright over Microsoft's unmodified upstream MIT code.

---

## 4. Third-Party Components & Non-Ownership Declaration

CodeX bundles, dynamically links, or invokes third-party components whose copyrights remain exclusively with their respective authors and organizations. Alperen AKKAYA claims **no copyright or ownership** over any third-party component, including:

| Component | Version (Verified) | Copyright Holder / Project | Governing License |
|---|---|---|---|
| Visual Studio Code (`Code - OSS`) | `1.148.0` | Microsoft Corporation | MIT |
| Electron | `43.8.9` | Electron contributors & GitHub Inc. | MIT |
| Chromium | `150.0.7871.250` | The Chromium Authors | BSD-3-Clause & embedded notices (`LICENSES.chromium.html`) |
| Node.js | `24.22.1` | Node.js contributors / OpenJS Foundation | MIT |
| V8 | `15.0.245.31-electron.0` | The V8 Authors / Google LLC | BSD-3-Clause |
| FFmpeg (`ffmpeg.dll`) | Bundled via Electron `43.8.9` | FFmpeg developers | LGPL-2.1+ (dynamically linked) |
| xTool (`xtool/LICENSE.md`) | Bundled tool | Kabir Oberai (`xtool-org`) | MIT |
| Bundled Node.js Runtime Modules | 191 (`node_modules.asar`) + 4 (`app/node_modules`) | Respective npm authors | Predominantly MIT / ISC / Apache-2.0 / BSD; 1 LGPL-2.1+ (`jschardet`); 1 Restricted (`@vscode/copilot-api`) — see [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md) |
| Built-in Extensions & Grammars | 84 root notices (`ThirdPartyNotices.txt`) | Microsoft, GitHub, TextMate, atom, Unicode, etc. | MIT / Apache-2.0 / BSD / ISC / Unicode |
| Bundled GitHub Copilot CLI (`@github/copilot`) | `1.0.73` | GitHub, Inc. | GitHub Copilot CLI License |
| `darwin.xtoolsdk` Archive *(Flagged in Audit)* | `iOS 27.2 / macOS 27.2` SDK bundle | Apple Inc. & LLVM Project | Proprietary Apple SDK terms / Apache-2.0 with LLVM Exception — see [LICENSE-AUDIT.md](LICENSE-AUDIT.md) |
| Linux `xtool` AppImage Shared Libraries (`squashfs-root`) | 23 Debian/Ubuntu libs | FSF, GNU, OpenSSL, Red Hat, etc. | LGPL-2.1+ / LGPL-3.0+ / GPL-2.0+/3.0+ / BSD / Apache-2.0 — see [LICENSE-AUDIT.md](LICENSE-AUDIT.md) |

Distribution of CodeX does not alter, override, or diminish the original copyrights or licenses of any third-party component. Full attribution texts are provided in [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md), [ThirdPartyNotices.txt](ThirdPartyNotices.txt), and `LICENSES.chromium.html`.

---

## 5. Trademarks

`CodeX`, the CodeX logo, and associated product identifiers are unregistered trademarks / trade dress of **Alperen AKKAYA** (see [licenses/TRADEMARKS.md](licenses/TRADEMARKS.md)).

Third-party marks—including `Microsoft`, `Visual Studio Code`, `Windows`, `Apple`, `Xcode`, `macOS`, `iOS`, `Swift`, `GitHub`, `GitHub Copilot`, `Anthropic`, `Claude`, `Chromium`, `Electron`, and `Node.js`—are trademarks of their respective owners. Their mention in CodeX indicates technical compatibility or component attribution only and implies no endorsement or affiliation.

---

## 6. Telif Hakkı Özeti (Türkçe)

**Telif Hakkı © 2026 Alperen AKKAYA. Tüm Hakları Saklıdır.**

- CodeX markası, özgün kullanıcı arayüzü özelleştirmeleri, Windows–WSL `xtool-bridge` betikleri, CodeX iOS Simülatör motoru, dil paketleri, paketleme/kurulum betikleri ve özgün belgeler **Alperen AKKAYA**'nın münhasır mülkiyetindedir.
- Temel alınan **Microsoft Visual Studio Code (`1.148.0`)** ve **xTool** MIT Lisansı kapsamında kendi telif haklarını korur; **Electron**, **Chromium**, **Node.js**, **FFmpeg** (`LGPL-2.1+`), **npm paketleri** ve üçüncü taraf SDK/ikili bileşenler üzerindeki haklar ilgili sahiplerine aittir. Üçüncü taraf lisans bildirimleri ve uyumluluk değerlendirmesi için [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md) ve [LICENSE-AUDIT.md](LICENSE-AUDIT.md) belgelerine bakınız.

---

*Related documents: [LICENSE](LICENSE) · [EULA.md](EULA.md) · [LICENSING.md](LICENSING.md) · [DISCLAIMER.md](DISCLAIMER.md) · [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md) · [LICENSE-AUDIT.md](LICENSE-AUDIT.md)*
