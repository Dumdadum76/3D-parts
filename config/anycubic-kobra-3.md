# Anycubic Kobra 3 Printer Configuration

Reference configuration and settings for the Anycubic Kobra 3 printer.

---

## Printer Specifications

### Hardware
- **Build Volume**: 250 x 250 x 260 mm
- **Nozzle Diameter**: 0.4mm (stock)
- **Max Nozzle Temperature**: 300°C
- **Max Bed Temperature**: 100°C
- **Heated Bed**: Yes (PEI-coated spring steel sheet)
- **Auto Bed Leveling**: Yes (Anycubic LeviQ 2.0)
- **Z-Offset Adjustment**: Automatic with manual fine-tuning available
- **Filament Sensor**: Yes
- **Resume Print**: Yes (power loss recovery)

### Motion System
- **Max Print Speed**: 500 mm/s (manufacturer claim)
- **Recommended Speed**: 60-150 mm/s for quality prints
- **Max Acceleration**: High (exact specs vary by firmware)
- **Extruder**: Direct drive
- **Leveling**: Automatic 49-point mesh

### Electronics
- **Controller Board**: 32-bit
- **Display**: Color touchscreen
- **Connectivity**: USB, SD card, WiFi (model dependent)
- **Firmware**: Marlin-based (Anycubic custom)

---

## Recommended Slicer Settings

### PLA Settings

#### Quality Print (0.15mm layers)
```
Layer Height: 0.15mm
First Layer Height: 0.2mm
Line Width: 0.4mm

Perimeters: 3-4 walls
Top Solid Layers: 5
Bottom Solid Layers: 4
Infill: 20%
Infill Pattern: Gyroid

Print Speed: 60mm/s
Outer Perimeter Speed: 40mm/s
Inner Perimeter Speed: 60mm/s
Infill Speed: 80mm/s
Travel Speed: 150mm/s
First Layer Speed: 20mm/s

Nozzle Temperature: 205°C
First Layer Nozzle Temp: 210°C
Bed Temperature: 60°C
First Layer Bed Temp: 65°C

Cooling:
  - Enable cooling: Yes
  - Fan speed: 100% (after layer 2)
  - First layer fan speed: 0%

Retraction:
  - Distance: 2mm (direct drive)
  - Speed: 40mm/s
  - Z-hop: 0.2mm (optional, helps prevent scars)
```

#### Standard Print (0.2mm layers)
```
Layer Height: 0.2mm
First Layer Height: 0.2mm

Perimeters: 3 walls
Top Solid Layers: 4
Bottom Solid Layers: 4
Infill: 20%

Print Speed: 80mm/s
Outer Perimeter Speed: 50mm/s
First Layer Speed: 20mm/s
Travel Speed: 180mm/s

Nozzle Temperature: 200-205°C
Bed Temperature: 60°C

Cooling: 100% after layer 2
Retraction: 2mm at 40mm/s
```

#### Fast Print (0.28mm layers)
```
Layer Height: 0.28mm
First Layer Height: 0.28mm

Perimeters: 2 walls
Infill: 15%

Print Speed: 120mm/s
Outer Perimeter Speed: 80mm/s
Travel Speed: 200mm/s

Nozzle Temperature: 210°C
Bed Temperature: 60°C

Cooling: 100% after layer 2
Retraction: 2mm at 45mm/s
```

---

### PETG Settings

#### Quality Print
```
Layer Height: 0.2mm
First Layer Height: 0.2mm

Perimeters: 4 walls
Top Solid Layers: 5
Bottom Solid Layers: 5
Infill: 30%
Infill Pattern: Gyroid

Print Speed: 50mm/s
Outer Perimeter Speed: 30mm/s
Infill Speed: 60mm/s
Travel Speed: 150mm/s
First Layer Speed: 15mm/s

Nozzle Temperature: 230-240°C
First Layer Nozzle Temp: 240°C
Bed Temperature: 80°C
First Layer Bed Temp: 85°C

Cooling:
  - Fan speed: 30-50% (after layer 3)
  - First layer fan speed: 0%
  - Note: Too much cooling can cause layer adhesion issues

Retraction:
  - Distance: 2mm
  - Speed: 35mm/s
  - Z-hop: 0.3mm (recommended to avoid blobs)

Additional Settings:
  - Extra perimeter overlap: Slightly increase for better layer adhesion
  - Print thin walls: Enable
```

