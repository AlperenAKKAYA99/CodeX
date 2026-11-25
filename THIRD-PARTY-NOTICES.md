# CodeX — Third-Party Software Notices and Attributions

**Product:** CodeX (`v1.148.0`)  
**Developer & Distributor:** Alperen AKKAYA (`https://github.com/AlperenAKKAYA99/CodeX`)  
**Copyright © 2026 Alperen AKKAYA (original CodeX components).**

---

## 1. Overview & Legal Scope

CodeX incorporates or depends upon third-party open-source and third-party licensed software components. Every third-party component retains its own copyright ownership and remains governed by its original license. Nothing in the CodeX Proprietary Software License or CodeX EULA v1.0 claims exclusive ownership over, or diminishes user/recipient rights granted under, third-party open-source licenses.

Machine-readable and upstream Chromium/Rust/extension attribution files distributed alongside CodeX:
- Root repository/app notices (84 grammar, syntax, UI & editor components): [`ThirdPartyNotices.txt`](ThirdPartyNotices.txt)
- Chromium & Electron bundled subcomponents: `LICENSES.chromium.html` (included in application binary root)
- Built-in extension notices: `extensions/terminal-suggest/ThirdPartyNotices.txt`, `extensions/theme-seti/ThirdPartyNotices.txt`, `extensions/copilot/LICENSE.txt`
- Rust CLI crate notices (382 entries across 419 Cargo.lock crates when building `cli/`): [`cli/ThirdPartyNotices.txt`](cli/ThirdPartyNotices.txt)

---

## 2. Core Platform & Upstream Base Components

| Component | Verified Version | Copyright Holder / Author | License | Compliance / Linking Notes |
|---|---|---|---|---|
| **Microsoft Visual Studio Code (`Code - OSS`)** | `1.148.0` | Microsoft Corporation (`2015 - present`) | `MIT` | Upstream application core; original Microsoft copyright headers preserved in source files and [`ThirdPartyNotices.txt`](ThirdPartyNotices.txt). |
| **Electron** | `43.8.9` | Electron contributors & GitHub Inc. | `MIT` | Desktop runtime shell. |
| **Chromium** | `150.0.7871.250` | The Chromium Authors | `BSD-3-Clause` + embedded notices | Complete subcomponent notices bundled in `LICENSES.chromium.html`. |
| **Node.js** | `24.22.1` | Node.js contributors / OpenJS Foundation | `MIT` | Embedded JS runtime inside Electron. |
| **V8 JavaScript Engine** | `15.0.245.31-electron.0` | The V8 Authors / Google LLC | `BSD-3-Clause` | Included via Electron / Chromium. |
| **FFmpeg (`ffmpeg.dll`)** | Bundled with Electron `43.8.9` | FFmpeg developers | `LGPL-2.1+` | **Dynamically linked shared library.** Users may replace `ffmpeg.dll` with a compatible LGPL build and debug modifications per LGPL Section 6. |
| **xTool** | Bundled binary/CLI (`xtool/LICENSE.md`) | Kabir Oberai (`xtool-org`) | `MIT` | Upstream Swift cross-compilation/iOS packaging tool. Note: bundled Linux AppImage shared libraries and `darwin.xtoolsdk` are tracked separately in Section 5 & [`LICENSE-AUDIT.md`](LICENSE-AUDIT.md). |
| **GitHub Copilot Chat Extension** | `0.76.0` | Microsoft Corporation / GitHub | `MIT` (`extensions/copilot/LICENSE.txt`) + bundled `@github/copilot` | Contains MIT chat extension plus `@github/copilot` CLI binary and `@vscode/copilot-api` (flagged Restricted in [`LICENSE-AUDIT.md`](LICENSE-AUDIT.md)). |
| **GitHub Copilot CLI (`@github/copilot` / `-win32-x64`)** | `1.0.73` | GitHub, Inc. | GitHub Copilot CLI License | Redistributed unmodified; non-standalone; full license included below. |

---

## 3. Compliance Obligations by License Family

- **MIT, ISC, BSD-2-Clause, BSD-3-Clause, 0BSD, Unlicense:** Copyright notices, permission notices, and disclaimers are preserved in source files, ASAR package metadata, [`ThirdPartyNotices.txt`](ThirdPartyNotices.txt), and this document. Endorser/contributor names may not be used for promotion without written consent (BSD 3-Clause).
- **Apache License 2.0:** Complete Apache-2.0 text provided below; NOTICE files in bundled dependencies (`@vscode/sandbox-runtime`, `detect-libc`, `kerberos`, `playwright-core`, etc.) are preserved inside `node_modules.asar` / `node_modules`.
- **GNU Lesser General Public License v2.1+ (`LGPL-2.1+`):** Applies to dynamically linked `ffmpeg.dll` (via Electron/Chromium) and bundled `jschardet@3.1.4`. CodeX EULA Section 6 expressly preserves user rights to modify LGPL libraries for personal use, replace dynamically linked LGPL libraries with interface-compatible builds, and reverse engineer solely to debug such modifications. Note: `jschardet` is bundled via esbuild/ASAR and is flagged for replacement or externalization in [`LICENSE-AUDIT.md`](LICENSE-AUDIT.md).
- **Mozilla Public License 2.0 (`MPL-2.0`):** `dompurify@3.4.16` in `markdown-language-features` is dual-licensed `(MPL-2.0 OR Apache-2.0)`; CodeX elects `Apache-2.0`. Development/build-time packages `axe-core` and `lightningcss` are under `MPL-2.0`.
- **Creative Commons Attribution 4.0 (`CC-BY-4.0`):** Applies to `@vscode/codicons` (`0.0.46-51` / `0.0.46-0`) icon assets by Microsoft Corporation.

