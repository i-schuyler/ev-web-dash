# Installation

## Purpose

This document explains how to install and access the EV Web Dashboard on a supported controller.

It focuses on **clarity and safety**, not clever shortcuts.

---

## Supported Environment

This project is designed for:

* ESP32-based controllers
* CAN bus–connected EV systems
* Devices that host their own Wi‑Fi access point and HTTP server

The dashboard runs **on the vehicle controller itself**.

No Internet connection is required at any stage.

---

## What You Need

Before installing, ensure you have:

* An ESP32-based controller supported by your firmware build
* A firmware binary (`.bin`) for either Development or Stable
* A phone, tablet, or computer with a modern web browser

No apps or special drivers are required.

---

## First-Time Setup (New Controller)

1. Flash the base firmware to the controller using your normal ESP32 flashing method.

   * USB flashing tools are acceptable for first install
   * This step is typically done on a workbench

2. Power the controller.

3. The controller will start its Wi‑Fi access point.

4. Connect your device to the controller’s Wi‑Fi network.

5. Open a browser and navigate to:

   ```
   http://192.168.4.1
   ```

6. The dashboard should load automatically.

If the page does not load, see the Troubleshooting section.

---

## Updating Firmware Over Wi‑Fi (OTA)

Once the dashboard is accessible, firmware updates can be performed **entirely over Wi‑Fi**.

### OTA Update Steps

1. Connect to the controller’s Wi‑Fi network.
2. Open the dashboard in a browser.
3. Navigate to the firmware update page.
4. Select the firmware `.bin` file.
5. Start the upload and wait for completion.

During the upload:

* Do not power off the controller
* Do not close the browser tab

If the connection drops or the upload fails:

* The update is treated as cancelled
* The controller continues running the existing firmware

---

## OTA Safety Guarantees

OTA updates follow these rules:

* Firmware is written only to the inactive OTA partition
* The uploaded image is verified before activation
* The boot partition is switched only after successful validation
* A software reboot is required to activate the new firmware

These guarantees apply to both Development and Stable builds.

Behavioral stability guarantees apply **only** to Stable releases.

---

## Accessing the Dashboard

The dashboard is accessed locally via browser.

Typical access flow:

* Power the vehicle or controller
* Connect to its Wi‑Fi network
* Open the dashboard URL

The interface is designed to be usable from:

* Phones
* Tablets
* Laptops

---

## Tuning Mode Access

By default, the dashboard operates in a **read-only** mode suitable for driving and observation.

To modify system parameters:

* The user must explicitly enter **Tuning Mode**
* Tuning Mode is intentionally gated to reduce accidental changes

Refer to the Tuning documentation before changing parameters.

---

## Stable vs Development Builds

* **Development builds** are suitable for evaluation and experimentation
* **Stable builds** should be used for vehicles that must be dependable

Review the Stability Promise before installing a Stable build on a relied-upon vehicle.

---

## Troubleshooting

### Dashboard does not load

* Confirm you are connected to the controller’s Wi‑Fi network
* Confirm the IP address is correct
* Power-cycle the controller and retry

### Firmware upload fails

* Ensure the firmware file matches your controller
* Retry the upload
* If failure persists, continue using the existing firmware

No recovery action is required for a failed OTA upload.

---

## Closing Notes

Installation is intentionally simple.

If the process feels fragile or surprising, that is considered a defect.

The system is designed to be approachable, reversible, and calm.
