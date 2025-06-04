# Symmetry Detection in 3D Volumes

This repository contains the main implementation of my master's thesis project, focused on detecting and quantifying **point-group symmetries** in 3D volumes using the **spectral analysis of spatial correlations**.

The code builds on and extends the [ASPIRE](https://github.com/ComputationalCryoEM/ASPIRE-Python) library (v0.12.1), and supports experiments on both synthetic volumes and real molecular structures with simulated Cryo-EM projections.

---

## 👩🏻‍🏫 Summary

We compute **auto-correlations** of a 3D volume in the Fourier-Bessel basis and compare them to **image-based correlations** derived from 2D projections.

The core idea is to detect point-group symmetries by identifying consistent patterns in projection-based correlation structures.

For full mathematical details and definitions, see the [📄 thesis.pdf](./thesis.pdf).

---

## 📓 Notebook

To preview the results without running the code, open `TestComplement.ipynb` directly on GitHub. It includes annotated figures and example outputs from the thesis.

---

##  Repository Structure

- `symmetry_detection.py` – Core tools for symmetry detection.
- `TestComplement.ipynb` – Examples and plots from the thesis, viewable on GitHub.
- `image_ac_auxiliary.py` – Helpers for Bessel transforms and image-based correlations.
- `new_ffb_3d.py` – Modified 3D Fourier-Bessel basis (from ASPIRE).
- `Blk_matrices_maker.py` – Generates the B-matrix dictionary.
- `set_up.py` – 
  - Builds `saved_dictionary_matricesB.pkl`
  - Downloads sample volumes from [rcsb.org](https://rcsb.org)
- `saved_dictionary_matricesB.pkl` – Precomputed B<sub>kl</sub> matrices.
- `vols/` – Folder for downloaded volume files.
- `thesis.pdf` – Contains the full theoretical background.

---

##  Setup & Requirements

Install dependencies:

```bash
pip install -r requirements.txt
```

Install ASPIRE:

``` bash
pip install git+https://github.com/ComputationalCryoEM/ASPIRE-Python.git@v0.12.1
```

Then run:

``` bash
python set_up.py
```
This creates the required matrices and downloads sample volume data.