---

## 4. Verified Shipped Node.js Runtime Inventory (191 Packages)

Extracted directly from built `resources/app/node_modules.asar` (`191` packages) and `resources/app/node_modules` (`4` packages):

### License Breakdown (Shipped Runtime Packages)

| License | Package Count |
|---|---:|
| `MIT` | 156 |
| `ISC` | 15 |
| `Apache-2.0` | 6 |
| `BSD-3-Clause` | 3 |
| `BlueOak-1.0.0` | 3 |
| `(BSD-2-Clause OR MIT OR Apache-2.0)` | 1 |
| `(MIT OR WTFPL)` | 1 |
| `0BSD` | 1 |
| `BSD` | 1 |
| `CC-BY-4.0` | 1 |
| `LGPL-2.1+` | 1 |
| `SEE LICENSE` | 1 |
| `Unlicense` | 1 |

### Complete Shipped Package List

| Package | Version | License | Declared Author / Rights Holder |
|---|---|---|---|
| `@anthropic-ai/sdk` | `0.82.0` | `MIT` | Anthropic <support@anthropic.com> |
| `@babel/runtime` | `7.29.2` | `MIT` | The Babel Team (https://babel.dev/team) |
| `@devcontainers/cli` | `0.88.0` | `MIT` | Microsoft Corporation |
| `@github/copilot-sdk` | `1.0.33-preview.0` | `MIT` | GitHub |
| `@github/copilot-sdk-win32-x64` | `1.0.33-preview.0` | `MIT` | — |
| `@hpke/common` | `1.10.1` | `MIT` | Ajitomi Daisuke |
| `@hpke/core` | `1.9.0` | `MIT` | Ajitomi Daisuke |
| `@isaacs/fs-minipass` | `4.0.1` | `ISC` | Isaac Z. Schlueter |
| `@microsoft/1ds-core-js` | `3.2.13` | `MIT` | Microsoft Application Insights Team |
| `@microsoft/1ds-post-js` | `3.2.13` | `MIT` | Microsoft Application Insights Team |
| `@microsoft/applicationinsights-core-js` | `2.8.15` | `MIT` | Microsoft Application Insights Team |
| `@microsoft/applicationinsights-shims` | `2.0.2` | `MIT` | Microsoft Application Insights Team |
| `@microsoft/dev-tunnels-connections` | `1.3.61` | `MIT` | Microsoft |
| `@microsoft/dev-tunnels-contracts` | `1.3.61` | `MIT` | Microsoft |
| `@microsoft/dev-tunnels-management` | `1.3.61` | `MIT` | Microsoft |
| `@microsoft/dev-tunnels-ssh` | `3.12.22` | `MIT` | Microsoft |
| `@microsoft/dev-tunnels-ssh-tcp` | `3.12.22` | `MIT` | Microsoft |
| `@microsoft/dynamicproto-js` | `1.1.9` | `MIT` | Microsoft Application Insights Team |
| `@parcel/watcher` | `2.5.6` | `MIT` | — |
| `@pondwader/socks5-server` | `1.0.10` | `MIT` | PondWader |
| `@tootallnate/once` | `3.0.1` | `MIT` | Nathan Rajlich <nathan@tootallnate.net> (http://n8.io/) |
| `@types/semver` | `7.5.8` | `MIT` | — |
| `@vscode/codicons` | `0.0.46-51` | `CC-BY-4.0` | Microsoft Corporation |
| `@vscode/copilot-api` | `0.5.2` | `SEE LICENSE` | Microsoft Corporation |
| `@vscode/deviceid` | `0.1.5` | `MIT` | Microsoft Corporation |
| `@vscode/diff` | `0.0.2-145` | `MIT` | Microsoft Corporation |
| `@vscode/fs-copyfile` | `2.0.0` | `MIT` | — |
| `@vscode/iconv-lite-umd` | `0.7.1` | `MIT` | Microsoft |
| `@vscode/native-watchdog` | `1.4.6` | `MIT` | Microsoft Corporation |
| `@vscode/os-proxy-resolver` | `0.4.0` | `MIT` | — |
| `@vscode/os-proxy-resolver-win32-x64-msvc` | `0.4.0` | `MIT` | — |
| `@vscode/policy-watcher` | `1.7.0` | `MIT` | João Moreno |
| `@vscode/proxy-agent` | `0.46.0` | `MIT` | — |
| `@vscode/ripgrep-universal` | `1.18.0` | `MIT` | — |
| `@vscode/sandbox-runtime` | `0.0.1` | `Apache-2.0` | Anthropic PBC |
| `@vscode/spdlog` | `0.15.8` | `MIT` | Microsoft |
| `@vscode/sqlite3` | `5.1.12-vscode` | `BSD-3-Clause` | Mapbox |
| `@vscode/sudo-prompt` | `9.3.2` | `MIT` | Joran Dirk Greef |
| `@vscode/tree-sitter-wasm` | `0.3.1` | `MIT` | Visual Studio Code Team |
| `@vscode/vscode-languagedetection` | `1.0.23` | `MIT` | Tyler Leonhardt |
| `@vscode/windows-ca-certs` | `0.3.4` | `BSD` | — |
| `@vscode/windows-mutex` | `0.5.3` | `MIT` | Microsoft |
| `@vscode/windows-process-tree` | `0.8.0` | `MIT` | Microsoft Corporation |
| `@vscode/windows-registry` | `1.3.0` | `MIT` | Microsoft Corporation |
| `@xterm/addon-clipboard` | `0.3.0-beta.335` | `MIT` | The xterm.js authors |
| `@xterm/addon-image` | `0.10.0-beta.332` | `MIT` | The xterm.js authors |
| `@xterm/addon-ligatures` | `0.11.0-beta.331` | `MIT` | The xterm.js authors |
| `@xterm/addon-progress` | `0.3.0-beta.331` | `MIT` | The xterm.js authors |
| `@xterm/addon-search` | `0.17.0-beta.331` | `MIT` | The xterm.js authors |
| `@xterm/addon-serialize` | `0.15.0-beta.331` | `MIT` | The xterm.js authors |
| `@xterm/addon-unicode11` | `0.10.0-beta.331` | `MIT` | The xterm.js authors |
| `@xterm/addon-webgl` | `0.20.0-beta.330` | `MIT` | The xterm.js authors |
| `@xterm/headless` | `6.1.0-beta.335` | `MIT` | — |
| `@xterm/xterm` | `6.1.0-beta.337` | `MIT` | — |
| `adm-zip` | `0.6.1` | `MIT` | Nasca Iacob <adm-zip@pm.me> (https://github.com/cthackers) |
| `agent-base` | `7.1.4` | `MIT` | Nathan Rajlich <nathan@tootallnate.net> (http://n8.io/) |
| `asn1` | `0.2.6` | `MIT` | Joyent (joyent.com) |
| `asynckit` | `0.4.0` | `MIT` | Alex Indigo <iam@alexindigo.com> |
| `await-semaphore` | `0.1.3` | `MIT` | Emma Kuo |
| `axios` | `1.20.0` | `MIT` | Matt Zabriskie |
| `base64-js` | `1.5.1` | `MIT` | T. Jameson Little <t.jameson.little@gmail.com> |
| `bcrypt-pbkdf` | `1.0.2` | `BSD-3-Clause` | — |
| `bindings` | `1.5.0` | `MIT` | Nathan Rajlich <nathan@tootallnate.net> (http://tootallnate.net) |
| `bn.js` | `4.12.3` | `MIT` | Fedor Indutny <fedor@indutny.com> |
| `brorand` | `1.1.0` | `MIT` | Fedor Indutny <fedor@indutny.com> |
| `buffer` | `5.7.1` | `MIT` | Feross Aboukhadijeh |
| `buffer-crc32` | `0.2.13` | `MIT` | Brian J. Brennan <brianloveswords@gmail.com> |
| `bufferutil` | `4.1.0` | `MIT` | Einar Otto Stangvik <einaros@gmail.com> (http://2x.io) |
| `buildcheck` | `0.0.7` | `MIT` | Brian White <mscdex@mscdex.net> |
| `bundle-name` | `4.1.0` | `MIT` | Sindre Sorhus |
| `call-bind-apply-helpers` | `1.0.2` | `MIT` | Jordan Harband <ljharb@gmail.com> |
| `chownr` | `3.0.0` | `BlueOak-1.0.0` | Isaac Z. Schlueter <i@izs.me> (http://blog.izs.me/) |
| `chrome-remote-interface` | `0.33.0` | `MIT` | Andrea Cardaci <cyrus.and@gmail.com> |
| `combined-stream` | `1.0.8` | `MIT` | Felix Geisendörfer <felix@debuggable.com> (http://debuggable.com/) |
| `d` | `1.0.1` | `ISC` | Mariusz Nowak <medyk@medikoo.com> (http://www.medikoo.com/) |
| `debug` | `4.4.3` | `MIT` | Josh Junon (https://github.com/qix-) |
| `deep-extend` | `0.6.0` | `MIT` | Viacheslav Lotsmanov <lotsmanov89@gmail.com> |
| `default-browser` | `5.2.1` | `MIT` | Sindre Sorhus |
| `default-browser-id` | `5.0.0` | `MIT` | Sindre Sorhus |
| `define-lazy-prop` | `3.0.0` | `MIT` | Sindre Sorhus |
| `delayed-stream` | `1.0.0` | `MIT` | Felix Geisendörfer <felix@debuggable.com> (http://debuggable.com/) |
| `detect-libc` | `2.1.2` | `Apache-2.0` | Lovell Fuller <npm@lovell.info> |
| `diffie-hellman` | `5.0.3` | `MIT` | Calvin Metcalf |
| `dunder-proto` | `1.0.1` | `MIT` | Jordan Harband <ljharb@gmail.com> |
| `end-of-stream` | `1.4.4` | `MIT` | Mathias Buus <mathiasbuus@gmail.com> |
| `es-define-property` | `1.0.1` | `MIT` | Jordan Harband <ljharb@gmail.com> |
| `es-errors` | `1.3.0` | `MIT` | Jordan Harband <ljharb@gmail.com> |
| `es-object-atoms` | `1.1.1` | `MIT` | Jordan Harband <ljharb@gmail.com> |
| `es-set-tostringtag` | `2.1.0` | `MIT` | Jordan Harband <ljharb@gmail.com> |
| `es6-iterator` | `2.0.3` | `MIT` | Mariusz Nowak <medyk@medikoo.com> (http://www.medikoo.com/) |
| `es6-symbol` | `3.1.3` | `ISC` | Mariusz Nowak <medyk@medikoo.com> (http://www.medikoo.com/) |
| `esniff` | `2.0.1` | `ISC` | Mariusz Nowak <medyk@medikoo.com> (http://www.medikoo.com/) |
| `event-emitter` | `0.3.5` | `MIT` | Mariusz Nowak <medyk@medikoo.com> (http://www.medikoo.com/) |
| `expand-template` | `2.0.3` | `(MIT OR WTFPL)` | LM <ralphtheninja@riseup.net> |
| `ext` | `1.4.0` | `ISC` | Mariusz Nowak <medyk@medikoo.com> (http://www.medikoo.com/) |
| `file-uri-to-path` | `1.0.0` | `MIT` | Nathan Rajlich <nathan@tootallnate.net> (http://n8.io/) |
| `follow-redirects` | `1.16.1` | `MIT` | Ruben Verborgh <ruben@verborgh.org> (https://ruben.verborgh.org/) |
| `form-data` | `4.0.6` | `MIT` | Felix Geisendörfer <felix@debuggable.com> (http://debuggable.com/) |
| `foundry-local-sdk` | `2.2.1` | `MIT` | — |
| `fs-constants` | `1.0.0` | `MIT` | Mathias Buus (@mafintosh) |
| `fs-extra` | `11.2.0` | `MIT` | JP Richardson <jprichardson@gmail.com> |
| `function-bind` | `1.1.2` | `MIT` | Raynos <raynos2@gmail.com> |
| `get-intrinsic` | `1.3.0` | `MIT` | Jordan Harband <ljharb@gmail.com> |
| `get-proto` | `1.0.1` | `MIT` | Jordan Harband <ljharb@gmail.com> |
| `github-from-package` | `0.0.0` | `MIT` | James Halliday |
| `gopd` | `1.2.0` | `MIT` | Jordan Harband <ljharb@gmail.com> |
| `graceful-fs` | `4.2.11` | `ISC` | — |
| `has-symbols` | `1.1.0` | `MIT` | Jordan Harband |
| `has-tostringtag` | `1.0.2` | `MIT` | Jordan Harband |
| `hasown` | `2.0.4` | `MIT` | Jordan Harband <ljharb@gmail.com> |
| `http-proxy-agent` | `7.0.2` | `MIT` | Nathan Rajlich <nathan@tootallnate.net> (http://n8.io/) |
| `https-proxy-agent` | `7.0.6` | `MIT` | Nathan Rajlich <nathan@tootallnate.net> (http://n8.io/) |
| `ieee754` | `1.2.1` | `BSD-3-Clause` | Feross Aboukhadijeh |
| `inherits` | `2.0.4` | `ISC` | — |
| `ini` | `1.3.8` | `ISC` | Isaac Z. Schlueter <i@izs.me> (http://blog.izs.me/) |
| `ip-address` | `10.7.2` | `MIT` | Beau Gunderson <beau@beaugunderson.com> (https://beaugunderson.com/) |
| `is-extglob` | `2.1.1` | `MIT` | Jon Schlinkert (https://github.com/jonschlinkert) |
| `is-glob` | `4.0.3` | `MIT` | Jon Schlinkert (https://github.com/jonschlinkert) |
| `is-inside-container` | `1.0.0` | `MIT` | Sindre Sorhus |
| `is-typedarray` | `1.0.0` | `MIT` | Hugh Kennedy <hughskennedy@gmail.com> (http://hughsk.io/) |
| `jschardet` | `3.1.4` | `LGPL-2.1+` | António Afonso |
| `json-schema-to-ts` | `3.1.1` | `MIT` | Thomas Aribart |
| `jsonfile` | `6.1.0` | `MIT` | JP Richardson <jprichardson@gmail.com> |
| `katex` | `0.16.22` | `MIT` | — |
| `kerberos` | `2.1.1` | `Apache-2.0` | The MongoDB NodeJS Team |
| `libsodium` | `0.8.4` | `ISC` | Ahmad Ben Mrad (@BatikhSouri) |
| `libsodium-wrappers` | `0.8.4` | `ISC` | Ahmad Ben Mrad (@BatikhSouri) |
| `lossless-json` | `4.3.3` | `MIT` | Jos de Jong |
| `math-intrinsics` | `1.1.0` | `MIT` | Jordan Harband <ljharb@gmail.com> |
| `miller-rabin` | `4.0.1` | `MIT` | Fedor Indutny <fedor@indutny.com> |
| `mime-db` | `1.52.0` | `MIT` | — |
| `minimist` | `1.2.8` | `MIT` | James Halliday |
| `minipass` | `7.1.3` | `BlueOak-1.0.0` | Isaac Z. Schlueter <i@izs.me> (http://blog.izs.me/) |
| `minizlib` | `3.1.0` | `MIT` | Isaac Z. Schlueter <i@izs.me> (http://blog.izs.me/) |
| `mkdirp-classic` | `0.5.3` | `MIT` | Mathias Buus (@mafintosh) |
| `ms` | `2.1.3` | `MIT` | — |
| `napi-build-utils` | `1.0.2` | `MIT` | Jim Schlight |
| `native-is-elevated` | `0.9.0` | `MIT` | arkon |
| `native-keymap` | `3.3.9` | `MIT` | Microsoft Corporation |
| `next-tick` | `1.1.0` | `ISC` | Mariusz Nowak <medyk@medikoo.com> (http://www.medikoo.com/) |
| `node-abi` | `3.8.0` | `MIT` | Lukas Geiger |
| `node-gyp-build` | `4.8.1` | `MIT` | Mathias Buus (@mafintosh) |
| `node-pty` | `1.2.0-beta.18` | `MIT` | Microsoft Corporation |
| `once` | `1.4.0` | `ISC` | Isaac Z. Schlueter <i@izs.me> (http://blog.izs.me/) |
| `open` | `10.1.2` | `MIT` | Sindre Sorhus |
| `opentype.js` | `2.0.0` | `MIT` | Frederik De Bleser |
| `pend` | `1.2.0` | `MIT` | Andrew Kelley <superjoe30@gmail.com> |
| `picomatch` | `4.0.5` | `MIT` | Jon Schlinkert (https://github.com/jonschlinkert) |
| `playwright-core` | `1.61.0-alpha-2026-06-04` | `Apache-2.0` | Microsoft Corporation |
| `proxy-from-env` | `2.1.0` | `MIT` | Rob Wu <rob@robwu.nl> (https://robwu.nl/) |
| `pump` | `3.0.4` | `MIT` | Mathias Buus Madsen <mathiasbuus@gmail.com> |
| `randombytes` | `2.1.0` | `MIT` | — |
| `rc` | `1.2.8` | `(BSD-2-Clause OR MIT OR Apache-2.0)` | Dominic Tarr <dominic.tarr@gmail.com> (dominictarr.com) |
| `readable-stream` | `3.6.0` | `MIT` | — |
| `run-applescript` | `7.0.0` | `MIT` | Sindre Sorhus |
| `safe-buffer` | `5.1.2` | `MIT` | Feross Aboukhadijeh |
| `safer-buffer` | `2.1.2` | `MIT` | Nikita Skovoroda |
| `semver` | `7.8.5` | `ISC` | GitHub Inc. |
| `shell-quote` | `1.12.0` | `MIT` | James Halliday |
| `simple-concat` | `1.0.1` | `MIT` | Feross Aboukhadijeh |
| `simple-get` | `4.0.1` | `MIT` | Feross Aboukhadijeh |
| `smart-buffer` | `4.2.0` | `MIT` | Josh Glazebrook |
| `socks` | `2.8.8` | `MIT` | Josh Glazebrook |
| `socks-proxy-agent` | `8.0.5` | `MIT` | Nathan Rajlich |
| `ssh2` | `1.17.0` | `MIT` | Brian White <mscdex@mscdex.net> |
| `string_decoder` | `1.1.1` | `MIT` | — |
| `tar` | `7.5.22` | `BlueOak-1.0.0` | Isaac Z. Schlueter |
| `tas-client` | `0.4.6` | `MIT` | Microsoft |
| `ts-algebra` | `2.0.0` | `MIT` | Thomas Aribart |
| `tslib` | `2.8.1` | `0BSD` | Microsoft Corp. |
| `tunnel-agent` | `0.6.0` | `Apache-2.0` | Mikeal Rogers <mikeal.rogers@gmail.com> (http://www.futurealoof.com) |
| `tweetnacl` | `0.14.5` | `Unlicense` | TweetNaCl-js contributors |
| `type` | `2.7.2` | `ISC` | Mariusz Nowak <medyk@medikoo.com> (https://www.medikoo.com/) |
| `typedarray-to-buffer` | `3.1.5` | `MIT` | Feross Aboukhadijeh |
| `undici` | `7.29.1` | `MIT` | — |
| `universalify` | `2.0.1` | `MIT` | Ryan Zimmerman <opensrc@ryanzim.com> |
| `utf-8-validate` | `5.0.10` | `MIT` | Einar Otto Stangvik <einaros@gmail.com> (http://2x.io) |
| `util-deprecate` | `1.0.2` | `MIT` | Nathan Rajlich <nathan@tootallnate.net> (http://n8.io/) |
| `uuid` | `3.4.0` | `MIT` | — |
| `vscode-jsonrpc` | `4.0.0` | `MIT` | Microsoft Corporation |
| `vscode-oniguruma` | `1.7.0` | `MIT` | Microsoft Corporation |
| `vscode-regexpp` | `3.1.0` | `MIT` | Toru Nagashima (https://github.com/mysticatea) |
| `vscode-textmate` | `9.3.2` | `MIT` | Microsoft Corporation |
| `websocket` | `1.0.35` | `Apache-2.0` | Brian McKelvey <theturtle32@gmail.com> (https://github.com/theturtle32) |
| `windows-foreground-love` | `0.6.1` | `MIT` | Tereza Tomcova |
| `wrappy` | `1.0.2` | `ISC` | Isaac Z. Schlueter <i@izs.me> (http://blog.izs.me/) |
| `ws` | `8.21.0` | `MIT` | Einar Otto Stangvik <einaros@gmail.com> (http://2x.io) |
| `yaeti` | `0.0.6` | `MIT` | Iñaki Baz Castillo <ibc@aliax.net> |
| `yauzl` | `3.3.1` | `MIT` | Josh Wolfe <thejoshwolfe@gmail.com> |
| `yazl` | `2.4.3` | `MIT` | Josh Wolfe <thejoshwolfe@gmail.com> |
| `zod` | `4.4.3` | `MIT` | Colin McDonnell <zod@colinhacks.com> |

---

## 5. Additional Bundled Assets, Tools & Audit Flags

The following non-npm / special assets are present in the repository or staging tools directory and require careful compliance tracking (see [`LICENSE-AUDIT.md`](LICENSE-AUDIT.md) for classification and remediation details):

1. **`@vscode/copilot-api@0.5.2` (`RESTRICTED`):** Bundled inside `node_modules.asar` and referenced by root/`remote`/`copilot`. Its proprietary GitHub license limits usage strictly to Microsoft Visual Studio Code / Code-OSS (dev only) and prohibits third-party redistribution.
2. **`resources/tools/darwin.xtoolsdk` (`RESTRICTED`):** Archive containing extracted Apple `iPhoneOS.sdk`, `MacOSX27.2.sdk`, `iPhoneSimulator27.2.sdk`, `StoreKitTest.framework`, `XCTest.framework`, and LLVM `ld64.lld`/`llvm-lib`/`dsymutil` toolset. Apple SDK redistribution requires explicit Apple licensing.
3. **`resources/tools/xtool/linux/xtool` & `squashfs-root` (`REVIEW REQUIRED / LGPL-GPL`):** Bundled Linux AppImage and 23 Debian/Ubuntu shared libraries including LGPL-2.1+/3.0+ and GPL-2.0+/3.0+ components (`libgnutls30`, `libhogweed6`, `libnettle8`, `libidn2-0`, `libunistring2`, `libp11-kit0`, `librtmp1`, `libssh-4`, `libtasn1-6`, `libzstd1`, `libicu70`, `libssl3`, `libcurl4`, etc.).
4. **`@anthropic-ai/claude-agent-sdk@0.3.304` (`RESTRICTED if shipped`):** Present in `devDependencies` / `build/agent-sdk` (`© Anthropic PBC. All rights reserved.`).
5. **Inno Setup `6.4.1` (`build tool`):** Installer wrapper copyrighted by Jordan Russell & Martijn Laan (`Open Source` Inno Setup License).

---

## 6. Root `ThirdPartyNotices.txt` Component Index (82 Entries)

Complete license texts and original copyright notices for all syntax grammars, editor helpers, and bundled Code - OSS libraries are reproduced in full inside [`ThirdPartyNotices.txt`](ThirdPartyNotices.txt):

1. `@fig/autocomplete-shared 1.1.2`
2. `@iktakahiro/markdown-it-katex 4.0.2 - MIT`
3. `amazon-q-developer-cli f66e0b0e917ab185eef528dc36eca56b78ca8b5d`
4. `atom/language-clojure 0.22.8 - MIT`
5. `atom/language-coffee-script 0.49.3 - MIT`
6. `atom/language-sass 0.62.1 - MIT`
7. `atom/language-xml 0.35.2 - MIT`
8. `autocomplete 2.684.0 - MIT`
9. `cacheable-request 7.0.4 - MIT`
10. `codex`
11. `Colorsublime-Themes 0.1.0`
12. `daaain/Handlebars 1.8.0 - MIT`
13. `dart-lang/dart-syntax-highlight 0.0.0 - BSD`
14. `davidrios/pug-tmbundle 0.0.0 - MIT`
15. `definitelytyped  - MIT`
16. `Document Object Model 4.0.0 - W3C License`
17. `dompurify 3.2.7 - Apache 2.0`
18. `dotenv-org/dotenv-vscode 0.26.0 - MIT License`
19. `dotnet/csharp-tmLanguage 0.1.0 - MIT`
20. `dotnet/razor 1.0.0 - MIT`
21. `expand-abbreviation 0.5.8 - MIT`
22. `fadeevab/make.tmbundle 0.0.0 - TextMate Bundle License`
23. `fish-shell 3.7.1`
24. `go-syntax 0.8.6 - MIT`
25. `HTML 5.1 W3C Working Draft 08 October 2015 - W3C Document License`
26. `Ionic documentation 1.2.4 - Apache-2.0`
27. `ionide/ionide-fsgrammar 0.0.0 - MIT`
28. `James-Yu/LaTeX-Workshop 8.19.1 - MIT`
29. `jeff-hykin/better-c-syntax 1.13.2 - MIT`
30. `jeff-hykin/better-cpp-syntax 1.17.4 - MIT`
31. `jeff-hykin/better-objc-syntax 0.2.0 - MIT`
32. `jeff-hykin/better-objcpp-syntax 0.1.0 - MIT`
33. `jeff-hykin/better-shell-syntax 1.8.7 - MIT`
34. `jeff-hykin/better-snippet-syntax 1.0.2 - MIT`
35. `jlelong/vscode-latex-basics 1.16.0 - MIT`
36. `js-beautify 1.6.8 - MIT`
37. `jtbandes/swift-tmlanguage  - MIT`
38. `JuliaEditorSupport/atom-language-julia 0.23.0 - MIT`
39. `Jxck/assert 1.0.0 - MIT`
40. `language-docker 28.3.3 - Apache-2.0`
41. `language-less 0.6.1 - MIT`
42. `language-php 0.49.0 - MIT`
43. `MagicStack/MagicPython 1.1.1 - MIT`
44. `marked 14.0.0 - MIT`
45. `microsoft/TypeScript-TmLanguage 0.0.1 - MIT`
46. `microsoft/vscode-css 0.0.0 - MIT License`
47. `microsoft/vscode-JSON.tmLanguage 0.0.0 - MIT`
48. `microsoft/vscode-markdown-tm-grammar 1.0.0 - MIT`
49. `microsoft/vscode-mssql 1.0.0 - MIT`
50. `mmims/language-batchfile 0.7.6 - MIT`
51. `NVIDIA/cuda-cpp-grammar 0.0.0 - MIT`
52. `PowerShell/EditorSyntax 1.0.0 - MIT`
53. `PSReadLine 2.4.4-beta4`
54. `RedCMD/YAML-Syntax-Highlighter 1.3.2 - MIT`
55. `redhat-developer/vscode-java 1.26.0 - MIT`
56. `REditorSupport/vscode-R 0.1.1 - MIT`
57. `rust-syntax 0.6.1 - MIT`
58. `semver 5.5.0 - The ISC License`
59. `seti-ui 0.1.0`
60. `shaders-tmLanguage 0.1.0 - MIT`
61. `Shopify/ruby-lsp 0.0.0 - MIT License`
62. `sumneko/lua.tmbundle 1.0.0 - TextMate Bundle License`
63. `textmate/asp.vb.net.tmbundle 0.0.0 - TextMate Bundle License`
64. `textmate/c.tmbundle 0.0.0 - TextMate Bundle License`
65. `textmate/diff.tmbundle 0.0.0 - TextMate Bundle License`
66. `textmate/git.tmbundle 0.0.0 - MIT`
67. `textmate/groovy.tmbundle 0.0.0 - TextMate Bundle License`
68. `textmate/html.tmbundle 0.0.0 - TextMate Bundle License`
69. `textmate/ini.tmbundle 0.0.0 - TextMate Bundle License`
70. `textmate/javascript.tmbundle 0.0.0 - TextMate Bundle License`
71. `textmate/markdown.tmbundle 0.0.0 - TextMate Bundle License`
72. `textmate/perl.tmbundle 0.0.0 - TextMate Bundle License`
73. `trond-snekvik/vscode-rst 1.5.3 - MIT`
74. `TypeScript-TmLanguage 0.1.8 - MIT`
75. `Unicode 12.0.0 - UNICODE, INC. LICENSE AGREEMENT - DATA FILES AND SOFTWARE`
76. `vscode-codicons 0.0.46-0 - MIT and Creative Commons Attribution 4.0`
77. `vscode-logfile-highlighter 3.4.0 - MIT`
78. `vscode-swift 0.0.1 - MIT`
79. `vscode-win32-app-container-tokens`
80. `walles/git-commit-message-plus 1.0.0 - MIT`
81. `Web Background Synchronization  - Apache-2.0`
82. `zsh 5.9`

---

## 7. Standard Third-Party License Texts

### 7.1 MIT License (Microsoft Visual Studio Code, Electron, Node.js, xTool & MIT Packages)

```text
Copyright (c) 2015 - present Microsoft Corporation (Visual Studio Code / Code - OSS)
Copyright (c) 2024 Kabir Oberai (xTool)
Copyright (c) Electron contributors & GitHub Inc. (Electron)
Copyright (c) Node.js contributors / OpenJS Foundation (Node.js)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

### 7.2 BSD 3-Clause License (Chromium, V8 & BSD-3-Clause Packages)

```text
Copyright (c) The Chromium Authors. All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

   * Redistributions of source code must retain the above copyright notice,
     this list of conditions and the following disclaimer.
   * Redistributions in binary form must reproduce the above copyright notice,
     this list of conditions and the following disclaimer in the documentation
     and/or other materials provided with the distribution.
   * Neither the name of Google LLC / the copyright holder nor the names of its
     contributors may be used to endorse or promote products derived from this
     software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE FOR
ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES
(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES;
LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON
ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS
SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```

### 7.3 Apache License 2.0 (Summary & Reference)

Components licensed under Apache License, Version 2.0 (`@vscode/sandbox-runtime`, `detect-libc`, `kerberos`, `playwright-core`, `dompurify` option, and Rust crates) are distributed under the terms of the [Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0). Original copyright statements, patent grant/retaliation terms, and `NOTICE` files remain intact within the installed package directories (`node_modules` / `node_modules.asar`).

### 7.4 GNU Lesser General Public License v2.1+ (`FFmpeg`, `jschardet`)

- **FFmpeg** (`ffmpeg.dll`) and **`jschardet`** (`3.1.4`) are licensed under the **GNU Lesser General Public License, Version 2.1 (or later)**: <https://www.gnu.org/licenses/old-licenses/lgpl-2.1.html>.
- Full LGPL-2.1 text is also preserved inside `LICENSES.chromium.html` and `node_modules.asar` (`jschardet/LICENSE`).
- Consistent with LGPL Section 6, CodeX users retain the freedom to modify these LGPL libraries for their own use, relink/replace dynamically linked `ffmpeg.dll` with a compatible build, and perform reverse engineering solely to debug permitted LGPL modifications.

### 7.5 GitHub Copilot CLI License (`@github/copilot@1.0.73`)

```text
GitHub Copilot CLI License

1. License Grant
   Subject to the terms of this License, GitHub grants you a non‑exclusive, non‑transferable, royalty‑free license to install and run copies of the GitHub Copilot CLI (the “Software”). Subject to Section 2 below, GitHub also grants you the right to reproduce and redistribute unmodified copies of the Software as part of an application or service.

2. Redistribution Rights and Conditions
   You may reproduce and redistribute the Software only in accordance with all of the following conditions:
   The Software is distributed only in unmodified form;
   The Software is redistributed solely as part of an application or service that provides material functionality beyond the Software itself;
   The Software is not distributed on a standalone basis or as a primary product;
   You include a copy of this License and retain all applicable copyright, trademark, and attribution notices; and
   Your application or service is licensed independently of the Software.
   Nothing in this License restricts your choice of license for your application or service, including distribution under an open source license. This License applies solely to the Software and does not modify or supersede the license terms governing your application or its source code.

3. Scope Limitations
   This License does not grant you the right to:
   Modify, adapt, translate, or create derivative works of the Software;
   Redistribute the Software except as expressly permitted in Section 2;
   Remove, alter, or obscure any proprietary notices included in the Software; or
   Use GitHub trademarks, logos, or branding except as necessary to identify the Software.

4. Reservation of Rights
   GitHub and its licensors retain all right, title, and interest in and to the Software. All rights not expressly granted by this License are reserved.

5. Disclaimer of Warranty
   THE SOFTWARE IS PROVIDED “AS IS,” WITHOUT WARRANTY OF ANY KIND, EXPRESS, IMPLIED, OR STATUTORY, INCLUDING WITHOUT LIMITATION WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, AND NON‑INFRINGEMENT. THE ENTIRE RISK ARISING OUT OF USE OF THE SOFTWARE REMAINS WITH YOU.

6. Limitation of Liability
   TO THE MAXIMUM EXTENT PERMITTED BY LAW, IN NO EVENT SHALL GITHUB OR ITS LICENSORS BE LIABLE FOR ANY DAMAGES ARISING OUT OF OR RELATING TO THIS LICENSE OR THE USE OR DISTRIBUTION OF THE SOFTWARE, WHETHER IN CONTRACT, TORT, OR OTHERWISE.

7. Termination
   This License terminates automatically if you fail to comply with its terms. Upon termination, you must cease all use and distribution of the Software.

8. Notice Regarding GitHub Services (Informational Only)
   Use of the Software may require access to GitHub services and is subject to the applicable GitHub Terms of Service and GitHub Copilot terms. This License governs only rights related to the Software and does not grant any rights to access or use GitHub services.
```

---

*Prepared from verified repository manifests, ASAR archives, and binary inspections. This document does not constitute formal legal certification.*
