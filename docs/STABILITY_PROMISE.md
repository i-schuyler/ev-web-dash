# Stability Promise

## Purpose

This document defines the **Stability Promise** for this project.

It exists to make one thing explicit:

> **Stable releases are designed to be calm, predictable, and safe to use on vehicles you depend on.**

This is not a marketing document. It is a contract of intent between the project and its users.

---

## Release Channels

This project intentionally maintains **two parallel release channels**:

### 1. Development (Open) Channel

The Development channel is:

* Public
* Open-source
* Actively evolving

It is where:

* New features are introduced
* New tuning parameters are added
* Experimental UI flows are tested
* Architectural changes occur

Characteristics:

* APIs may change
* Parameter names or behavior may shift
* Documentation may lag behind implementation

**The Development channel is not intended for vehicles that must be reliable day-to-day.**

Its purpose is learning, experimentation, and collaboration.

---

### 2. Stable (Paid) Channel

The Stable channel is:

* Versioned
* Frozen except for bug fixes
* Explicitly tested
* Documented to match actual behavior

Stable releases are intended for:

* Vehicles that must start reliably
* Builds with significant financial or safety investment
* Users who want confidence over novelty

Access to Stable releases may require a paid license.

The license does **not** buy features.
It buys **predictability and restraint**.

---

## What “Stable” Means Here

A release labeled **Stable** makes the following commitments:

### Behavioral Stability

* Public APIs do not change within a major version
* Tuning parameters do not change meaning without a major version bump
* Default values are conservative and safe

### OTA Safety

* Firmware uploads write only to the inactive OTA partition
* Uploaded firmware is verified before activation
* Failed or interrupted uploads do not alter the running system
* The boot partition is switched only after successful validation

### Documentation Accuracy

* All exposed tuning parameters are documented
* Documentation reflects actual runtime behavior
* Known limitations are stated plainly

### Upgrade Predictability

* Minor version updates do not require retuning
* Patch releases do not change behavior
* Any breaking change requires a major version increment

---

## Tuning Mode Guarantees

Stable releases that expose **Tuning Mode** follow additional rules:

* Every tunable parameter includes:

  * A plain-language description
  * Units and valid ranges
  * A defined default value
  * Notes on whether a reboot is required

* Parameters are categorized to reduce cognitive load

* Unsafe or experimental parameters are clearly labeled

* All parameters and their values can be saved to custom profiles.

* Tuning Mode requires explicit user intent to enter

The system favors **clarity over cleverness**.

---

## What Stable Releases Refuse to Become

Stable releases explicitly refuse to become:

* Buggy
* Unreliable
* Frustrating to use
* Confusing
* Overwhelming

This refusal guides design decisions, feature inclusion, and release timing.

If a feature threatens stability, it remains in the Development channel until it does not.

---

## What Stability Does *Not* Mean

Stability does **not** mean:

* No innovation
* No evolution
* No experimentation

It means:

> Innovation happens **first** in Development, and **only later** becomes Stable—if it earns that trust.

---

## Versioning Policy

* **Major versions** may introduce breaking changes
* **Minor versions** add features without breaking existing behavior
* **Patch versions** fix bugs only

Stable users are never surprised by silent behavior changes.

---

## Closing Statement

This project treats vehicles as serious systems.

A Stable release is a promise to behave conservatively, explain itself clearly, and fail safely.

If that promise cannot be upheld, the release does not ship as Stable.
