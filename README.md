# EWCL: Entropy-Weighted Collapse Law Toolkit

A lightweight, non-dynamics, entropy-aware prediction engine for protein stability analysis and collapse scoring — validated against pLDDT, B-factor, and RMSD. Built for use in protein folding studies, drug discovery, and mutation impact research.

## 🔬 Features
- Entropy scoring from static PDB files
- Collapse probability curves via EWCL formula ($P_i \propto e^{-\lambda S_i}$)
- Region-specific comparison (WT vs Mutant)
- Overlay with pLDDT and B-factor
- 3D colored structure visualization using NGLView
- Correlation metrics: Pearson r, R², p-values
- Extensible for academic and biotech use cases

## 🧪 Usage

### 📦 Install Requirements
```bash
pip install -r requirements.txt
```

### 🚀 Run Example (P53)
```bash
jupyter notebook examples/demo_p53.ipynb
```

### ⚡ Quick Test (CLI)
```bash
python ewcl_toolkit/ewcl_entropy_scoring.py --input data/sample_structures/AF-p53.pdb --region 120 160
```

## 📁 Project Structure
```
.
├── README.md
├── LICENSE
├── requirements.txt
├── ewcl_toolkit/
│   ├── __init__.py
│   ├── ewcl_entropy_scoring.py       # Main EWCL logic
│   ├── region_analysis.py            # WT vs Mutant comparisons
│   ├── visualization.py              # Plotting + 3D rendering
│   └── utils.py                      # Shared tools (e.g. RMSD, pLDDT loaders)
├── examples/
│   ├── demo_p53.ipynb
│   ├── demo_tau.ipynb
│   └── mutant_vs_wt.ipynb
├── data/
│   └── sample_structures/
│       ├── AF-p53.pdb
│       ├── BRCA1_wt.pdb
│       └── Tau_AF.pdb
├── test/
│   └── test_entropy_score.py
└── .github/
    └── workflows/
        └── python-app.yml            # Continuous integration
```

### 📁 Examples
To explore the toolkit interactively:

1. Go to the [`examples/`](examples) folder.
2. Open `EWCL_demo.ipynb` to run a ready-to-go analysis.
3. Use the `.pdb` files for Tau and p53 as test cases.
4. Compare output with `expected_output.png`.
5.
6. ## 🧠 Citation
*Preprint in preparation. Contact for early access.*

## 🔬 Test & Continuous Integration
CI via GitHub Actions to ensure stability:
- Automatic testing on push/PR
- Unit tests for entropy + plotting logic

## 🔗 License
MIT

## 🙋 Contributing
- Pull requests welcome
- Open issues for bugs or feature suggestions
- Let's collaborate across academia and biotech 🚀

