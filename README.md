# Discovery-of-mMiniaturized-CDPCE-MD-result
## F4/B31 Selected MD Systems

  Molecular dynamics trajectories and analysis scripts for selected F4 and B31 enzyme–DNA systems.

  ## MD Analysis Scripts

  - F4 analysis script: `scripts/analyze_F4_selected8_two_metrics.py`
  - B31 analysis script: `scripts/analyze_B31_target_c_base_rmsd.py`

  ## MD Results

  - `F4_B31_16systems_analysis_package_20260916.tar.gz`

  The package contains initial structures, solvated structures, topology files, production trajectories, and minimal
  analysis scripts for 16 selected MD systems.

  ## Included Systems

  ### F4 systems

  Eight F4 trajectories are included:

  - F4_WT_preC
  - F4_WT_preA
  - F4_WT_preT
  - F4_WT_preG
  - F4_E70K_preC
  - F4_E70K_preA
  - F4_E70K_preT
  - F4_E70K_preG

  For each F4 system, the package contains:

  - initial PDB structure
  - solvated PDB structure
  - Amber topology file: `solv.prmtop`
  - production trajectory: `production.xtc`

  ### B31 systems

  Eight B31 trajectories are included:

  - B31_WT_preA
  - B31_WT_preC
  - B31_WT_preG
  - B31_WT_preT
  - B31_R47D_preA
  - B31_R47D_preC
  - B31_R47D_preG
  - B31_R47D_preT

  For each B31 system, the package contains:

  - initial PDB structure
  - solvated PDB structure
  - Amber topology file: `solv.prmtop`
  - production trajectory: `screen.xtc`

  ## MD Method

  ### Step 1. Initial structure preparation

  Initial enzyme–DNA complex structures were prepared for F4 and B31 systems.
  For F4, selected WT and E70K systems with different DNA sequence contexts were used.
  For B31, selected WT and R47D systems with different −1 DNA base identities were used.

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

  Production MD trajectories were collected for the selected F4 and B31 systems.

  Trajectory files included in this package:

  - F4: `production.xtc`
  - B31: `screen.xtc`

  The analysis window used in the provided scripts is:

  - 10–100 ns
  - 0.1 ns bin size

  ### Step 4. Trajectory analysis

  Trajectory analysis was performed using MDTraj, MDAnalysis, NumPy, pandas-compatible CSV output, and custom Python
  scripts.

  For F4 systems, the provided script calculates:

  - `target_c_base_rmsd_mean_A`
  - `e70_sidechain_dna2_backbone_occ_le_4A`

  For B31 systems, the provided script calculates:

  - `target_c_base_rmsd_mean_A`

  RMSD calculations use the initial trajectory frame as the reference structure after protein backbone alignment.
