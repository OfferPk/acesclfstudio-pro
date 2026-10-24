# ACESCLFStudio Pro (v1.0.0)

> **Academy S-2014-006 Common LUT Format (CLF) & ACES 2.0 Color Transform Workstation & CLI Validator**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](http://LICENSE) [![Academy Standards](https://img.shields.io/badge/Standard-Academy%20S--2014--006%20%2F%20ACES%202.0-gold.svg)](https://acescentral.com) [![Python](https://img.shields.io/badge/Python-3.8%2B-brightgreen.svg)](https://www.python.org/) ![Platform](https://img.shields.io/badge/Platform-Web%20%7C%20CLI%20%7C%20Docker-purple.svg)

---

## 🎨 Overview

**ACESCLFStudio Pro** is an autonomous engineering workstation designed for digital imaging technicians (DITs), colorists, VFX technical directors, and mastering engineers working in the **Academy Color Encoding System (ACES 1.3 / 2.0)** ecosystem. It provides:

1. **Academy S-2014-006 CLF Synthesis**: Generate production-ready XML color transformation files with Matrix, 1D Shaper LUT, and 3D Volumetric Lattice stages.  
2. **DaVinci Resolve / Adobe .cube Export**: Export high-precision 17³, 33³, and 65³ 3D LUT cubes for live on-set monitoring and grading suites.  
3. **10-Point Normative Auditor**: Automated verification engine validating XML schema conformance, RFC 4122 UUID identifiers, 32-bit floating-point bit depths, matrix dimensions, and lattice coordinate boundaries.  
4. **Standalone Python CLI (`clf-cli.py`)**: Zero-dependency command-line utility for VFX render pipelines and automated ingest QC.

---

## 🚀 Key Features

- **Standard ACES Primaries & Transforms**: Built-in support for AP0 (ACES2065-1), AP1 (ACEScg), Rec.709, Rec.2020 HDR, and DCI-P3 D65 cinema standards.  
- **Floating-Point Precision**: Enforces 32-bit floating-point (`inBitDepth="32f" outBitDepth="32f"`) chromaticity transformation stages preserving wide dynamic range without clipping.  
- **Multi-Stage Node Pipeline**: Matrix adaptation ➔ 1D non-linear shaper curve ➔ 3D trilinear color grading cube.  
- **On-the-Fly Look Grading**: Interactive sliders for Exposure (EV stops), Contrast Gamma, and Saturation with live matrix display.  
- **10/10 Normative Compliance**: Validated against Academy of Motion Picture Arts and Sciences (AMPAS) S-2014-006 standards.

---

## 🛠 Quick Start

### 1\. Interactive Web Studio

Open `source-code/index.html` directly in any modern web browser:

- Select an Input/Output transform preset.  
- Adjust exposure, contrast, and saturation in real time.  
- Generate and copy compliant Academy CLF XML.  
- Convert and download DaVinci Resolve `.cube` files.  
- Run the 10-point normative auditor.

### 2\. Standalone Python CLI

\# Display CLI help

python3 build/clf-cli.py \--help

\# Create a sample CLF transform file

python3 build/clf-cli.py create sample.clf \--name "ACEScg\_to\_Rec709" \--preset AP1\_to\_Rec709

\# Audit an existing CLF file

python3 build/clf-cli.py audit sample.clf

\# Convert CLF to DaVinci Resolve .cube

python3 build/clf-cli.py convert sample.clf \--out sample.cube \--size 33

### 3\. Run Automated Test Suite

python3 test\_clf.py

---

## 📁 Repository Structure

product\_275/

├── README.md                          \# Main project overview & user manual

├── test\_clf.py                        \# 10-point automated unit test suite

├── source-code/

│   ├── index.html                     \# Interactive multi-tab Studio UI

│   ├── clf.css                        \# Post-production dark theme stylesheet

│   ├── clf-engine.js                  \# ACES color transform & CLF XML engine

│   ├── clf-auditor.js                 \# 10-point normative compliance rules

│   └── app.js                         \# Application event controller & UI glue

├── build/

│   ├── clf-cli.py                     \# Standalone executable CLI utility

│   └── acesclfstudio-pro-v1.0.0.zip   \# Complete production release package

├── documentation/

│   ├── ARCHITECTURE.md                \# Academy S-2014-006 specification deep-dive

│   ├── USER\_GUIDE.md                  \# Comprehensive operational manual

│   └── MONETIZATION\_AND\_MARKETING\_PLAYBOOK.md \# Commercial strategy & pricing tiers

└── screenshots/

    └── clf-studio-preview.svg         \# High-resolution vector preview of GUI

---

## 📄 License

Released under the MIT License. Copyright © 2026 Autonomous Digital Product Factory.