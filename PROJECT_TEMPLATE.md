# Project Template

Copy this template for each new part replication project.

## Project: [Part Name]

**Date Started**: YYYY-MM-DD
**Status**: Planning / Scanning / Modeling / Printing / Complete
**Original Part Source**: [e.g., Closet organizer, Brand/Model if known]

---

## Part Information

### Physical Measurements
- Length: ___ mm
- Width: ___ mm
- Height/Thickness: ___ mm
- Critical dimensions: [Note any specific measurements that must be precise]
- Weight (original): ___ g

### Material
- Original material: [e.g., ABS, Polycarbonate, Nylon]
- Print material: [e.g., PLA, PETG, ABS]
- Color:

### Function
[Describe what this part does and how it's used]

### Failure Mode
[Why did the original part fail? This helps design a better replacement]

---

## Scanning Notes

**Date Scanned**: YYYY-MM-DD
**Device**: iPhone 15 Pro / iPad Pro M4
**App Used**: Polycam / 3D Scanner App / Scaniverse

### Scan Settings
- Scan quality: Low / Medium / High
- Processing: Device / Cloud
- Export format: OBJ / STL / USDZ

### Challenges
- [ ] Shiny/reflective surfaces
- [ ] Transparent areas
- [ ] Complex geometry
- [ ] Undercuts
- [ ] Small details

**Notes**: [Any special techniques used or issues encountered]

**Files**: `scans/[filename]`

---

## Modeling Notes

**Software Used**: MeshLab / Meshmixer / Blender

### Processing Steps
1. [e.g., Imported scan, removed noise]
2. [e.g., Filled holes in mesh]
3. [e.g., Smoothed surface]
4. [e.g., Reduced polygon count to 200K triangles]
5. [e.g., Added 0.3mm clearance to mounting holes]

### Design Modifications
- [ ] Reinforced weak points
- [ ] Added clearances for fit
- [ ] Improved mounting features
- [ ] Optimized for printing orientation

**Modifications Made**: [List any intentional changes from the original]

**Files**: `models/[filename].stl`

---

## Printing Configuration

### Slicer Settings
- **Slicer**: Anycubic Slicer / OrcaSlicer / Cura
- **Profile**: [Profile name or custom]
- **Layer Height**: 0.X mm
- **Perimeters**: X walls
- **Infill**: X%
- **Infill Pattern**: Gyroid / Grid / Honeycomb
- **Support**: Yes / No
- **Support Type**: [If used]

### Print Settings
- **Nozzle Temp**: X°C
- **Bed Temp**: X°C
- **Print Speed**: X mm/s
- **First Layer Speed**: X mm/s
- **Cooling**: X%
- **Adhesion**: None / Brim / Raft

### Material Details
- **Material**: PLA / PETG / ABS / TPU
- **Brand**:
- **Color**:
- **Spool**: New / Partially used / Dried

**Files**: `sliced/[filename].gcode`

---

## Print Log

### Attempt 1
**Date**: YYYY-MM-DD
**Result**: Success / Failed / Partial
**Print Time**: X hours X minutes
**Material Used**: X g / X m

**Issues**:
- [Any problems encountered]

**Solutions**:
- [What was done to fix issues]

### Attempt 2
[If needed]

---

## Post-Processing

- [ ] Supports removed
- [ ] Sanding (grits used: ___)
- [ ] Filing
- [ ] Drilling/tapping
- [ ] Heat treatment
- [ ] Painting/coating
- [ ] Assembly

**Notes**: [Details on post-processing steps]

---

## Testing & Validation

### Fit Check
- [ ] Mounting holes align
- [ ] Clearances correct
- [ ] Mating surfaces flush
- [ ] Interference-free operation

### Function Test
- [ ] Part performs intended function
- [ ] Load bearing adequate
- [ ] Movement smooth (if applicable)
- [ ] No unexpected wear or stress

### Durability
**Test Period**: [How long has it been installed/used?]
**Observations**: [Any issues or successes noted during use]

---

## Final Results

**Success**: Yes / No / Partial
**Would Print Again**: Yes / No
**Recommended Changes**: [What would you do differently next time?]

### Comparison to Original
- Strength: Better / Same / Worse
- Fit: Better / Same / Worse
- Appearance: Better / Same / Worse
- Cost: $X.XX (material only)

---

## Photos

Reference photos stored in `photos/`:
- [ ] Original part (multiple angles)
- [ ] Damaged/failed areas
- [ ] During scanning
- [ ] 3D model screenshots
- [ ] Print in progress
- [ ] Finished print
- [ ] Installed/in use

---

## Files Inventory

```
scans/
  - raw_scan_001.obj
  - [additional scans]

models/
  - part_v1.stl
  - part_v2_modified.stl
  - [design iterations]

sliced/
  - part_v2_draft.gcode
  - part_v2_final.gcode

photos/
  - original_01.jpg
  - [reference photos]
```

---

## Lessons Learned

[Document what you learned from this project that will help with future parts]

---

## Notes

[Any additional notes, observations, or reminders]