---

### ABS Settings

**Note**: ABS requires an enclosure for best results. The Kobra 3 doesn't come with one by default.

#### Quality Print
```
Layer Height: 0.2mm
First Layer Height: 0.3mm

Perimeters: 4 walls
Infill: 40%

Print Speed: 60mm/s
First Layer Speed: 15mm/s

Nozzle Temperature: 240-250°C
Bed Temperature: 100°C (or as hot as your bed can go)

Cooling:
  - Fan speed: 0-20% maximum
  - First layer: 0%
  - Keep chamber hot, minimize cooling

Retraction: 2mm at 35mm/s

Important:
  - Use enclosure to prevent warping
  - Brim or raft recommended for bed adhesion
  - Watch for fumes - print in well-ventilated area
  - Consider ABS juice (ABS dissolved in acetone) on bed
```

---

### TPU (Flexible) Settings

```
Layer Height: 0.2mm
First Layer Height: 0.2mm

Perimeters: 3 walls
Infill: 20-30%
Infill Pattern: Grid or Honeycomb

Print Speed: 20-30mm/s (SLOW!)
Outer Perimeter Speed: 15mm/s
Infill Speed: 30mm/s
Travel Speed: 80mm/s
First Layer Speed: 10mm/s

Nozzle Temperature: 220-230°C
Bed Temperature: 40-50°C

Cooling: 30-50%

Retraction:
  - Distance: 1mm (minimal, or disable)
  - Speed: 25mm/s
  - Direct drive helps with flexible filaments

Additional Settings:
  - Enable Linear Advance if available
  - Maximize outline overlap
  - Avoid sharp corners in design
```

---

## Calibration Procedures

### Initial Setup Checklist
- [ ] Assemble printer per manufacturer instructions
- [ ] Run auto bed leveling (LeviQ 2.0)
- [ ] Load filament and perform test extrusion
- [ ] Set Z-offset (first layer height)
- [ ] Run calibration cube test print

### Bed Leveling
1. Heat bed to printing temperature (60°C for PLA)
2. Heat nozzle to printing temperature
3. Navigate to: Menu > Prepare > Auto Level
4. Wait for 49-point probe sequence
5. Save mesh: Menu > Prepare > Store Settings

**Note**: Re-level if you:
- Change nozzle
- Move the printer
- Notice first layer issues
- Every 20-30 prints (preventive maintenance)

### Z-Offset Calibration
1. Start a test print or use built-in calibration
2. Watch first layer closely
3. Adjust Z-offset in real-time:
   - Too high: Filament not sticking, gaps between lines
   - Too low: Nozzle scraping, filament squished too thin
   - Perfect: Slight squish, lines touch but aren't over-compressed
4. Save Z-offset when satisfied

### E-Steps Calibration (Extruder Steps)
```
1. Heat nozzle to printing temp (200°C for PLA)
2. Mark filament 120mm above extruder entry
3. Extrude 100mm: Menu > Prepare > Move Axis > Extruder > 100mm
4. Measure remaining distance to mark
5. Calculate: New E-steps = Old E-steps × (100 / Actual Distance)
6. Update: Menu > Control > Motion > E-steps/mm
7. Save: Menu > Control > Store Settings
```

### Flow Rate Calibration
```
1. Print single-wall calibration cube (available on Thingiverse)
2. Measure wall thickness with calipers
3. Expected: 0.4mm (for 0.4mm nozzle)
4. Calculate: New Flow = Old Flow × (0.4 / Measured Thickness)
5. Adjust in slicer: Print Settings > Advanced > Flow Rate
6. Typical range: 95-105%
```

