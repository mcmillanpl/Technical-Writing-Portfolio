# Release Notes: Integrated Power & Data Suite

**Release Date**: December 21, 2025  
**Version**: v2.4.0 (The "Connectivity" Update)

## Overview
The v2.4.0 release focuses on bridging the gap between field hardware and cloud-based monitoring. Key updates include a new authentication scope for the User Access API and expanded telemetry logic for the Sample Product firmware.

---

## Software & API Updates

### User Access API (v1.2)
* **NEW**: Added `read:telemetry` scope to allow third-party monitoring tools to pull real-time battery health data.
* **UPDATE**: Enhanced error messaging for the `license_type` parameter to provide prescriptive resolution steps for expired tokens.
* **FIX**: Resolved an issue where Webhook subscriptions would intermittently timeout during high-concurrency SOQL queries.

### MadCap Flare Workflow
* **NEW**: Migrated all project bindings from HTTPS to SSH to comply with updated enterprise security protocols.
* **UPDATE**: Updated the [Git Command Reference](./reference/git-commands.md) to include "Stash" and "Pop" workflows for multi-author collaboration.

---

## Hardware & Technical Reference

### SENS PowerCab2 System (Firmware v4.11)
* **NEW**: Added **Modbus TCP** support for remote monitoring of DC load anomalies.
* **UPDATE**: Revised the [PowerCab2 Technical Manual](../reference/101343_PowerCab2_Manual.pdf) (Section 4.2) to include updated torque specifications for high-vibration environments.
* **COMPLIANCE**: Validated all new alarm logic against **NFPA 70 (2025 Edition)** safety signaling standards.

### SuperTorque 8ZR
* **NEW**: Released the [Quick-Start Deployment Guide](../reference/101346_8R_Quick-Start.pdf) in Spanish and French to support international field operations.

---

## Maintenance & Bug Fixes
* **Documentation**: Fixed broken cross-references in the C# Advanced Operations tutorial.
* **Security**: Patched a vulnerability in the Setup Utility's USB driver communication bridge.

---

## Contributor Credits
Documentation managed and authored by **Pamela McMillan** using a "Docs-as-Code" methodology via Markdown and MadCap Flare.