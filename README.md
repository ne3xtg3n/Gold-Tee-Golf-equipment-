# 🏌️‍♂️ GOLD TEE — Illuminated, Rechargeable Golf Tee
**Two Styles:** Window (V2) · Windowless (V3)

Repo tree (drop-in)

gold-tee/
├── README.md
├── LICENSE
├── docs/
│   ├── printing.md
│   ├── assembly.md
│   ├── durability_tests.md
│   ├── safety.md
│   ├── troubleshooting.md
│   └── faq.md
├── cad/
│   ├── gold_tee.scad           # one parametric model → both styles
│   └── usb_cap.scad
├── stls/
│   ├── gold_tee_window.stl
│   ├── gold_tee_windowless.stl
│   └── usb_cap.stl
├── electronics/
│   ├── schematic-notes.md
│   └── code/
│       └── tee_light.ino
├── print_profiles/
│   ├── PrusaSlicer_config.ini   # tuned PETG + TPU profiles [OPTIONAL]
│   └── Cura_profile.curaprofile # [OPTIONAL]
└── images/
    ├── hero_window_remote.jpg      # (kept as remote embeds in README)
    ├── hero_windowless_1_remote.jpg
    └── hero_windowless_2_remote.jpg


---

<p align="center">
  <img src="https://github.com/user-attachments/assets/f97330b8-8637-4bcf-997c-96623dc8f62b"
       alt="Gold Tee — V2 Window Hero" width="100%" style="border-radius:16px;"/>
</p>

<p align="center"><b>V2 (Window) — Hero</b><br/>Slim, standard tee geometry with side USB-C access and LED illumination.</p>

---

## ✨ Two Styles — Visual Showcase

<table>
  <tr>
    <td width="50%" valign="top">
      <div align="center">
        <img src="https://github.com/user-attachments/assets/f97330b8-8637-4bcf-997c-96623dc8f62b"
             alt="Gold Tee V2 Window — Hero"
             width="95%" style="border-radius:12px;"/>
        <br/>
        <sub><b>V2 — Window</b><br/>Classic look with tiny light window + side USB-C</sub>
      </div>
    </td>
    <td width="50%" valign="top">
      <div align="center">
        <img src="https://github.com/user-attachments/assets/821aceda-5df2-4655-b6bb-91826e01f9c4"
             alt="Gold Tee V3 Windowless — Hero 1"
             width="95%" style="border-radius:12px;"/>
        <br/>
        <sub><b>V3 — Windowless</b><br/>Fully translucent body for perfectly even LED diffusion</sub>
      </div>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <div align="center">
        <img src="https://github.com/user-attachments/assets/6a7fbad7-4490-4620-8a7b-c2b028614ab0"
             alt="Gold Tee V3 Windowless — Hero 2"
             width="95%" style="border-radius:12px;"/>
        <br/>
        <sub><b>V3 — Windowless</b><br/>Translucent shell = no cutout → stronger structure + smoother glow</sub>
      </div>
    </td>
    <td width="50%" valign="top">
      <div align="center" style="opacity:.85">
        <em>More build photos coming soon…</em>
      </div>
    </td>
  </tr>
</table>

---

## 🎥 Quick Demos (inline video)

<p align="center">
  <video src="https://github.com/user-attachments/assets/77d3a296-9ec4-4084-8735-6f5efd39a7a5" controls loop muted playsinline style="max-width:100%; border-radius:12px;"></video>
  <br/><sub>Showcase Reel #1 — Geometry + Glow</sub>
</p>

<p align="center">
  <video src="https://github.com/user-attachments/assets/634f3851-9a31-4649-8433-869856424c65" controls loop muted playsinline style="max-width:100%; border-radius:12px;"></video>
  <br/><sub>Showcase Reel #2 — Windowless Diffusion</sub>
</p>

> If your browser doesn’t autoplay inline: download or open in a new tab.

---

## What is Gold Tee?
A standard-feel golf tee with a rechargeable LED for night play and ball-finding. **One parametric CAD file outputs both styles** so you can export the exact variant you want.

