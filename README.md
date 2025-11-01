# 3D Parts Replication Repository

A complete workflow and project management system for scanning, modeling, and 3D printing replacement parts.

## Overview

This repository contains everything you need to replicate plastic parts using 3D scanning and printing technology. Perfect for creating replacement parts for household items, closet organizers, appliances, and more.

## Equipment

- **Scanner**: iPhone 15 Pro or iPad Pro (M4) with LiDAR
- **Printer**: Anycubic Kobra 3
- **Computer**: For processing models and slicing

## Quick Start

1. **Read the Workflow**: Start with [`WORKFLOW.md`](WORKFLOW.md) for the complete step-by-step process
2. **Review Printer Settings**: Check [`config/anycubic-kobra-3.md`](config/anycubic-kobra-3.md) for detailed printer configuration
3. **Start a Project**: Copy the template and begin your first replication

## Repository Structure

```
3D-parts/
├── WORKFLOW.md              # Complete workflow guide (START HERE)
├── PROJECT_TEMPLATE.md      # Template for documenting each project
├── config/
│   └── anycubic-kobra-3.md # Printer-specific settings and calibration
├── projects/
│   └── .template/          # Template directory structure
│       ├── scans/          # Raw 3D scan files
│       ├── models/         # Processed STL files
│       ├── sliced/         # G-code files
│       └── photos/         # Reference images
└── reference/              # Additional reference materials
```

## The Three-Step Process

### 1. Scan the Part
Using your iPhone 15 Pro or iPad Pro M4:
- Use apps like Polycam, Scaniverse, or 3D Scanner App
- Capture all angles with good lighting
- Export as OBJ or STL

### 2. Build a 3D Model
Process and clean your scan:
- Use MeshLab, Meshmixer, or Blender
- Fix mesh errors, fill holes, smooth surfaces
- Add clearances for proper fit
- Export as STL for printing

### 3. Slice and Print
Prepare for your Anycubic Kobra 3:
- Use Anycubic Slicer or OrcaSlicer
- Select appropriate settings for your material
- Generate G-code and print
- Test fit and iterate as needed

## Documentation

- **[WORKFLOW.md](WORKFLOW.md)** - Comprehensive guide covering all three steps
- **[config/anycubic-kobra-3.md](config/anycubic-kobra-3.md)** - Printer settings, calibration, and troubleshooting
- **[PROJECT_TEMPLATE.md](PROJECT_TEMPLATE.md)** - Template for documenting each part replication

## Starting a New Project

To replicate a new part:

1. Create a new project folder:
   ```bash
   cp -r projects/.template projects/my-part-name-2024-11-01
   ```

2. Copy the project template:
   ```bash
   cp PROJECT_TEMPLATE.md projects/my-part-name-2024-11-01/README.md
   ```

3. Follow the workflow in `WORKFLOW.md`

4. Document your process in the project's README.md

## Recommended Apps & Software

### Scanning (iOS)
- **Polycam** - Professional quality, great LiDAR support
- **Scaniverse** - Free, user-friendly
- **3D Scanner App** - Simple interface, direct STL export

### Modeling (Desktop)
- **MeshLab** - Free, excellent for mesh cleanup
- **Meshmixer** - Free, great for repairs and modifications
- **Blender** - Free, professional-grade 3D modeling

### Slicing
- **Anycubic Slicer** - Pre-configured for Kobra 3
- **OrcaSlicer** - Advanced features
- **Cura** - Popular alternative

## Tips for Success

- **Scan carefully** - A good scan makes everything easier
- **Test fit early** - Print small test pieces before full parts
- **Document everything** - Future you will thank present you
- **Iterate** - First print rarely perfect, that's normal
- **Start simple** - Begin with PLA before trying exotic materials

## Common Use Cases

- Closet organizer parts
- Appliance knobs and handles
- Drawer brackets and guides
- Automotive interior clips
- Furniture hardware
- Electronics enclosure parts
- Tool organizers

## Resources

### Learning
- [Teaching Tech Calibration Guide](https://teachingtechyt.github.io/calibration.html)
- [Prusa Knowledge Base](https://help.prusa3d.com/)
- [All3DP Tutorials](https://all3dp.com/)

### Communities
- r/3Dprinting - General help and inspiration
- r/AnycubicKobra - Printer-specific community
- r/functionalprint - Practical printing projects

### Models (for reference)
- [Printables](https://www.printables.com/)
- [Thingiverse](https://www.thingiverse.com/)
- [Thangs](https://thangs.com/)

## Contributing

This repository is for personal use, but feel free to fork and adapt for your own workflow!

## License

Personal project - use freely

---

**Last Updated**: 2024-11-01
