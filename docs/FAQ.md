# FAQ

## Can this brick my vehicle?

Stable releases are explicitly designed to **fail safely**.

* Firmware updates write only to the inactive OTA partition
* Uploaded firmware is verified before activation
* Failed or interrupted uploads are treated as cancelled

If an update does not complete successfully, the system continues running the existing firmware.

Development builds may change behavior and should not be relied on for safety-critical use.

---

## Why isn’t this completely free?

The Development channel *is* completely free.

Stable releases cost money because they require:

* Additional testing
* Documentation discipline
* Upgrade path guarantees
* Saying no to unstable features

You are not paying for access to ideas.
You are paying for predictability.

---

## What happens if I stop paying?

Nothing stops working.

Once installed, the system runs locally on your vehicle.

If you stop purchasing Stable releases:

* You keep the versions you already have
* You can continue using Development builds
* You do not lose access to your vehicle or data

There is no subscription lock-in.

---

## Why not just use a mobile app?

Apps:

* Require ongoing maintenance
* Depend on OS updates
* Often require Internet access

This project uses the browser because:

* Browsers are universal
* They work offline
* They age better than apps

If your device has a browser, it can talk to the vehicle.

---

## Is this tied to specific hardware?

The platform is designed around **ESP32-based controllers** with CAN connectivity.

Specific hardware support depends on the firmware configuration.

The architecture is intentionally modular so it can be adapted to different EV systems.

---

## Can I customize or extend it?

Yes.

The Development channel is open-source and intended to be modified.

If you are building a custom system or integrating with other hardware, Development builds are the right place to start.

---

## Why not just expose everything at once?

Because overwhelm is a failure mode.

The UI is intentionally structured:

* Read-only driving views by default
* Explicit entry into Tuning Mode
* Clear labeling of risk

This reduces mistakes and makes intent explicit.

---

## Is this suitable for customer vehicles?

Yes — **with Stable releases**.

Shops and builders delivering vehicles to others should always use Stable builds to ensure predictable behavior and documented tuning.

---

## Where do I start?

* If you want to explore: use the Development channel
* If you want to rely on it: review the Stability Promise and choose a Stable release

The README links to all relevant documentation.
