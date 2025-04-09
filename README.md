# 🧬 Entropy-Weighted Collapse Law (EWCL) Protein Toolkit

A lightweight Python-based engine for analyzing protein structural uncertainty using the **Entropy-Weighted Collapse Law (EWCL)** — a novel approach that estimates the most probable structural conformations based on entropy-driven collapse probability.

---

## 🌟 Key Features
- Non-simulation entropy scoring — no MD required
- Compare EWCL scores with pLDDT, B-factor, or RMSD
- Identify unstable/mutated regions in proteins
- Compatible with AlphaFold or RCSB `.pdb` files
- Works in Colab or locally (via pip)

---

## 📦 Installation
```bash
pip install -r requirements.txt
```
Or run directly in Google Colab:
```python
# Upload your PDB file, then:
!python ewcl_static_tool_colab.py
```

---

## 🚀 Quickstart
```python
from ewcl import run_ewcl_on_pdb
labels, scores = run_ewcl_on_pdb("example.pdb")
```

---

## 📂 Input Requirements
- Standard `.pdb` file from AlphaFold or RCSB
- pLDDT values should be embedded in the **B-factor column**
  > If not explicitly provided, the EWCL tool uses the **B-factor column as a proxy for pLDDT**.
- Clean structural chain (heteroatoms and DNA optional but not required)

---

## 📊 Example Output
```python
labels = ['GLY_45', 'ARG_46', 'LEU_47', 'PHE_48']
scores = [0.072, 0.094, 0.083, 0.051]  # EWCL collapse probabilities
```
These scores reflect entropy-weighted likelihood of collapse at each residue. Lower values = higher entropy = less likely to persist.

---

## 📈 Visualizations
```python
from ewcl import plot_ewcl_scores, compare_with_plddt
plot_ewcl_scores(labels, scores)
compare_with_plddt(labels, scores, plddt_values)
```

### 📷 Example Visual Output
- EWCL Collapse Line Plot:
  ![Line Plot](docs/imgs/ewcl_line.png)
- pLDDT Comparison Scatter:
  ![Scatter Plot](docs/imgs/plddt_scatter.png)
- Highlighted Outliers:
  ![Outlier Highlight](docs/imgs/outliers.png)

---

## 🧪 Advanced Usage
You can zoom in on regions of interest:
```python
labels, scores = run_ewcl_on_pdb("brca1.pdb", region=(120, 160))
```
Compare wild-type and mutant proteins:
```python
from ewcl import compare_models
compare_models("brca1_wt.pdb", "brca1_mut.pdb", region=(270, 310))
```

---

## 🔬 Research Applications
- Protein stability scoring
- Disorder prediction
- Mutational impact assessment
- Structural outlier detection
- Biotech & drug target validation

---

## 🧬 Want to try your own protein?
Upload any valid `.pdb` file (from AlphaFold or RCSB) into the working directory and run it through the EWCL engine:
```python
labels, scores = run_ewcl_on_pdb("your_protein.pdb")
```

---

## 📜 License & IP Notes
This toolkit is **open for academic and non-commercial use**. It is currently protected under a **provisional patent**. Contributions are welcome for further development.

---

## 📚 References
- Quantum entropy collapse laws (PDQC, EWCL)
- AlphaFold pLDDT documentation
- OpenMM & MDTraj libraries
- RMSD and structural entropy models

---

## ⚙️ Coming Soon
- Interactive GUI panel for residue exploration
- Real-time lambda adjustment for collapse tuning
- Expanded comparison to RMSF and MD-derived metrics

---

## 📦 How to Cite
Cristino, L. et al. (2025). *Entropy-Weighted Collapse Law: A New Framework for Structure Prediction and Disorder Detection*. GitHub Repository: https://github.com/CristinoLLC/ewcl-protein-toolkit

