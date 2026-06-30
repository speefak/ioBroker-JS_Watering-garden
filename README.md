```markdown
# HH-GA-Watering Script

**ioBroker JavaScript Script** for controlling a **Haozee 2-Zone Smart Irrigation Valve** using a Zigbee button.

---

## Features

- **Single Press** → Start Zone 1 (Pond)
- **Double Press** → Start Zone 2 (Flower)
- **Long Press** → Close all valves
- Automatic detection of the device's built-in 10-minute timer
- Safety shutdown after 10:30 minutes (fallback)
- Clean log output with prefix
- Suppression of duplicate logs during manual actions

---

## Device

- **Model:** Haozee Smart Irrigation Computer 2 Outputs
- **Zigbee ID Example:** `c02cedfffe72acf5`
- **Important Objects:**
  - `state_l1` → Zone 1 (Pond)
  - `state_l2` → Zone 2 (Flower)

---

## Installation

1. In ioBroker go to **Scripts** and create a new JavaScript script
2. Paste the full code from `watering.js`
3. **Important:** Adjust the Object IDs to match your device
4. Save and enable the script

---

## Configuration

You can adjust the following values at the top of the script:

```javascript

const buttonSingle = 'zigbee.0.a4c138068ef8ffff.single';  // Button action
const buttonDouble = 'zigbee.0.a4c138068ef8ffff.double';  // Button action
const buttonLong   = 'zigbee.0.a4c138068ef8ffff.long';    // Button action

const valvePond    = 'zigbee.0.c02cedfffe72acf5.state_l1';  // Valve #1
const valveFlower  = 'zigbee.0.c02cedfffe72acf5.state_l2';  // Valve #2

const wateringTimeSeconds = 600;   // Device built-in timer (10 minutes)
const safetyDelaySeconds  = 630;   // Safety timer (10:30 minutes)
```

---

## Log Examples

```log
HH-GA-Watering | Script started | Safety timer: 630s (10:30)
HH-GA-Watering | 🔘 Starting Pond watering (600s) - valve → OPEN
HH-GA-Watering | Pond valve closed (automatic by device after 600s)
HH-GA-Watering | 🔴 Long Press → Close all valves (Pond + Flower)
```

---

## File Structure

```
/
├── watering.js          ← Main script
├── README.md            ← This file
```

---

## Important Notes

- This script does **not** use Manual Mode (not required for this device)
- The built-in 10-minute timer of the Haozee valve is detected and logged
- The safety shutdown acts as a fallback if the valve doesn't close automatically
- Long Press produces only one combined log message

---

## Changelog

- **v1.0** (2026-06-30)
  - Improved log formatting (fewer lines, cleaner output)
  - Long Press now shows only one log entry
  - Better suppression of duplicate messages

- **v1.1** – Initial stable version

--------------------------------------------------------------------------------------------------------------

This script was created and published free of charge for the open source community.
If you find it useful and would like to support future development, consider making a small donation:

    Bitcoin (BTC): 33AXe8Z8XBuGKx9eHHmGnvbawrNYjSgDcM

    Ethereum (ETH): 0xa61d178EA84C2200A8617b51B4bCf98F87ff59Ff

    Solana (SOL): BDf5EgsN8fRUicYzeM8cuaNhL7zdty2qsEj2mC2jA4Fm

    Ripple (XRP): rLHzPsX6oXkzU2qL12kHCH8G8cnZv1rBJh

    Cardano (ADA): addr1q8anur2wvvc6pv3cpp30vv05makyra8huh0lk0yhdk6hcnlrzr27g03klu862usxqsru794d03gzkk8n86ta34n85z0svn5ams   

    USTether (USDT): 0xa61d178EA84C2200A8617b51B4bCf98F87ff59Ff


Thank you for your support! 🙏

