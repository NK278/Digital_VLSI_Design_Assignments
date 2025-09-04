# Digital VLSI Design Assignments

This repository contains assignments and experiments related to **Digital VLSI (Very Large Scale Integration) Design**, carried out using **Cadence Design Systems** tools and the **UMC 65 nm (coms065) technology library**.

The goal is to bridge theory with hands‑on practice in a real CMOS technology node through schematic design, simulation, (optional) layout, and sign‑off checks.

---

## ✨ Overview
Digital VLSI Design focuses on implementing digital circuits at the transistor/gate level and evaluating key metrics such as **functionality, timing, power, and area**. Using **Cadence Virtuoso + Spectre/ADE** with **UMC 180 nm** and **UMC 65 nm (coms065)** PDKs, the work here emphasizes:
- RTL/logic‑level thinking mapped to transistor‑level schematics
- Testbench‑driven verification and waveform analysis
- (Optional) layout and physical verification (DRC/LVS/PEX)

---

## 🎯 Objectives
- Gain practical fluency with **Cadence Virtuoso** and **Spectre/ADE** workflows.  
- Design and verify digital logic in **180 nm** and **65 nm** CMOS nodes.  
- Understand the end‑to‑end flow: **schematic → simulation → (layout) → verification**.  
- Study trade‑offs among **delay, power, and area** in real PDKs.

---

## 🔧 Tools & Technology
- **EDA**: Cadence Virtuoso (schematic/layout), Spectre (simulation), ADE (analysis)  
- **PDKs**: UMC **180 nm** and UMC **65 nm (coms065)**  
- **Verification**: DRC, LVS, PEX (runset/corners provided by institute environment)

---

## ⚙️ Cadence Setup Instructions

### 1) Run Cadence for 180 nm
> One‑time environment setup per working directory.
```bash
mkdir cad180        # one time only
csh
cd cad180
source /cadence/cshrc
virtuoso
```

### 2) Run Cadence for 65 nm (coms065)
> One‑time environment setup per working directory.
```bash
mkdir cmos65        # one time only
csh
cd cmos65

cp /usr/local/cmos065_536/install/setup_working_dir_OA/.cdsinit ./
cp /usr/local/cmos065_536/install/setup_working_dir_OA/.cshrc_cmos065 ./
cp /usr/local/cmos065_536/install/setup_working_dir_OA/.simrc ./
cp /usr/local/cmos065_536/install/setup_working_dir_OA/.ucdprod ./
cp /usr/local/cmos065_536/install/setup_working_dir_OA/cds.lib ./

source ./.cshrc_cmos065
virtuoso
```

---

## 📂 Additional Desktop Workflow (Common on Lab Machines)
If you’re working from the Desktop and using global runsets/corners:
```bash
cd ~/Desktop

# Create folders
mkdir cmos65
mkdir eldo
cd cmos65
mkdir drcRunDir
mkdir lvsRunDir
mkdir pexRunDir

# Copy required setup files
cp /usr/local/cmos065_536/install/setup_working_dir_OA/.cdsinit .
cp /usr/local/cmos065_536/install/setup_working_dir_OA/.cshrc_cmos065 .
cp /usr/local/cmos065_536/install/setup_working_dir_OA/.simrc .
cp /usr/local/cmos065_536/install/setup_working_dir_OA/.ucdprod .
cp /usr/local/cmos065_536/install/setup_working_dir_OA/cds.lib .

# Copy technology corners and runsets
cp -r /global/corners/ .
cp /global/runset_drc_global ./drcRunDir/
cp /global/runset_lvs_global ./lvsRunDir/
```

> **Important:** The trailing `.` in the `cp` commands copies the file **into the current directory**. Don’t omit it.

---

## 🧪 Quick Usage Notes
- Launch **Virtuoso** inside your configured directory (e.g., `cmos65`) so it picks up the local `cds.lib`, `.cdsinit`, and `.simrc`.  
- In **ADE**, choose the correct simulator (**Spectre**) and corners if available.  
- For layout/verification, use your lab’s DRC/LVS runsets and corner libraries (as copied above).

---

## 📖 Learning Outcomes
- Confident use of **Cadence Virtuoso** for digital design and analysis.  
- Understanding of **PDK‑driven flows** in real technology nodes.  
- Ability to reason about **power‑delay‑area** trade‑offs.  
- Stronger fundamentals in **digital logic and VLSI methodology**.

---

## 👨‍💻 Author
**NK278** — Digital VLSI Design coursework and project submissions using Cadence (UMC 65 nm coms065, 180 nm).

---

## 📜 License
This repository is intended for **academic and learning purposes**. You may reference and adapt the material with proper attribution.
