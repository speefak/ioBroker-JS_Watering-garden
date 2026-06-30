# HH-GA-Watering Script

ioBroker JavaScript script to control a **Haozee 2-Zone Smart Irrigation Valve** using a Zigbee button.

---

## Features

- **Single Press** → Start Zone 1 (Pond)
- **Double Press** → Start Zone 2 (Flower)
- **Long Press** → Emergency close all valves
- Automatic safety shutdown after **5:30 minutes**
- Proper command sending (`ack: false`)

---

## Important Note

> **You must adjust the Object IDs** in the script to match your device!

The IDs used in this script are specific to the author's setup (`c02cedfffe72acf5`).  
Replace them with your own device IDs from the Zigbee adapter.

---

## Device

- **Model:** Haozee Smart Irrigation Computer 2 Outputs
- **Protocol:** Zigbee (via zigbee2mqtt / Zigbee Adapter)

---

## Installation

1. In ioBroker go to **Scripts** and create a new JavaScript script
2. Paste the entire content of `watering.js`
3. **Adjust the Object IDs** at the top of the script
4. Save and enable the script

---

## Files

- `watering.js` → Main script

---

## Configuration

```javascript
// ==================== CONFIGURATION ====================

const buttonSingle = 'zigbee.0.a4c138068ef8ffff.single';
const buttonDouble = 'zigbee.0.a4c138068ef8ffff.double';
const buttonLong   = 'zigbee.0.a4c138068ef8ffff.long';

const valvePond    = 'zigbee.0.c02cedfffe72acf5.state_l1';   // ← Change this
const valveFlower  = 'zigbee.0.c02cedfffe72acf5.state_l2';   // ← Change this
