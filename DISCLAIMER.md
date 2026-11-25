# CodeX — Software Disclaimer & Pre-Release Risk Notice

**Product:** CodeX (v1.148.0)  
**Developer & Copyright Holder:** Alperen AKKAYA  
**Repository:** <https://github.com/AlperenAKKAYA99/CodeX>

---

## 1. Beta & Experimental Software Notice

CodeX and several of its integrated subsystems are currently under active development and contain **beta, preview, and experimental features**. By downloading, installing, or operating CodeX, you acknowledge that experimental workflows may change, contain defects, or behave unexpectedly in production environments.

Specifically, the following capabilities are provided on an experimental / preview basis:

- **Windows-to-WSL Swift/iOS Build Bridge (`xtool-bridge.mjs` & `extract-sdk.py`):** Automated path translation, tar/Python SDK extraction workarounds for WSL 1/WSL 2 environments, and cross-platform Swift/iOS compilation pipelines.
- **Automated Environment Provisioning (`install-wsl.cmd`):** Elevated installer/Quick-Action routines that configure Windows Subsystem for Linux (WSL) and Ubuntu distributions on your host machine.
- **CodeX iOS Simulator:** A WebView-based SwiftUI source parser, state tracker, and visual UI renderer for rapid interface previewing. **Important:** The built-in simulator renders UI representations from source code and does **not** emulate Apple ARM64 iOS hardware or execute compiled Mach-O iOS binaries natively on Windows.
- **Device Deployment, Signing & Debugging:** USB device communication, syslog streaming, LLDB-DAP debugging, and third-party authentication/signing flows involving Apple developer accounts.
- **AI Coding Assistants:** Optional integration points for AI models and external SDKs.

---

## 2. Data Loss, Environment & Security Risks

You are solely responsible for maintaining backups of your source code, project repositories, signing certificates, provisioning profiles, environment variables, and operating system state.

- Running automated installers, WSL provisioning scripts, build cleanup tasks, debugger sessions, or AI coding tools carries an inherent risk of file modification, configuration changes, build failures, or data loss.
- Do not rely on preview or unverified builds for safety-critical, medical, aviation, financial infrastructure, or mission-critical production systems without independent verification and backups.

---

## 3. No Warranty ("AS IS" and "AS AVAILABLE")

TO THE MAXIMUM EXTENT PERMITTED BY APPLICABLE LAW, CODEX AND ALL ACCOMPANYING DOCUMENTATION, TOOLS, EXTENSIONS, AND INSTALLERS ARE PROVIDED **"AS IS"** AND **"AS AVAILABLE"**, WITH ALL FAULTS AND WITHOUT WARRANTY OF ANY KIND.

Alperen AKKAYA expressly disclaims all warranties, express, implied, statutory, or otherwise, including without limitation implied warranties of:

- Merchantability and satisfactory quality,
- Fitness for a particular purpose,
- Title and non-infringement of third-party intellectual property rights,
- Continuous availability, accuracy, security, or compatibility with future operating system updates, Apple SDK changes, Xcode formats, or WSL kernel updates.

---

## 4. Limitation of Liability

TO THE MAXIMUM EXTENT PERMITTED BY APPLICABLE LAW, IN NO EVENT SHALL ALPEREN AKKAYA OR CONTRIBUTORS BE LIABLE FOR ANY INDIRECT, INCIDENTAL, SPECIAL, CONSEQUENTIAL, EXEMPLARY, OR PUNITIVE DAMAGES WHATSOEVER (INCLUDING DAMAGES FOR LOSS OF PROFITS, DATA LOSS, CORRUPTION OF REPOSITORIES OR WORKSPACES, SYSTEM DOWNTIME, HARDWARE ISSUES, OR COST OF PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES) ARISING OUT OF OR RELATED TO THE USE OF OR INABILITY TO USE CODEX, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGES.

### Statutory & Consumer Law Savings Clause (Republic of Türkiye & International)

Nothing in this Disclaimer excludes or limits any warranty or liability that cannot lawfully be excluded or limited under applicable mandatory law. In particular, under the laws of the **Republic of Türkiye** (including the Law on the Protection of Consumers No. 6502 / *Tüketicinin Korunması Hakkında Kanun* and mandatory provisions of the Turkish Code of Obligations / *Türk Borçlar Kanunu*), mandatory liability for intent (*kast*), gross negligence (*ağır kusur*), personal injury, or non-waivable statutory consumer remedies remains unaffected where applicable.

---

## 5. Third-Party Services, SDKs, and External Accounts

CodeX may interact with third-party platforms and services—including Apple Developer services, Apple iOS devices, GitHub, GitHub Copilot, Anthropic APIs, and Microsoft Windows/WSL components.

- Alperen AKKAYA makes no representations or warranties regarding third-party software, SDKs, API availability, or third-party account standing (such as Apple Developer certificate/account status).
- Use of external SDKs, cloud AI APIs, or device signing credentials is governed strictly by the terms of service and license agreements of the respective third-party providers.
- Certain third-party artifacts inspected in [LICENSE-AUDIT.md](LICENSE-AUDIT.md) remain subject to third-party licensing restrictions and legal counsel review.

---

## 6. No Legal Certification

Legal and licensing files in this repository are prepared for structured technical compliance documentation and product clarity. They do not constitute formal legal advice or certified legal clearance. Qualified legal counsel should review specific commercial, export, consumer, or third-party SDK redistribution obligations prior to broad commercial release.

---

*See also: [LICENSE](LICENSE) · [EULA.md](EULA.md) · [LICENSING.md](LICENSING.md) · [COPYRIGHT.md](COPYRIGHT.md) · [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md) · [LICENSE-AUDIT.md](LICENSE-AUDIT.md)*
