# OCT .vol Frame Extractor (MATLAB)
Utilities to extract all OCT B-scan frames from Heidelberg/HEYEX .vol files and organize them into separate MS and Control sets. The toolkit also prepares basic metadata and preprocessing outputs.

# Features
.Extracts every B-scan frame from each .vol file
.Saves frames into class-specific folders (MS / Control)
.Preprocesses and returns metadata for downstream analysis
.Batch processing over multiple .vol files

mkdir -p project-root/{data/{MS,Control},output/{extracted_frames_MS,extracted_frames_Control}}
touch project-root/{openval.m,saveBscanFrames.m,processMultipleVolFiles.m,README.md}

# How it works

- openval.m
Reads a .vol file, prepares all B-scan frames and metadata, and applies the required preprocessing.

saveBscanFrames.m
Saves frames to the proper output directory (MS or Control), creating subfolders as needed.

processMultipleVolFiles.m
Finds all .vol files under a given input folder and runs the end-to-end pipeline (calls openval → saveBscanFrames) for each file.

# Usage

Place your .vol files under:

data/MS/ for MS subjects

data/Control/ for control subjects

Run the batch processor twice—once per class—so frames land in:

output/extracted_frames_MS/

output/extracted_frames_Control/

Inspect results with your preferred image viewer or MATLAB apps (e.g., Volume Viewer).

# Notes

Designed around Heidelberg/HEYEX .vol exports (OCT).

Make sure you have the necessary MATLAB toolboxes for image I/O/visualization if you plan to review frames inside MATLAB.

## MS vs Control

| MS | Control |
|---|---|
| ![MS](output/extracted_frames_MS/ms01_spectralis_macula_v1_s1_R/ms01_spectralis_macula_v1_s1_R_frame_001.png) | ![Control](output/extracted_frames_Control/hc01_spectralis_macula_v1_s1_R/hc01_spectralis_macula_v1_s1_R_frame_001.png) |

