# Project Template

To start a new part replication project:

1. Copy this `.template` folder to a new folder with a descriptive name:
   ```bash
   cp -r projects/.template projects/my-part-name-YYYY-MM-DD
   ```

2. Copy the `PROJECT_TEMPLATE.md` from the root directory into your new project folder:
   ```bash
   cp PROJECT_TEMPLATE.md projects/my-part-name-YYYY-MM-DD/README.md
   ```

3. Fill out the README.md with your project details as you progress

4. Organize your files:
   - `scans/` - Raw scan files from your iPhone/iPad
   - `models/` - Processed STL files ready for slicing
   - `sliced/` - G-code files for printing
   - `photos/` - Reference photos of the original part

## Naming Convention

Suggested folder naming: `[part-description]-[YYYY-MM-DD]`

Examples:
- `closet-bracket-2024-11-01`
- `drawer-handle-left-2024-11-15`
- `hinge-cover-bathroom-2024-12-01`

This keeps projects organized and chronologically sortable.
