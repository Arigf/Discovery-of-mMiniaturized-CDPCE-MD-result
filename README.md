# Discovery-of-mMiniaturized-CDPCE-MD-result
## Sdd-CC/Sdd-TC Selected MD Systems

  Molecular dynamics trajectories and analysis scripts for selected Sdd-CC and Sdd-TC enzyme–DNA systems.

  ## MD Analysis Scripts

  - Sdd-CC analysis script: `scripts/analyze_Sdd-CC_selected8_two_metrics.py`
  - Sdd-TC analysis script: `scripts/analyze_Sdd-TC_target_c_base_rmsd.py`

  ## MD Results

  - `Sdd-CC_Sdd-TC_16systems_analysis_package_20260916.tar.gz`

  The package contains initial structures, solvated structures, topology files, production trajectories, and minimal
  analysis scripts for 16 selected MD systems.

  ## Included Systems

  ### Sdd-CC systems

  Eight Sdd-CC trajectories are included:

  - Sdd-CC_WT_preC
  - Sdd-CC_WT_preA
  - Sdd-CC_WT_preT
  - Sdd-CC_WT_preG
  - Sdd-CC_E70K_preC
  - Sdd-CC_E70K_preA
  - Sdd-CC_E70K_preT
  - Sdd-CC_E70K_preG

  For each Sdd-CC system, the package contains:

  - initial PDB structure
  - solvated PDB structure
  - Amber topology file: `solv.prmtop`
  - production trajectory: `production.xtc`

  ### Sdd-TC systems

  Eight Sdd-TC trajectories are included:

  - Sdd-TC_WT_preA
  - Sdd-TC_WT_preC
  - Sdd-TC_WT_preG
  - Sdd-TC_WT_preT
  - Sdd-TC_R47D_preA
  - Sdd-TC_R47D_preC
  - Sdd-TC_R47D_preG
  - Sdd-TC_R47D_preT

  For each Sdd-TC system, the package contains:

  - initial PDB structure
  - solvated PDB structure
  - Amber topology file: `solv.prmtop`
  - production trajectory: `screen.xtc`

  ## MD Method

  ### Step 1. Initial structure preparation

  Initial enzyme–DNA complex structures were prepared for Sdd-CC and Sdd-TC systems.
  For Sdd-CC, selected WT and E70K systems with different DNA sequence contexts were used.
  For Sdd-TC, selected WT and R47D systems with different −1 DNA base identities were used.

  The selected systems were prepared as enzyme–DNA complexes containing the catalytic metal center and relevant DNA
  substrate region.

  ### Step 2. MD system preparation

  MD systems were prepared using Amber/OpenMM-compatible topology files.

  Each system includes:

  - solvated structure
  - Amber topology file
  - production trajectory
  - corresponding initial PDB structure

  The topology files are required for trajectory loading and reproducible analysis.

  ### Step 3. Production MD

  Production MD trajectories were collected for the selected Sdd-CC and Sdd-TC systems.

  Trajectory files included in this package:

  - Sdd-CC: `production.xtc`
  - Sdd-TC: `screen.xtc`

  The analysis window used in the provided scripts is:

  - 10–100 ns
  - 0.1 ns bin size

  ### Step 4. Trajectory analysis

  Trajectory analysis was performed using MDTraj, MDAnalysis, NumPy, pandas-compatible CSV output, and custom Python
  scripts.

  For Sdd-CC systems, the provided script calculates:

  - `target_c_base_rmsd_mean_A`
  - `e70_sidechain_dna2_backbone_occ_le_4A`

  For Sdd-TC systems, the provided script calculates:

  - `target_c_base_rmsd_mean_A`

  RMSD calculations use the initial trajectory frame as the reference structure after protein backbone alignment.