### Temperature Towers
Print temperature towers to find optimal temperature for each filament:
1. Download temperature tower STL
2. Set up in slicer with temperature changes per height
3. Print and examine each section for:
   - Best layer adhesion
   - Minimal stringing
   - Clean bridges and overhangs
   - Good surface finish

### Retraction Tuning
```
Print retraction test (e.g., retraction tower or stringing test)

Adjust:
- Retraction distance: Start at 2mm for direct drive
- Retraction speed: 35-45mm/s
- Z-hop: 0.2-0.3mm if needed

Goal: Minimize stringing without causing clogs or gaps
```

---

## Maintenance Schedule

### Before Each Print
- [ ] Check bed is clean (IPA wipe if needed)
- [ ] Verify filament loaded and dry
- [ ] Confirm bed mesh loaded
- [ ] Check nozzle isn't clogged

### Weekly (Heavy Use) / Monthly (Light Use)
- [ ] Clean PEI build surface thoroughly
- [ ] Check belt tension
- [ ] Lubricate Z-axis lead screw
- [ ] Check all bolts and screws are tight
- [ ] Clean extruder gears
- [ ] Verify fans are operating correctly

### Monthly
- [ ] Deep clean bed with warm soapy water
- [ ] Check wiring for damage
- [ ] Re-run full bed leveling calibration
- [ ] Clean/replace nozzle if needed
- [ ] Update firmware (check for updates)

### Every 1-2 kg of Filament
- [ ] Replace nozzle
- [ ] Deep clean hotend
- [ ] Check PTFE tube for wear
- [ ] Re-calibrate e-steps and flow rate

---

## Troubleshooting Guide

### First Layer Issues

**Not Sticking**
- Increase bed temperature by 5°C
- Decrease Z-offset (nozzle closer to bed)
- Clean bed with IPA
- Slow down first layer (15-20mm/s)
- Add brim or raft
- Ensure bed is properly leveled

**Nozzle Too Close**
- Increase Z-offset
- Filament appears transparent or nozzle scratches surface
- Adjust in real-time during first layer

**Warping**
- Increase bed temperature
- Add brim or "mouse ears" to corners
- Eliminate drafts
- Use enclosure (especially for ABS/PETG)
- Slow down cooling

### Print Quality Issues

**Stringing/Oozing**
- Increase retraction distance (try 2.5-3mm)
- Increase retraction speed
- Lower nozzle temperature by 5°C
- Enable Z-hop (0.2mm)
- Dry filament

**Layer Adhesion Problems**
- Increase nozzle temperature by 5°C
- Slow down print speed
- Increase fan speed (for PLA)
- Decrease fan speed (for PETG/ABS)
- Dry filament
- Check for partial nozzle clog

**Rough Surfaces**
- Lower print speed (especially outer perimeters)
- Check belt tension
- Ensure frame is square and stable
- Lower layer height for finer detail
- Adjust temperature (might be too high)

**Elephants Foot**
- Enable "Elephant's Foot Compensation" in slicer
- Reduce first layer bed temperature
- Increase Z-offset slightly
- Reduce first layer flow rate to 95%

**Blobs and Zits**
- Enable "Retract on Layer Change"
- Adjust seam position settings
- Reduce nozzle temperature
- Increase retraction
- Enable coasting

---

## Bed Adhesion Methods

### PEI Surface (Stock)
- **Best for**: PLA, PETG
- **Prep**: Clean with IPA before each print
- **Remove**: Wait for bed to cool, part will release easily
- **Lifespan**: Months to years with proper care
- **When to replace**: When surface becomes too scratched or won't clean

### Glue Stick
- **Best for**: PETG (prevents bonding too strongly)
- **Application**: Thin layer on cool bed, heat to spread
- **Cleanup**: Warm water

### Painter's Tape / Blue Tape
- **Best for**: PLA when PEI is damaged
- **Application**: Smooth, overlap edges slightly
- **Replace**: When surface tears or becomes too textured

