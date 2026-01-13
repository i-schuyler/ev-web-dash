# Release Channels

## Purpose

This document explains how releases are organized, what each release channel is for, and how to choose the right one for your use case.

It is intentionally practical and mechanical.

If you want values and intent, read the **Stability Promise**.
If you want access rules, read **Licensing & Access**.

---

## Overview

This project maintains **two primary release channels**:

* **Development (Open)**
* **Stable (Licensed)**

Both are built from the same codebase.
They differ in guarantees, testing depth, and intended use.

---

## Development (Open) Channel

### What It Is

The Development channel is the active working edge of the project.

It is:

* Public
* Open-source
* Continuously evolving

### What to Expect

In the Development channel:

* Features may appear, change, or be removed
* Tuning parameters may be added or renamed
* UI layouts and flows may evolve
* Documentation may lag behind behavior

OTA safety mechanisms still apply, but **behavioral stability is not guaranteed**.

### Intended Use

Use the Development channel if:

* You are actively developing or contributing
* You are experimenting or learning
* You are building a custom or non-critical vehicle
* You are comfortable debugging and recovering systems

### What It Is Not

The Development channel is not intended for:

* Daily-driver vehicles
* Shared or customer vehicles
* Situations where unexpected behavior is unacceptable

---

## Stable (Licensed) Channel

### What It Is

The Stable channel consists of **explicitly versioned releases** that adhere to the Stability Promise.

It is:

* Frozen except for bug fixes
* Tested against defined expectations
* Documented to match actual behavior

### What to Expect

In the Stable channel:

* Public APIs remain consistent within a major version
* Tuning parameter meaning does not change silently
* Defaults are conservative and safe
* Upgrade behavior is predictable

OTA updates follow strict validation and rollback rules.

### Intended Use

Use the Stable channel if:

* Your vehicle must start reliably
* You depend on the system day-to-day
* You are delivering a vehicle to someone else
* You value predictability over early access

### Access

Stable releases require a paid license.

The license grants access to the Stable builds themselves — not special features.

---

## Versioning

Releases follow semantic versioning:

* **Major** (`X.0.0`): breaking changes
* **Minor** (`X.Y.0`): new features, no breaking changes
* **Patch** (`X.Y.Z`): bug fixes only

Only Stable releases make compatibility guarantees.

---

## Moving Between Channels

It is expected that users may:

* Start on Development to evaluate the system
* Move to Stable once a build is finalized

Moving from Stable back to Development is always possible, but may require retuning or adjustment.

There is no lock-in.

---

## Summary

* **Development** favors speed, learning, and experimentation
* **Stable** favors restraint, clarity, and dependability

Choose the channel that matches the level of responsibility your vehicle requires.

When in doubt:

> If unexpected behavior would stress you out — choose Stable.
