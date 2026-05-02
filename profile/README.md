# OpenPiste

**Open source fencing electronics and IT platform**

Fencing electronics are expensive. A scoring device from a commercial supplier can cost several thousand euros. Repeater displays, video refereeing systems, and competition display software add more. Clubs and federations pay for proprietary hardware that is difficult to maintain, impossible to modify, and locks them into a single vendor.

OpenPiste is the alternative.

---

## What OpenPiste is

A complete, open source platform covering everything a club or federation needs to run a piste electronically:

- **Scoring device** — ESP32-based, full-spec, field-tested
- **Weapon and wire tester** — redesigned for armourers with no technical background
- **Remote controls** — Android app or dedicated hardware touchscreen (CYD)
- **Piste monitor** — browser-based, no app required, single piste or multi-piste overview with fencer photos
- **Wireless repeater displays** — via ESP-NOW, no WiFi or wiring needed
- **Open hardware designs** — schematics and PCB layouts included

Everything runs on standard, affordable components. The scoring device is powered by USB-C at 5V — any powerbank will do.

---

## Built to work with what you already have

OpenPiste speaks the industry-standard protocols used by professional commercial equipment:

| Protocol | Purpose |
|----------|---------|
| **Cyrano (UDP)** | Competition management — works with FencingTime, Engarde, FencingFox and others |
| **FPA (UDP)** | Real-time data — Android remote, CYD hardware remote, video refereeing via the free [SFS iOS app](https://superfencingsystem.com/) |
| **ESP-NOW** | Wireless repeater displays — direct device-to-device, no WiFi required |
| **MQTT / JSON** | Modern open layer — currently powers the piste monitor; broader ecosystem integration planned |

No changes to your existing competition software. No migration required. Drop it in and it works.

---

## The ecosystem

```
Scoring device
      │
      ├─── Cyrano (UDP) ──► FencingTime / Engarde / FencingFox
      │
      ├─── FPA (UDP) ─────► SFS video referee app (iOS)
      │                 ├─► Android remote control app
      │                 └─► CYD hardware remote
      │
      ├─── ESP-NOW ───────► Wireless repeater displays (no WiFi required)
      │
      └─── MQTT ──────────► Raspberry Pi
                                  └─── Piste monitor (browser)
                                       single piste or multi-piste overview
```

The Raspberry Pi runs the MQTT broker and the piste monitor web server. The local broker can be bridged to a global one, enabling remote monitoring from anywhere in the world. MQTT support for remotes and other clients is planned for a future phase.

---

## Field-tested

The weapon and wire tester was significantly redesigned based on direct feedback from professional armourers at the **European Fencing Championships in Genova**, where the project founder worked as EFC SEMI delegate. The goal: a device that anyone can use confidently, with no technical background required.

---

## Repositories

| Repo | Description |
|------|-------------|
| [esp32scoringdeviceMqtt](https://github.com/pietwauters/esp32scoringdeviceMqtt) | Scoring device firmware — active development |
| [ImprovedTesterAfterGenova](https://github.com/pietwauters/ImprovedTesterAfterGenova) | Weapon and wire tester — active development |
| [remotecontrolapp](https://github.com/pietwauters/remotecontrolapp) | Android remote control app (Kotlin) |
| [CYDRemoteControl](https://github.com/pietwauters/CYDRemoteControl) | Hardware remote control (ESP32 + touchscreen) |
| [CyranoPisteMonitor](https://github.com/pietwauters/CyranoPisteMonitor) | Browser-based piste monitor |
| [esp32_scoring_device_hardware](https://github.com/pietwauters/esp32_scoring_device_hardware) | Electronics designs — schematics and PCBs |

---

## About

OpenPiste is a volunteer open source project by **Piet Wauters** (Hasselt, Belgium), member of the FIE SEMI Commission and EFC SEMI Commission — the technology commissions of the International and European Fencing Federations.

All contributions are welcome. See the individual repos for details.
