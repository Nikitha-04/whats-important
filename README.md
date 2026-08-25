# 📱 WA Important — Smart WhatsApp Message Manager

![Platform](https://img.shields.io/badge/platform-Android-3DDC84?logo=android)
![Language](https://img.shields.io/badge/language-Kotlin-7F52FF?logo=kotlin)
![Min SDK](https://img.shields.io/badge/minSDK-26-blue)
![Privacy](https://img.shields.io/badge/data-100%25%20on--device-success)

> **Never miss what truly matters in the noise of endless notifications.**
> *Built for productivity and peace of mind.*

---

## 🚀 The Problem

WhatsApp and WhatsApp Business accounts are flooded with hundreds of messages a day — casual chats, group pings, promotional spam. The sheer volume makes it easy to miss what actually matters: an urgent text from a boss, a request from family, or a message carrying a critical keyword like *"payment"* or *"urgent"*.

Making this worse, many Android OEMs (vivo, iQOO, Xiaomi, OnePlus) aggressively kill background services to save battery. A naive listener app simply stops working — silently — and you never know what you missed.

## 💡 The Solution

**WA Important** is a lightweight, privacy-first Android app that acts as a smart filter layer for your WhatsApp notifications. It listens to incoming messages on-device and categorizes them in real time using rules you define — no cloud, no accounts, nothing ever leaves your phone.

Instead of opening WhatsApp to a sea of unread chats, open **WA Important** to see exactly what needs your attention.

## ⚙️ How It Works

```
WhatsApp Notification
        │
        ▼
NotificationListenerService (foreground, survives OEM battery kill)
        │
        ▼
Message Parsing — sender, text, group vs. DM, timestamp
        │
        ▼
Rule Engine — keyword match · sender priority · custom rules
        │
        ▼
Flagged as Important? ── Yes → ⭐ Important tab
                       └─ No  → All Messages tab
```

## ✨ Key Features

- **🔔 Live Message Capture** — Instantly reads and logs incoming messages from both **WhatsApp** and **WhatsApp Business**.
- **⭐ Smart Importance Filtering** — Create rules combining **sender name** and **keywords**.
  - *Flag all messages from "Mom"*
  - *Flag any message containing "urgent"*
  - *Flag messages from "Boss" containing "meeting"*
- **🗂️ Dual-Tab UI** — Clean Jetpack Compose interface to switch between *All Messages* and *⭐ Important*.
- **💾 Persistent Rules** — Filtering rules are saved on-device and survive restarts.
- **🔋 Built to Survive OEM Battery Management** — Foreground service + persistent notification keeps the listener alive on aggressive Android skins.
- **🔒 Privacy First** — 100% offline. No messages, contacts, or personal data ever leave your device.

## 🛠️ Technical Implementation

| Layer | Details |
|---|---|
| **Language** | Kotlin |
| **UI** | Jetpack Compose (Material Design 3) |
| **Notification Capture** | `NotificationListenerService`, foreground service for reliability on OEM skins |
| **Reactivity** | `StateFlow` + Coroutines for instant UI updates |
| **Persistence** | File-based local storage (`JSONObject` / `JSONArray`) for rules |
| **Compatibility** | Android 8.0 (API 26) → Android 14 (API 34) |

## 🚀 Getting Started

1. Install the APK on your Android device.
2. Grant **Notification Access** when prompted.
3. Tap the **⚙ Settings** icon to configure your Important Filter rules.
4. Sit back and let WA Important curate your notifications.

## 🗺️ Roadmap

- [ ] Time-of-day sensitivity in rules
- [ ] Heads-up alert / daily digest notification
- [ ] Device-specific autostart/whitelist guidance (vivo, iQOO, Xiaomi)
- [ ] Room database migration for rule + message storage

## 👥 Team

WA Important is built by a two-person team, split across the two hardest parts of the problem:

| Role | Owner | Focus |
|---|---|---|
| **Notification & Platform Engineer** | @Nikitha(#) | Reliable notification capture, foreground service, keeping the listener alive under aggressive OEM battery management (vivo/iQOO/Xiaomi/OnePlus) |
| **Rule Engine & UI Engineer** | @Mohan(#) | Rule/scoring logic for what counts as "important," and the Jetpack Compose UI that surfaces it |

## 🔒 Privacy First

WA Important **never**:
- Uploads your messages to any server
- Requires a login or account
- Shares data with third parties

It reads notification content the same way your smartwatch or Bluetooth headset does — via Android's standard `NotificationListenerService` API.

---

*Built with ❤️ to bring focus back to your digital life.*