### Hairspray
- **Best for**: ABS, large PLA prints
- **Application**: Light mist on cool bed
- **Cleanup**: IPA or warm soapy water

### ABS Slurry (ABS in Acetone)
- **Best for**: ABS only
- **Application**: Thin layer on heated bed
- **Warning**: Use in well-ventilated area, flammable
- **Cleanup**: Acetone

---

## Filament Storage & Drying

### Storage
- Keep filament sealed with desiccant
- Store in airtight containers when not in use
- PLA can tolerate more humidity than PETG/Nylon
- Ideal storage: < 20% relative humidity

### Signs Filament Needs Drying
- Popping/crackling sound during printing
- Increased stringing
- Poor layer adhesion
- Brittle prints
- Surface imperfections

### Drying Guide
| Material | Temperature | Time |
|----------|-------------|------|
| PLA      | 45-50°C     | 4-6h |
| PETG     | 60-65°C     | 6-8h |
| ABS      | 60-70°C     | 4-6h |
| Nylon    | 70-80°C     | 12h+ |
| TPU      | 50-60°C     | 4-6h |

Methods:
- Dedicated filament dryer (best)
- Food dehydrator
- Oven (least precise, use oven thermometer)

---

## Recommended Upgrades

### Essential
- **Spare nozzles**: Keep 0.4mm replacements on hand
- **Different nozzle sizes**: 0.2mm (detail), 0.6mm (speed/strength)
- **Filament storage**: Airtight containers with desiccant
- **Digital calipers**: For measuring prints and calibration

### Quality of Life
- **Hardened steel nozzle**: For abrasive filaments (carbon fiber, glow in dark)
- **Build surface alternatives**: Textured PEI, smooth PEI, or spring steel sheets
- **Filament dryer**: For keeping filament dry during storage
- **Camera**: For remote monitoring

### Performance
- **Enclosure**: Essential for ABS, helpful for large prints
- **Better cooling**: Upgraded part cooling fan ducts
- **Linear rails**: For smoother motion (advanced)
- **All-metal hotend**: If not stock (for printing at higher temps)

---

## Useful G-Code Commands

### Manual Control
```gcode
M109 S200       ; Set nozzle temp and wait
M190 S60        ; Set bed temp and wait
M104 S200       ; Set nozzle temp, don't wait
M140 S60        ; Set bed temp, don't wait

G28             ; Home all axes
G29             ; Run auto bed level

M500            ; Save settings to EEPROM
M501            ; Load settings from EEPROM
M502            ; Load factory defaults
M503            ; Display current settings
```

### Filament Change
```gcode
M600            ; Pause for filament change (if supported)
M104 S200       ; Heat nozzle
M109 S200       ; Wait for temperature
G92 E0          ; Reset extruder position
G1 E100 F300    ; Extrude 100mm to purge
```

### Maintenance
```gcode
M18             ; Disable all steppers
M84             ; Same as M18
M106 S255       ; Fan on full
M107            ; Fan off
```

---

## Quick Start for First Print

1. **Level bed**: Menu > Prepare > Auto Level
2. **Set Z-offset**: Start test print, adjust in real-time
3. **Load filament**: Heat to 200°C (PLA), insert, extrude until flowing
4. **Clean bed**: Wipe with IPA
5. **Slice model**: Use PLA Standard preset from this guide
6. **Start print**: Load G-code, monitor first layer closely
7. **Adjust**: Fine-tune as needed

---

## Support Resources

- **Manufacturer**: [Anycubic Official Website](https://www.anycubic.com/)
- **Manual**: Check included documentation or Anycubic website
- **Community**: r/AnycubicKobra, Anycubic Facebook groups
- **Firmware**: Check Anycubic website for updates

---

**Last Updated**: 2024-11-01
**Firmware Version**: [Check your printer display: Menu > About]

---

## Notes Section

Use this space to record your specific findings for your individual printer:

**My Optimal PLA Temperature**: ___°C
**My Z-Offset Value**: ___mm
**My E-Steps**: ___ steps/mm
**My Flow Rate**: ___%

**Custom Notes**:
