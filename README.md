# HH-GA-Watering Script

**ioBroker JavaScript Script** for controlling a **Haozee 2-Zone Smart Irrigation Valve** using a Zigbee button.

---

## Features

- **Single Press** → Start Zone 1 (Pond)
- **Double Press** → Start Zone 2 (Flower)
- **Long Press** → Close all valves
- Automatic detection of the device's built-in 10-minute timer
- Safety shutdown after 10:30 minutes (fallback)
- Clean and clear log output with prefix
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
const wateringTimeSeconds = 600;   // Device built-in timer (10 minutes)
const safetyDelaySeconds  = 630;   // Safety timer (10:30 minutes)



