# CompBioMed Lab - Ventricular Arrhythmia Localization

This repository contains the assets and report for a CompBioMed laboratory project focused on ventricular arrhythmia analysis from cardiac MRI data.

The work combines:
- Medical image segmentation of the left ventricle (LV) and scar tissue
- Mesh cleanup and post-processing
- Electrophysiology simulation and re-entry analysis
- ECG pattern exploration (ECGSIM)
- RVOT origin classification with machine learning

The full methodology and results are documented in `CompBiomed_REPORT.pdf`.

## Repository Contents

| Path | Description |
|---|---|
| `CompBiomed_REPORT.pdf` | Final project report (methodology, results, conclusions). |
| `p2_1.vtk` | Patient 2 cardiac MRI volume used as input data. |
| `2023-04-17-Scene.mrml` | 3D Slicer scene for loading/viewing the case setup. |
| `after_meshmixer_LV.stl` | LV mesh after Meshmixer post-processing. |
| `Segmentation_Scar.stl` | Scar segmentation mesh. |
| `myborder.stl` | Border zone mesh of scar tissue. |
| `mycore.stl` | Core zone mesh of scar tissue. |
| `ParaviewLV/filteredLV.pvd` | ParaView collection file for filtered LV output. |
| `ParaviewLV/filteredLV/filteredLV_0.vtp` | Filtered LV geometry referenced by the PVD file. |

## Software Used in the Project

- 3D Slicer (segmentation and scene management)
- Meshmixer (mesh cleaning/smoothing/decimation)
- ParaView (post-processing and visualization)
- Processing + Arritmic3D (simulation visualization)
- Python (data preparation and ML experiments)
- ECGSIM (ECG signal analysis)

## Quick Start

1. Open and read `CompBiomed_REPORT.pdf` for context and workflow details.
2. Load `2023-04-17-Scene.mrml` in 3D Slicer to inspect the MRI case (`p2_1.vtk`).
3. Open `ParaviewLV/filteredLV.pvd` in ParaView to inspect the processed LV mesh.
4. Compare scar-related meshes (`Segmentation_Scar.stl`, `myborder.stl`, `mycore.stl`) in your preferred 3D tool.

## Reported Outcomes (from the report)

- 3672 simulation runs in the parameter sweep
- 22 simulations with re-entry, 14 sustained re-entries
- Patient 2 identified as pro-arrhythmic in the analyzed setup
- Best RVOT classifier: XGBoost model (~82% test accuracy)

## Notes

- This repository mainly stores project artifacts (report + geometry/volume files).
- The full simulation and ML code used during the lab is described in the report but is not fully included here.
