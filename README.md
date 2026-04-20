# 📍 SCA-BA for Distributed Generation Placement in Power Systems
[![DOI](https://zenodo.org/badge/1205068047.svg)](https://doi.org/10.5281/zenodo.19473443)

Metaheuristic optimization framework combining **Sine-Cosine Algorithm (SCA)** and **Bat Algorithm (BA)** for optimal placement of **Distributed Generation (DG)** units in power distribution systems.

This project demonstrates how nature-inspired algorithms can determine the optimal location and sizing of DG units to minimize power losses and improve voltage profile.

---

## 📄 Related Publication

Yustika, L.M., Raharjo, J., Ikhsan, R.R.N., Wijaya, I.G.P.O.I. (2025)
*Comparison of Sine-Cosine and Bat Algorithm for Distributed Generation Placement*
Jurnal Nasional Teknik Elektro dan Teknologi Informasi
https://doi.org/10.22146/v14i3.19191

---

## 🚀 Features

- 🔆 Optimal DG placement using **SCA** and **BA**
- 📉 Minimizes **total active power losses**
- ⚡ Improves **voltage profile** across all buses
- ⚙️ Supports key constraints:
  - Bus voltage limits
  - DG capacity limits
  - Power balance constraint
- 🧪 Validated on **IEEE 9-bus test system**
- 🧠 Clean and modular Python implementation

---

## 🧠 Method Overview

The DG placement problem aims to minimize total active power loss:

$$P_{loss} = \sum_{k=1}^{n_b} r_k \frac{P_k^2 + Q_k^2}{V_k^2}$$

Subject to:
- $V_{min} \leq V_i \leq V_{max}$ — voltage limits
- $P_{DG,min} \leq P_{DG} \leq P_{DG,max}$ — DG capacity limits
- Power balance at each bus

Two algorithms are compared:

- **SCA** → sine-cosine oscillatory update for exploration and exploitation
- **BA** → echolocation-inspired search for frequency-controlled optimization

Both methods are benchmarked on the same test system for fair comparison.

---

## 📊 Key Results

**Normal Load Condition:**

| Condition | Active Loss (MW) | Reactive Loss (MVAR) | Loss Reduction (Active) | Loss Reduction (Reactive) |
|-----------|-----------------|---------------------|------------------------|--------------------------|
| Base case (no DG) | 34.70 | 31.16 | — | — |
| SCA | 5.35 | 2.06 | **85%** | **93%** |
| BA  | 30.96 | 11.98 | 11% | 61% |

**Load Increase +10% Condition:**

| Condition | Active Loss (MW) | Reactive Loss (MVAR) | Loss Reduction (Active) | Loss Reduction (Reactive) |
|-----------|-----------------|---------------------|------------------------|--------------------------|
| SCA | 30.80 | 11.88 | 11% | 62% |
| BA  | 34.70 | 29.01 | 0% | 6.9% |

**DG Placement (Bus 6):**

| Method | DG Location | DG Capacity |
|--------|------------|-------------|
| SCA    | Bus 6      | 250 kW      |
| BA     | Bus 6      | 299 kW      |

**SCA achieves:**
- **85% active power loss reduction** and **93% reactive power loss reduction** under normal load
- Voltage profile maintained within 0.98–1.02 pu across all buses
- Superior robustness under 10% load growth scenario

---

## 📂 Project Structure

```text
sca-ba-dg-placement/
├── notebooks/
│   ├── SCA_DG_Placement.ipynb   # SCA implementation
│   └── BA_DG_Placement.ipynb    # BA implementation
├── results/                      # Output & analysis
├── README.md
├── .gitignore
└── LICENSE
```

---

## ⚙️ Requirements

- Python 3.x
- NumPy
- Matplotlib
- Jupyter Notebook

Install dependencies:

```bash
pip install numpy matplotlib
```

---

## ▶️ Usage

Clone and run the notebooks:

```bash
git clone https://github.com/Kiky-41/sca-ba-dg-placement.git
cd sca-ba-dg-placement
jupyter notebook
```

Open either notebook under `/notebooks` and run all cells.

---

## 📊 Dataset

The test system used is the **IEEE 9-bus distribution system**.

**Bus data parameters:**

| Parameter | Description |
|-----------|-------------|
| P, Q load | Active and reactive load per bus |
| V nominal  | Nominal bus voltage |
| Line impedance | Resistance and reactance per branch |
| DG limits  | Min/max DG capacity per bus |

---

## 📌 Reproducibility

This repository focuses on the algorithm implementation.
Simulation results may vary depending on system parameters and convergence settings.

---

## 📖 Citation

If you use this work, please cite:

```bibtex
@article{yustika2025scaba,
  title={Comparison of Sine-Cosine and Bat Algorithm for Distributed Generation Placement},
  author={Yustika, Lindiasari Martha and Raharjo, Jangkung and Ikhsan, Rifki Rahman Nur and Wijaya, I.G.P.O. Indra},
  journal={Jurnal Nasional Teknik Elektro dan Teknologi Informasi},
  year={2025},
  doi={10.22146/v14i3.19191}
}
```

---

## 🔗 DOI (Zenodo)

After creating a GitHub release, Zenodo will automatically generate a DOI for this repository.

---

## 📜 License

Creative Commons Attribution 4.0 International (CC BY 4.0)

---

## 🙌 Acknowledgements

This work is based on research in power distribution systems, optimal DG placement, and nature-inspired metaheuristic optimization.

---

## ⭐ Support

If you find this repository useful:
- ⭐ Star this repo
- 🍴 Fork and contribute
- 📢 Share with the research community
