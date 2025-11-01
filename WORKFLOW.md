# 3D Part Replication Workflow

Complete guide for scanning, modeling, slicing, and printing replacement parts.

## Equipment

- **Scanner**: iPhone 15 Pro or iPad Pro (M4) - both have LiDAR sensors
- **Printer**: Anycubic Kobra 3
- **Computer**: For processing and slicing

---

## Step 1: Scan the Part

### Recommended Scanning Apps

#### Option A: Polycam (Recommended)
- **Platform**: iOS (iPhone 15 Pro / iPad Pro M4)
- **Cost**: Free tier available, Pro features $10/month
- **Pros**:
  - Excellent LiDAR integration
  - Clean mesh output
  - Direct export to common formats (OBJ, STL, USDZ, GLB)
  - Cloud processing for high-quality meshes
- **Download**: [App Store - Polycam](https://apps.apple.com/app/polycam-lidar-3d-scanner)

#### Option B: 3D Scanner App
- **Platform**: iOS
- **Cost**: Free with in-app purchases
- **Pros**:
  - Simple interface
  - Good for small objects
  - Direct STL export
- **Download**: [App Store - 3D Scanner App](https://apps.apple.com/app/3d-scanner-app)

#### Option C: Scaniverse
- **Platform**: iOS
- **Cost**: Free
- **Pros**:
  - Completely free
  - Good quality scans
  - Exports to OBJ, USDZ, GLB
- **Download**: [App Store - Scaniverse](https://apps.apple.com/app/scaniverse)

### Scanning Best Practices

1. **Lighting**: Use even, diffuse lighting. Avoid harsh shadows and direct sunlight.

2. **Background**: Place the part on a contrasting, non-reflective surface. Avoid glass or shiny surfaces.

3. **Part Preparation**:
   - Clean the part thoroughly
   - For shiny/transparent parts, consider using scanning spray (washable powder coating)
   - Matte, textured surfaces scan better than glossy ones

4. **Scanning Technique**:
   - Hold your device steady, move slowly and smoothly
   - Circle around the object at multiple heights (low, middle, high)
   - Capture all angles, including undercuts and internal features
   - Overlap each pass by 30-50%
   - For small parts, use a turntable if available

5. **Multiple Scans**: For complex parts, scan from multiple orientations and merge later

6. **Export Format**: Export as OBJ or STL for best compatibility

### Scan Checklist
- [ ] Part is clean and dry
- [ ] Good, even lighting setup
- [ ] Contrasting background prepared
- [ ] Multiple angles captured
- [ ] All critical features visible
- [ ] Scan exported in OBJ or STL format

---

## Step 2: Build a 3D Model

### Processing the Scan

#### Option A: Polycam's Built-in Processing
If using Polycam Pro, use their cloud processing to generate a clean mesh directly.

#### Option B: Mesh Cleanup Software

**MeshLab (Free & Open Source)**
- **Download**: [MeshLab](https://www.meshlab.net/)
- **Use for**:
  - Cleaning up scan artifacts
  - Removing noise
  - Filling holes
  - Reducing polygon count

**Meshmixer (Free)**
- **Download**: [Meshmixer by Autodesk](https://www.meshmixer.com/)
- **Use for**:
  - Advanced mesh repair
  - Smoothing
  - Hollowing parts (to save material)
  - Adding supports

**Blender (Free & Open Source)**
- **Download**: [Blender](https://www.blender.org/)
- **Use for**:
  - Professional-grade mesh editing
  - Retopology (creating clean geometry)
  - Sculpting details
  - Boolean operations

### Modeling Workflow

1. **Import the Scan**
   - Load OBJ or STL file into your chosen software
   - Check scale (measure a known dimension)

2. **Clean the Mesh**
   ```
   MeshLab workflow:
   - Filters > Cleaning and Repairing > Remove Duplicate Faces
   - Filters > Cleaning and Repairing > Remove Duplicate Vertices
   - Filters > Smoothing, Fairing and Deformation > Laplacian Smooth
   - Filters > Remeshing, Simplification and Reconstruction > Quadric Edge Collapse Decimation
   ```

3. **Fix Errors**
   - Fill holes
   - Remove disconnected components
   - Fix inverted normals
   - Ensure manifold geometry (watertight mesh)

4. **Optimize**
   - Reduce polygon count while maintaining detail
   - Target: 100K-500K triangles for most parts
   - Keep higher detail for critical features

5. **Measure & Adjust**
   - Verify critical dimensions
   - Add clearances where needed (typically 0.2-0.5mm for fitting parts)
   - Scale if necessary

6. **Export for Printing**
   - Export as STL (binary format preferred)
   - Check units (usually mm for 3D printing)
   - Verify proper orientation

### Modeling Checklist
- [ ] Mesh is watertight (no holes)
- [ ] All normals face outward
- [ ] Scale is correct
- [ ] Critical dimensions verified
- [ ] Clearances added for fitting parts
- [ ] Exported as binary STL

---

## Step 3: Slice and Print

### Slicing Software for Anycubic Kobra 3

**Anycubic Slicer (Recommended)**
- Based on PrusaSlicer
- Pre-configured profiles for Kobra 3
- Download from Anycubic website

**Alternative: OrcaSlicer**
- **Download**: [OrcaSlicer](https://github.com/SoftFever/OrcaSlicer)
- Excellent for multi-color and advanced features
- May need manual profile configuration

**Alternative: Cura**
- **Download**: [Ultimaker Cura](https://ultimaker.com/software/ultimaker-cura)
- Will need Kobra 3 profile setup

### Anycubic Kobra 3 Specifications

- **Build Volume**: 250 x 250 x 260 mm
- **Nozzle**: 0.4mm (standard)
- **Max Hotend Temp**: 300°C
- **Max Bed Temp**: 100°C
- **Print Speed**: Up to 500mm/s (recommended 50-150mm/s for quality)

### Slicing Settings for Replacement Parts

#### General Settings (PLA)
```
Layer Height: 0.2mm (balance of speed and quality)
First Layer Height: 0.2mm
First Layer Speed: 20mm/s

Perimeters: 3-4 walls
Top/Bottom Layers: 4-5 layers
Infill: 20-40% (depending on strength requirements)
Infill Pattern: Gyroid or Grid

Print Speed: 60-80mm/s
Travel Speed: 150-200mm/s

Temperature:
  - Nozzle: 200-210°C (PLA)
  - Bed: 60°C

Cooling: 100% after first layer
Supports: Only if needed (prefer to orient to minimize)
```

#### For Functional/Structural Parts
```
Layer Height: 0.15-0.2mm
Perimeters: 4-5 walls
Infill: 40-60%
Infill Pattern: Gyroid (strong and efficient)
Temperature: Tune for your filament
Consider: PETG or ABS for better strength
```

#### For Precise Fitting Parts
```
Layer Height: 0.1-0.15mm
Perimeters: 4 walls
First Layer: Tuned carefully for adhesion
Cooling: Maximum for dimensional accuracy
Speed: Reduce to 50mm/s for better quality
Elephant's Foot Compensation: Enable
```

### Pre-Print Checklist
- [ ] STL loaded and oriented properly
- [ ] Part fits on build plate
- [ ] Supports added if needed (minimize)
- [ ] Brim or raft if adhesion is a concern
- [ ] Layer height appropriate for detail needed
- [ ] Infill percentage suitable for strength requirements
- [ ] Temperatures correct for filament
- [ ] Preview shows no errors
- [ ] Estimated time and material acceptable

### Printing Process

1. **Prepare the Printer**
   - Level the bed (auto-level on Kobra 3)
   - Clean the build surface
   - Ensure filament is dry and loaded

2. **First Layer is Critical**
   - Watch the first layer closely
   - Adjust Z-offset if needed
   - Should be slightly squished but not too flat

3. **Monitor the Print**
   - Check periodically for failures
   - Watch for warping or lifting
   - Ensure supports are working if used

4. **Post-Processing**
   - Remove supports carefully
   - Sand smooth if needed
   - Test fit before finishing

### Troubleshooting Common Issues

**Part doesn't fit**
- Check if model dimensions match original
- Add clearance in modeling stage (0.2-0.5mm)
- Verify printer is calibrated (e-steps, flow rate)

**Poor surface quality**
- Reduce print speed
- Lower layer height
- Adjust temperature
- Check for mechanical issues

**Warping**
- Increase bed temperature
- Add brim or raft
- Enclose printer for ABS/PETG
- Check for drafts

**Layer adhesion issues**
- Increase temperature
- Dry filament
- Slow down print speed
- Check for partial clogs

---

## Project Organization

For each part you replicate, create a folder in `/projects/` with:

```
projects/
  └── closet-bracket-2024-11-01/
      ├── scans/           # Raw scan files (OBJ, PLY, etc.)
      ├── models/          # Processed 3D models (STL)
      ├── sliced/          # G-code files
      ├── photos/          # Reference photos
      ├── notes.md         # Project notes and measurements
      └── README.md        # Part-specific documentation
```

See `PROJECT_TEMPLATE.md` for a template to copy for each project.

---

## Material Selection Guide

### PLA
- **Best for**: General replacement parts, indoor use
- **Pros**: Easy to print, rigid, biodegradable
- **Cons**: Lower heat resistance (60°C), brittle
- **Use for**: Most closet parts, brackets, organizational items

### PETG
- **Best for**: Functional parts needing durability
- **Pros**: Strong, flexible, heat resistant (80°C), chemical resistant
- **Cons**: Strings more, harder to print
- **Use for**: Parts under stress, outdoor use, frequently handled parts

### ABS
- **Best for**: High-temperature applications
- **Pros**: Very strong, heat resistant (100°C), can be smoothed with acetone
- **Cons**: Requires enclosure, warps easily, fumes
- **Use for**: Parts near heat sources, automotive applications

### TPU (Flexible)
- **Best for**: Gaskets, seals, shock absorption
- **Pros**: Flexible, durable, resistant to abrasion
- **Cons**: Slow to print, requires direct drive
- **Use for**: Bumpers, feet, flexible connectors

---

## Tips for Success

1. **Measure Twice, Print Once**: Verify dimensions before committing to a long print
2. **Start Simple**: Begin with PLA for your first prints
3. **Iterate**: First print at draft quality to test fit, then print final at high quality
4. **Document Everything**: Take photos, note settings, record what works
5. **Keep Originals**: Don't throw away the original until replacement is proven
6. **Test Fit Often**: Print test pieces of critical dimensions first
7. **Consider Strength**: Print orientation affects strength significantly

---

## Resources

### Communities
- r/3Dprinting - General 3D printing help
- r/AnycubicKobra - Kobra-specific community
- r/functionalprint - Inspiration for practical prints

### Learning
- [Teaching Tech Calibration](https://teachingtechyt.github.io/calibration.html)
- [Prusa Knowledge Base](https://help.prusa3d.com/)
- [All3DP Guides](https://all3dp.com/topic/3d-printing-guides/)

### File Repositories (for reference/inspiration)
- [Thingiverse](https://www.thingiverse.com/)
- [Printables](https://www.printables.com/)
- [Thangs](https://thangs.com/)

---

## Quick Reference Commands

### MeshLab Cleanup Pipeline
```
1. Remove duplicates: Filters > Cleaning > Remove Duplicate Faces/Vertices
2. Smooth: Filters > Smoothing > Laplacian Smooth (5-10 steps)
3. Fill holes: Filters > Remeshing > Close Holes
4. Simplify: Filters > Remeshing > Quadric Edge Collapse Decimation
5. Export: File > Export Mesh As > STL (Binary)
```

### Printer Calibration Tests
```
1. Bed level test print
2. Temperature tower (find optimal temp)
3. Retraction test (minimize stringing)
4. Flow rate calibration (dimensional accuracy)
5. First layer calibration (adhesion)
```

---

**Good luck with your part replication!**
