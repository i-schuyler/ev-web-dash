# Tuning Model

## Purpose

This document defines how **tuning** works in this system.

It explains:

* What tuning means here
* How parameters are structured
* How risk is communicated
* How safety and clarity are preserved

This document is normative.
If behavior diverges from what is described here, the behavior is considered incorrect.

---

## What “Tuning” Means in This System

Tuning is the intentional modification of system parameters that affect vehicle behavior.

These parameters may influence:

* Torque delivery
* Power limits
* Regeneration behavior
* Thermal limits
* Fault thresholds
* System coordination over CAN

Tuning is **not** automatic.

The system does not attempt to infer intent or optimize on the user’s behalf.

All changes are explicit.

---

## Design Principles

The tuning model is built around the following principles:

* **Explicitness** — no hidden behavior changes
* **Legibility** — parameters explain themselves
* **Boundedness** — values have declared limits
* **Reversibility** — safe defaults always exist
* **Consent** — tuning requires deliberate entry

If a parameter cannot be explained clearly, it does not belong in the tuning interface.

---

## Modes of Operation

### Read-Only Mode (Default)

By default, the dashboard operates in a read-only mode suitable for:

* Driving
* Monitoring
* Diagnostics

In this mode:

* Live values are visible
* No parameters can be changed

This minimizes accidental modification during vehicle operation.

---

### Tuning Mode

Tuning Mode must be explicitly entered by the user.

Entering Tuning Mode signals intent to:

* View tunable parameters
* Modify configuration values
* Accept responsibility for changes

The UI clearly indicates when Tuning Mode is active.

---

## Parameter Structure

All tunable parameters follow a consistent structure.

Each parameter includes:

* **Key** — stable identifier used in JSON and code
* **Description** — plain-language explanation
* **Units** — physical units, if applicable
* **Default** — known-safe starting value
* **Minimum / Maximum** — enforced bounds
* **Scope** — subsystem affected
* **Change Behavior** — live-change or reboot-required
* **Risk Level** — qualitative risk indicator

If any of these fields are missing, the parameter is incomplete.

---

## JSON Representation

Tuning parameters are stored and exchanged as structured JSON.

This allows:

* Easy inspection
* Version control
* Profile sharing
* Backup and restore

A typical parameter entry includes both metadata and value.

Example (illustrative):

```json
{
  "key": "max_torque_nm",
  "value": 280,
  "units": "Nm",
  "default": 200,
  "min": 0,
  "max": 350,
  "scope": "inverter",
  "change": "reboot",
  "risk": "high",
  "description": "Maximum commanded motor torque"
}
```

The exact schema may evolve, but the fields and intent remain consistent.

---

## Risk Communication

Every tunable parameter carries a **risk classification**.

Risk levels are qualitative and intended to guide attention, not forbid action.

Typical categories:

* **Low** — unlikely to cause damage or unsafe behavior
* **Medium** — may affect drivability or component stress
* **High** — may damage hardware or compromise safety if misused

Risk is communicated visually and textually in the UI.

No parameter is presented without a stated risk level.

---

## Defaults and Recovery

Every parameter has a defined default value.

Defaults are chosen to:

* Be conservative
* Prioritize hardware safety
* Result in a functional vehicle

Users can always:

* Revert individual parameters to defaults
* Restore a full default profile

Defaults are versioned and documented.

---

## Profiles

The system supports tuning profiles.

Profiles allow:

* Saving a set of parameter values
* Restoring known-good configurations
* Comparing changes over time

Profiles are stored as JSON and can be exported and imported.

---

## Versioning and Compatibility

Tuning parameters are versioned.

In Stable releases:

* Parameter keys do not change within a major version
* Parameter meaning does not change silently
* Defaults may evolve only in minor or major versions

If a parameter must be removed or redefined, this requires a major version increment.

---

## What This Model Refuses to Do

The tuning model explicitly refuses to:

* Auto-tune based on opaque algorithms
* Hide parameters while changing them internally
* Apply undocumented compensation behavior
* Modify parameters without user intent

Predictability is prioritized over optimization.

---

## Closing Statement

Tuning is power.

This system treats that power with respect by making it:

* Visible
* Explained
* Bounded
* Reversible

If tuning ever feels mysterious or surprising, the model has failed.
