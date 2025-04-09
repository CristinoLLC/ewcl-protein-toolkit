# EWCL: Entropy-Weighted Collapse Law Toolkit

A lightweight, non-dynamics, entropy-aware prediction engine for protein stability analysis and collapse scoring — validated against pLDDT, B-factor, and RMSD. Built for use in protein folding studies, drug discovery, and mutation impact research.

---

## 🚀 Features

- Entropy scoring from static PDB files
- Collapse probability curves via EWCL formula ($P_i \propto e^{-\lambda S_i}$)
- Region-specific comparison (WT vs Mutant)
- Overlay with pLDDT and B-factor
- 3D colored structure visualization using NGLView
- Correlation metrics: Pearson $r$, $R^2$, $p$-values
- Extensible for academic and biotech use cases

---

## 📦 Install Requirements

```bash
pip install -r requirements.txt
```

---

## 📂 Usage

Run the engine on your `.pdb` structure:

```python
from ewcl_static_tool import run_ewcl_on_pdb

labels, scores = run_ewcl_on_pdb("AF-P04637.pdb")
```

Then plot the collapse probabilities:

```python
import matplotlib.pyplot as plt

plt.plot(labels, scores)
plt.xlabel("Residue")
plt.ylabel("Entropy Likelihood")
plt.title("EWCL Collapse Score")
plt.show()
```

---

## 🧬 Try Your Own Protein

You can run the EWCL scoring engine on **any valid `.pdb` file** (from AlphaFold, RCSB, or your own data):

```python
from ewcl_static_tool import run_ewcl_on_pdb

labels, scores = run_ewcl_on_pdb("your_protein.pdb")
```

📈 From there, you can visualize the results like this:

```python
import matplotlib.pyplot as plt

plt.plot(labels, scores)
plt.xlabel("Residue")
plt.ylabel("Entropy Likelihood")
plt.title("EWCL Collapse Score")
plt.show()
```

📂 Place the `.pdb` file in the working directory or `/examples/`.

---

## 📁 Examples

See the `examples/` folder or download the full [EWCL Toolkit Example Pack](https://github.com/CristinoLLC/ewcl-protein-toolkit/releases) for:

- `EWCL_demo.ipynb`: sample notebook
- PDB files for Tau and p53
- Expected output image
- Reproducible results

---

## 📊 Validation Summary

| Metric          | Value     |
|-----------------|-----------|
| Pearson r       | ~0.14 (vs. B-factor) |
| p-value         | 1.14e-12  |
| Output Match    | Wild-type/mutant divergence observed |
| Runtime         | ~2s for 300+ residue proteins |

---

## 📜 License

This project is licensed under the MIT License. See `LICENSE` for details.

---

## 🧠 Citation

If you use this toolkit in your work, please cite the accompanying paper or repository.