# Pharmacophore-Guided Substructure Incorporation

A workflow for identifying and incorporating structurally diverse substructures into a reference molecule while preserving key molecular interactions through pharmacophore matching.

## Overview

This project implements a **pharmacophore-guided substructure incorporation** workflow for integrating chosen substructures into a reference molecule. It performs the following:

1. Extracts pharmacophore features from the reference molecule and input substructures.
2. Identifies feature correspondences between the reference molecule and substructures.
3. Aligns the input substructure to the pharmacophore of the reference molecule.
4. Integrates the aligned substructure into the reference molecule to generate new molecular structures.

The generated molecules can also be used as inputs to the [FARE](https://github.com/CathereneTomy/FARE/tree/main) repository to identify suitable fragment replacements, if desired.

## Installation

### Option 1: Using Conda (Recommended)

1. Clone the repository:

   ```bash
   git clone https://github.com/CathereneTomy/Ph-GSI.git
   cd Ph-GSI
   ```

2. Create the environment from the YAML file:

   ```bash
   conda env create -f environment_phgsi.yml
   ```

3. Activate the environment:

   ```bash
   conda activate phgsi
   ```

### Option 2: Using pip

1. Clone the repository:

   ```bash
   git clone https://github.com/CathereneTomy/Ph-GSI.git
   cd Ph-GSI
   ```

2. Create a Python 3.14 virtual environment (Conda is recommended).

3. Install the dependencies:

   ```bash
   pip install -r requirements.txt
   ```

## Running the Project

### Using Jupyter Notebook

1. Start Jupyter:

   ```bash
   jupyter notebook
   ```

2. Open `ph-gsi.ipynb` in your browser.

3. Run the cells sequentially to execute the **pharmacophore-guided substructure incorporation** workflow.

### Example Usage

The notebook demonstrates pharmacophore-guided incorporation using:

* **Reference molecule**: `Cc1ccc(-c2cc(C(F)(F)F)nn2-c2ccc(S(N)(=O)=O)cc2)cc1`
* **Input substructure**: `C1=CNC2=CN=CN=C21`

Key functions:

* `ph_similarity_pipeline()` — Computes pharmacophore similarity.
* `align_and_visualize()` — Aligns the input substructure with the reference pharmacophore.
* `build_ph_gsi_molecule()` — Generates molecules by incorporating the aligned substructure into the reference molecule.

## Project Structure

```text
.
├── README.md                    # This file
├── requirements.txt             # Python dependencies (pip)
├── environment_phgsi.yml        # Conda environment definition
├── ph-gsi.ipynb                 # Main Jupyter notebook
├── utils.py                     # Core utility functions
└── alignment.png                # Example output
```

## Output

The pipeline produces:

* Pharmacophore alignment visualizations
* Substructure-incorporated molecule SMILES
* RMSD and query coverage metrics
* 2D molecular visualizations
