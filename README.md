# Table of Contents
- Introduction
- Methodology
- Timeline
- Device Matrix
- Observational Patterns
- Glossary
- Tools & Inspection Utilities
- Goal

---

## 📘 Introduction
It didn’t start with a flashing warning or a big breach. It started with something small — small enough to ignore.  

Fresh off a factory reset, the VivoBook demanded the BitLocker recovery key. Instead of the normal sign-in flow, Windows flagged the personal account as a “work email.” Off at first glance, but not urgent.  

That changed quickly. Unexpected prompts, settings shifting on their own, and subtle changes began to stack up. Within weeks, the same disturbances showed up across other devices.  

No help came — not from professionals, not from the inner circle. The problem was too strange, too invisible for anyone else to believe. Clean installs, factory resets, and config changes failed. Repair attempts gave way to a new approach: documentation.  

This repository is the result of months of investigation, built in real time, on compromised hardware, without a safety net. Not a clean lab. Not a theory exercise. Every entry is drawn from direct, repeatable experience.  

One small event was all it took. From there, the unraveling gathered its own momentum.  

Designed for clarity, reproducibility, and empowerment — not for academic polish or institutional approval. Every byte recorded here is observed, not assumed.  

---

## 🧭 Methodology
This work is guided by six vectors: **Work Profile, Data Exfiltration, Telephony, Overlay & UI, Test & Debug, Persistence.** Every app and system process is mapped against these vectors at the forensic level.  

The approach combines:  
- Community knowledge (Google, Reddit, XDA) — real-world cases and shared exploits.  
- App tooling — Inure, App Manager, Fing, NetGuard, RethinkDNS, APK Mirror.  
- Direct observation — logging device activity, overlays, telephony, and persistence testing.  

---

## 📅 Timeline of Events

**January 2025**  
Initial signs appear after a factory reset on the Asus VivoBook. Attempting to retrieve the BitLocker key triggers a “work email” login prompt on a personal account — later tied to unauthorized MDM enrollment. Early system shifts surface.  

**February 2025**  
Laptop anomalies persist. Forced updates, network instability, and permission resets continue. Suspicion builds, but the full scope isn’t yet connected across devices.  

**March 2025**  
Escalation. Physical theft coincides with forced resets, unauthorized changes, and confirmed SIM manipulation. Three devices compromised: Asus VivoBook, OnePlus 6T, BLU V.  

**April 2025**  
Two new devices join: TCL K24 and Celeron 5. TCL K24 shows abnormal behavior within minutes of Wi-Fi login. Celeron 5, with no old accounts, still shows early compromise indicators.  

**May 2025**  
A new iPhone X shows anomalies within 24 hours of Wi-Fi use, followed by SIM swap via eSIM. Around the same time, unsolicited parental control prompts hit the smart TV. By month’s end: six devices compromised.  

**June 2025**  
Research points to router-level interference and MITM-like behavior. Smart TVs show MDM-style controls: blocked stores, lost remotes, irregular MAC addresses.  

**July 2025**  
Mobile app login redirects to an ISP error page. Inspection reveals malformed URL syntax using non-standard slashes — first confirmed case of URL manipulation via glyph drift.  

**August 2025**  
A new router shows DNS traffic rerouted despite Cloudflare settings. A new iPhone stays boxed and offline. Attempts to explain the scope to family end in disbelief. Documentation continues.  

**📌 Current Status (August 2025)**  
All compromised vectors are mapped with precision. Zero tolerance for fluff.  

**Total Compromised Devices: 9**  

---

## 📊 Device Matrix

| Device     | Model / Build                          | OS Version                 | Date of Compromise | Notes                                         |
|------------|----------------------------------------|----------------------------|--------------------|-----------------------------------------------|
| Laptop     | Asus VivoBook                          | Windows 10 Home            | Jan 2025           | Group Policy alerts, BitLocker failure        |
| Phone      | OnePlus 6T (Build: a60104321115)       | Android 11 / OxygenOS 11.1.2.2 | Mar 2025       | SIM swap, recorder app                        |
| Phone      | BLU B160V (aka BLU V)                  | Android 14                 | Mar 2025 (Easter)  | OTA update on low-end hardware                |
| Phone      | TCL K24 (Model: T434D)                 | Android 14                 | Apr 2025           | Settings app vanished post-login              |
| Phone      | Celeron 5G SC (Model: SN339D)          | Android 14                 | Apr 2025           | Early signs after Wi-Fi login                 |
| Phone      | iPhone X                               | iOS                        | May 2025           | Settings vanished, SIM swap via eSIM          |
| Smart TV   | OnnTV                                   | Proprietary OS             | Jun 2025           | Remote failure, store blocked                 |
| Smart TV   | Samsung TV                              | Tizen OS                   | Jun 2025           | Three MAC addresses seen                      |
| Router     | Technicolor                            | N/A                        | Jan 2025           | DNS manipulation, MITM suspected              |
| Router     | Arris                                  | N/A                        | Aug 2025           | DNS set to 1.1.1.1 but rerouted               |
| Phone      | iPhone 11 (new, unused)                | iOS                        | Aug 2025 (unconfirmed) | Never connected to network                  |

---

## 🧠 Observational Patterns
Recurring behaviors across devices:  

- **Settings instability** — disappearing/reappearing after network or account actions.  
- **SIM + network manipulation** — confirmed swaps, DNS rerouting, MITM-like activity.  
- **Cross-device coordination** — changes mirrored across hardware without shared accounts.  
- **Overlay + UI anomalies** — ghost apps, blocked stores, remote control failures.  
- **Encoding obfuscation** — malformed URLs, glyph drift, spoofed characters.  

---

## 🧱 Glossary
Working index for forensic device investigation.  

- **MDM (Mobile Device Management)** — Remote layer for silent installs, restrictions, rerouting.  
- **Device Admin / Device Owner** — Elevated roles granting full device control.  
- **SIM Swap** — Replacing or hijacking a SIM to take service.  
- **DNS Rerouting** — Redirecting internet traffic without consent.  
- **Accessibility Services** — Input tools for disabled users, often exploited for automation.  
- **Ghost Apps** — Apps that appear briefly or run silently.  
- **Overlays** — UI layers spoofing or hijacking app screens.  
- **Logcat** — Android system log viewer for monitoring behavior.  
- **Manifest Drift** — Behavior changes after install without visible updates.  
- **Telemetry** — Silent reporting of usage data.  
- **Obfuscation** — Hiding code, URLs, or app actions.  
- **Unicode / Confusables** — Characters that look identical but act different, often used for spoofing.  

---

## Tools & Inspection Utilities
- **App Manager** — Permission + component breakdown.  
- **Fing** — Network scanner showing router traffic.  
- **NetGuard** — DNS firewall and traffic blocker.  
- **Aurora Store** — Anonymous frontend for Google Play.  
- **APK Mirror** — Archive of official app versions.  

---

## 🔒 Goal
To give clarity and structure for anyone feeling lost, scared, or gaslit — by devices or by people around them. The weight of this experience is hard to grasp unless you’ve lived it.  

This guide is here to remind you: **you are not alone.**