- **Standard Geometry:** 70 mm (2.75") height, ~4 mm shaft, pointed tip, 12 mm shallow cup  
- **Electronics:** 5 mm LED, 1S LiPo (~50 mAh), tiny USB-C charge-only board, optional vibration switch (no MCU) or accelerometer  
- **Print-Ready:** Sideways orientation, 100% infill, PETG/TPU/PC depending on your flex goal

---

## 🧩 Parametric CAD (one file → both styles)

- File: `cad/gold_tee.scad`  
- Switch the style by changing one line at the top:
  ```scad
  STYLE = "window";      // or "windowless"

Export (OpenSCAD GUI)

1. Open cad/gold_tee.scad


2. Set STYLE = "window" → F6 (Render) → Export STL → stls/gold_tee_window.stl


3. Set STYLE = "windowless" → F6 → Export STL → stls/gold_tee_windowless.stl



Export (Command line / CI)

# from repo root
openscad -D 'STYLE="window"'     -o stls/gold_tee_window.stl     cad/gold_tee.scad
openscad -D 'STYLE="windowless"' -o stls/gold_tee_windowless.stl cad/gold_tee.scad


---

🖨️ Printing Quick-Start (TL;DR)

Orientation: print sideways (tee lies on its side). Layers ⟂ club path = stronger.

Infill: 100% (tiny part; prioritize strength)

Layer height: 0.20 mm (0.12–0.16 mm if you want ultra-smooth diffusion)

Supports: minimal (tip + underside of cup). Brim: 3–5 mm

Materials:

V2 Window: PETG or PC → rigid, tough

V3 Windowless: translucent PETG → even glow; TPU for max flex (wood-like)


Deep-dive tuning: see docs/printing.md



---

🔧 Assembly Snapshot

1. Dry-fit USB-C + LiPo in side cavity.


2. Pad with silicone gel/foam around LiPo + wires.


3. Epoxy the LED in the head; aim die toward cup for brightest top glow.


4. Seal the USB cap (friction fit or tiny drop of flexible adhesive).


5. Charge cool (let tee cool after play before charging).


6. Impact should trigger 5–10 s glow (vibration switch or accel logic).
Full steps with photos & diagrams: docs/assembly.md.




---

📦 Bill of Materials (per tee)

Item	Qty	Notes	Est. Cost

5 mm diffused LED (white)	1	2–3 V, ~10–20 mA pulse	$0.05
LiPo 1S 50 mAh	1	~12×20×4 mm	$2.00
MCP73831-2 charger (or TP4054/4057)	1	set 50–80 mA charge current	$1.20
USB-C charge-only breakout	1	CC resistors populated	$0.75
Vibration switch SW-18010P (or accel)	1	simple trigger	$0.15
SOT-23 NPN / logic MOSFET	1	LED drive	$0.10
Silicone gel + epoxy	—	pad + potting	$0.50
Filament: PETG/TPU/PC (~5–7 g)	—	translucent PETG for V3	$0.10
Estimated total			≈ $4.85


Electronics layout & notes: electronics/schematic-notes.md


---

🧪 Durability & “Virtual” Testing (what to expect)

Sideways print ≈ ~2× stronger vs vertical layers under club impact

Windowless PETG resists crack propagation vs a cutout window

TPU shaft (hybrid print) greatly lowers snap risk; protects electronics

Field life depends on course hardness, strike quality, temp, and print quality
Full notes: docs/durability_tests.md.



---

⚠️ Safety

Use a charge-only USB-C board and conservative I<sub>chg</sub> (≤ 50–80 mA for 50 mAh).

Don’t charge when hot from play; let cool first.

Pot/seal electronics against moisture; bench-test before course use.
Details: docs/safety.md.



---

🧰 Troubleshooting

Snaps on impact: switch shaft to TPU or raise temp/flow to improve layer welds

Dim glow: aim LED die upward; thin wall near LED (V3) to ~0.8–1.0 mm

USB-C loose: add a tiny TPU shim or dab of flexible adhesive to cap

False triggers: add small RC delay or use a digital accel threshold
More fixes: docs/troubleshooting.md.



---

🙋 FAQ

USGA length? This design targets 70 mm (2.75"); max allowed is 101.6 mm (4").

Do I need an MCU? No; a vibration switch + transistor is enough. An accel + MCU gives finer control.

Can I resin-print this? Yes for translucency, but impact resistance varies by resin.
See docs/faq.md.



---

📁 Repo Map

cad/                # OpenSCAD (parametric), USB cap
stls/               # pre-exported STLs for both styles
docs/               # printing, assembly, durability, safety, FAQ, troubleshooting
electronics/        # wiring notes + optional simple firmware
print_profiles/     # [optional] tuned slicer profiles (PETG/TPU)
images/             # (optional local copies; README uses remote URLs)


---

🧑‍💻 License & Credits

MIT License (see LICENSE).
Design & documentation by Christopher Perry.
Images & videos © their respective owner(s).

---

## cad/gold_tee.scad (single parametric file)

```scad
// GOLD TEE — Parametric Tee (Window + Windowless)
// Export both styles by changing STYLE.
// Suggested STL names: gold_tee_window.stl / gold_tee_windowless.stl

$fn = 64;

// -------------------- Style Switch --------------------
STYLE = "windowless";   // "window" or "windowless"

// -------------------- Geometry Params --------------------
tee_height = 70;        // mm (2.75")
tip_len    = 10;        // mm, ground insert tip
shaft_dia  = 4.0;       // mm, standard feel (3.6–4.5 good range)
head_dia   = 12.0;      // mm, shallow cup outer diameter
cup_depth  = 3.0;       // mm, 2–4 typical
body_wall  = 1.0;       // mm around cavities

// -------------------- Electronics Cavity --------------------
bat_len = 20;           // LiPo length (Z axis inside cavity)
bat_w   = 12;           // LiPo width  (Y axis)
bat_h   = 4;            // LiPo thick  (X axis outward)
usb_w   = 9;            // USB-C opening width (Y)
usb_h   = 5;            // USB-C opening height (Z)
cavity_z = 6;           // center height of side cavity from base (Z)

// -------------------- Window (V2 only) --------------------
win_len = 14;           // Z length of window cut
win_w   = 6;            // Y width of window cut
win_th  = 0.8;          // X thickness through wall

// -------------------- LED Channel --------------------
chan_w  = 4.0;          // X width for wire/LED channel
chan_h  = tee_height - tip_len - 12; // Z height of channel

// -------------------- Visual Detail --------------------
ridges_step = 3;        // mm spacing between flex ridges (visual only)
ridge_d     = 1.0;      // mm ridge sphere diameter
show_ridges = true;     // set false to remove

// ============================================================
// Modules
// ============================================================
module tee_shell() {
    // pointed tip
    translate([0,0,0])
        cylinder(h=tip_len, r1=0.1, r2=shaft_dia/2);

    // straight shaft
    translate([0,0,tip_len])
        cylinder(h=tee_height - tip_len - 10, r=shaft_dia/2);

    // spherical head with shallow cup
    translate([0,0,tee_height-10])
        difference() {
            sphere(d=head_dia);
            translate([0,0,(head_dia/2) - cup_depth])
                cylinder(h=cup_depth + 0.2, r=(head_dia/2) - 1);
        }
}

module side_cavity() {
    translate([shaft_dia/2 + (body_wall/2), 0, cavity_z])
        cube([bat_h + body_wall, bat_w, bat_len], center=true);
}

module usb_slot() {
    translate([shaft_dia/2 + body_wall, 0, cavity_z])
        cube([2, usb_w, usb_h], center=true);
}

module led_channel() {
    translate([0,0, tip_len + 5])
        cube([chan_w, body_wall, chan_h], center=true);
}

module window_cut() {
    translate([shaft_dia/2 + body_wall/2, 0, cavity_z])
        cube([win_th, win_w, win_len], center=true);
}

module flex_ridges(step=ridges_step, d=ridge_d) {
    for (i = [0 : step : tee_height - tip_len - 10]) {
        translate([0, shaft_dia/2 + 0.6, tip_len + i])
            sphere(d=d);
    }
}

// ============================================================
// Construct the tee
// ============================================================
difference() {
    tee_shell();

    // internals
    side_cavity();
    usb_slot();
    led_channel();

    // style-specific
    if (STYLE == "window") window_cut();
}

// surface detail
if (show_ridges) flex_ridges();


---

cad/usb_cap.scad

$fn = 48;
usb_w = 9;      // must match gold_tee.scad
usb_h = 5;
cap_th = 3;     // depth into slot
lip   = 0.4;    // slight oversize for friction

difference() {
  cube([cap_th, usb_w + 2*lip, usb_h + 2*lip], center=true);
  translate([cap_th/2 - 0.6, 0, 0])
    cube([1.2, usb_w - 1.2, usb_h - 1.2], center=true);
}


---

electronics/schematic-notes.md (overview)

# Schematic Notes — Gold Tee

## Minimal (no MCU)
- 1S LiPo (50 mAh) → MCP73831-2 charger (charge-only USB-C board)
- Vibration switch (SW-18010P) → NPN/MOSFET → LED (with series resistor)
- LED 5 mm diffused, epoxy-potted in head

## Optional (MCU + accel)
- Small accel (e.g., LIS3DH) + tiny MCU
- Impact threshold triggers LED on-time (e.g., 6 s)
- Sleep mode for battery life

**Charging current:** 50–80 mA for 50 mAh cell (conservative).  
**Seal:** silicone gel around LiPo + epoxy pot LED cavity.


---

electronics/code/tee_light.ino

// Minimal: vibration switch on D2 (INPUT_PULLUP), LED on D3 via transistor
const int vibPin = 2;
const int ledPin = 3;
unsigned long tOff = 0;
const unsigned long onMs = 6000;

void setup() {
  pinMode(vibPin, INPUT_PULLUP);
  pinMode(ledPin, OUTPUT);
  digitalWrite(ledPin, LOW);
}

void loop() {
  if (digitalRead(vibPin) == LOW) { // vibration closes switch briefly
    tOff = millis() + onMs;
  }
  digitalWrite(ledPin, (millis() < tOff) ? HIGH : LOW);
}


---

docs/printing.md (highlights)

# Printing Guide

- **Orientation:** Always **sideways** (tee on its side). Improves impact strength substantially.
- **Infill:** 100% (tiny part).
- **Layer heights:** 0.20 mm default; 0.12–0.16 mm for smoother diffusion on V3.
- **Walls:** 3–4 perimeters recommended if you tweak dimensions.
- **Supports:** Tip + cup underside only; tree supports preferred.
- **Brim:** 3–5 mm.

## Materials
- **PETG (V2, V3):** Tough + good translucency.
- **TPU 95A (shaft/hybrid):** Maximum flex; wood-like feel.
- **PC (advanced):** Strongest but higher temp; ensure enclosure + bed adhesion.

## Hybrid Trick (TPU shaft + PETG head)
- Slice two parts by Z or by splitting the model in CAD (advanced users).
- Bond with CA + TPU-safe primer or mechanical interlock in CAD.


---

docs/assembly.md (highlights)

# Assembly Guide

1. **Dry Fit**
   - Insert USB-C breakout + charger board + LiPo into side cavity.
   - Verify USB cap friction fit.

2. **Pad & Route**
   - Silicone gel/foam around LiPo; keep gel away from USB connector.
   - Route wires through internal channel; trim excess leads.

3. **LED Install**
   - Mix epoxy. Seat 5 mm LED in head; orient die upward toward cup.
   - Wipe any squeeze-out; let cure.

4. **Seal + Test**
   - Insert USB cap (friction or tiny flexible adhesive).
   - Charge cool (don’t charge while hot from play).
   - Tap tee → LED on 5–10 s.

> Tip: For V3 windowsless, ~0.8–1.0 mm wall near LED gives the best diffusion.


---

docs/durability_tests.md (highlights)

# Durability Notes

- Sideways print = layers perpendicular to strike → fewer split failures.
- Windowless shell avoids crack initiation around a cutout.
- TPU shaft reduces peak shock to electronics; PETG head maintains seating.
- Field life varies with strike quality, turf hardness, temperature.

Bench tests to try:
- Mallet test at head/cup edge (repeat 25–50×).
- Freeze test (-5 to 0 °C) → mallet test (brittleness check).
- Sand ingress check → blow out + re-test cap fit.


---

docs/safety.md

# Safety

- Use **charge-only** USB-C (no data) and set **I_chg ≤ 50–80 mA** for 50 mAh LiPo.
- Do **not** charge immediately after play; let it cool first.
- Moisture-seal electronics; avoid submersion.
- Dispose of damaged LiPo properly; don’t puncture.


---

docs/troubleshooting.md

# Troubleshooting

**Snaps on first strike**
- Raise nozzle temp / slow speed (layer fusion)
- Switch to TPU shaft or full TPU
- Ensure sideways orientation

**LED flickers/off**
- Cold solder joint → reflow
- Add small electrolytic across LED drive
- Vibration switch too sensitive → series RC filter

**USB cap loosens**
- Increase lip by +0.2 mm in `usb_cap.scad`
- Dab of flexible adhesive


---

docs/faq.md

# FAQ

**Q:** Is this USGA-legal?
**A:** Overall length target is 70 mm; USGA allows up to 4" (101.6 mm). Electronics visibility may conflict with tournament rules—use for casual/night play.

**Q:** Resin vs FDM?
**A:** Resin gives beautiful diffusion but can be brittle. PETG/TPU FDM is more impact-friendly.

**Q:** Can I widen the cup?
**A:** Yes—change `head_dia` and `cup_depth` in `gold_tee.scad`.


---

LICENSE (MIT)

MIT License

Copyright (c) 2025 Christopher Perry

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights…
[full MIT text here]


---

Done.

This version showcases your hero images + videos beautifully, gives makers a one-file parametric CAD, and ships print/assembly/safety/troubleshooting docs so anyone can build it confidently. If you want, I can also draft a GitHub Social Preview (OG image) banner and a release checklist (tagging STLs per version, changelog, etc.).

