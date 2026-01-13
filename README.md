# EV Web Dashboard & OTA Platform

*A calm, browser-based interface for configuring, tuning, and updating DIY electric vehicle systems — fully offline.*

---

## What This Is

This project provides a **self-hosted web dashboard** that runs directly on an ESP32-based EV controller.

When you connect to the vehicle over Wi‑Fi and open a browser, you get:

* A live vehicle status dashboard
* A safe, offline firmware upload (OTA) system
* A structured **Tuning Mode** for configuring driveline, inverter, and system parameters

No apps. No cloud. No Internet required.

If a device has a browser, it can talk to the vehicle.

---

## Why It Exists

DIY EV systems are powerful — and often opaque.

Configuration is frequently split across:

* Serial consoles
* CAN tools
* Ad‑hoc scripts
* Undocumented parameters

This project exists to make EV systems:

* **Legible** — the vehicle explains itself
* **Tunable** — parameters are visible, described, and bounded
* **Updatable** — firmware can be safely replaced without special tools
* **Calm** — failure modes are predictable and non‑destructive

---

## Core Features

### Web Dashboard

* Runs entirely on the vehicle controller
* Phone, tablet, and laptop friendly
* Read‑only driving views for safety

### Tuning Mode

* Explicit, gated configuration mode
* All tunable parameters shown with:

  * Plain‑language descriptions
  * Units and valid ranges
  * Defaults and safety notes
* Parameters stored and exchanged as structured JSON
* Support for saving and loading tuning profiles

### Safe OTA Firmware Updates

* Browser‑based firmware upload
* Writes only to the inactive OTA partition
* Verifies firmware before activation
* Failed or interrupted uploads are treated as cancelled
* No bricking from Wi‑Fi dropouts

---

## Who This Is For

This project is designed for people who are **building or integrating EV systems**, including:

* DIY EV converters
* EV shops and builders
* Kit car and experimental vehicle projects
* Educators and hackerspaces
* Open‑source EV controller projects

It assumes:

* You understand what tuning parameters are
* You want control, not magic
* You value clarity over automation theater

It is *not* intended for mass‑market EV owners or zero‑responsibility users.

---

## Stability Model

This project maintains **two release channels**:

* **Development (Open)** — for experimentation and collaboration
* **Stable (Licensed)** — for dependable, real‑world vehicle use

Stable releases are governed by a formal **Stability Promise**.

---

## Documentation Map

This repository is intentionally documentation-first.

Key documents:

- [`INSTALLATION.md`](docs/INSTALLATION.md) — how to get up and running safely
- [`TUNING_MODEL.md`](docs/TUNING_MODEL.md) — how tuning works, and why
- [`STABILITY_PROMISE.md`](docs/STABILITY_PROMISE.md) — guarantees for Stable releases
- [`RELEASE_CHANNELS.md`](docs/RELEASE_CHANNELS.md) — how Development and Stable differ
- [`LICENSING_AND_ACCESS.md`](docs/LICENSING_AND_ACCESS.md) — access model and scope
- [`PRICING_PHILOSOPHY.md`](docs/PRICING_PHILOSOPHY.md) — why stability costs money
- [`FAQ.md`](docs/FAQ.md) — common questions and expectations

If behavior and documentation ever disagree, the documentation is considered authoritative.

---

## Philosophy

This project refuses to become:

* Buggy
* Unreliable
* Frustrating
* Confusing
* Overwhelming

Vehicles are serious systems.

The software that configures them should behave accordingly.

---

## Status

This project is under active development.

- The **Development channel** is public and evolving
- Development builds may change behavior and interfaces
- **Stable releases** are versioned, licensed, and conservative

If you are evaluating the system or contributing, start with Development.

If you intend to rely on it in a vehicle, use a Stable release and review the Stability Promise first.

---

## Getting Started

Start with [`INSTALLATION.md`](docs/INSTALLATION.md) for first-time setup and safe access to the dashboard.

If you are evaluating the system, start with the Development channel.

If you intend to rely on it in a vehicle, review the Stability Promise before choosing a Stable release.

---

## Contributions

Contributions are welcome in the Development channel.

Design decisions prioritize:

* Safety
* Predictability
* Clear failure modes

---

## Closing

This is not just a dashboard.

It is an attempt to give DIY electric vehicles something they rarely have:

**An interface that explains itself — and lets you change it without fear.**
