# Dataset Instructions

The `data/` folder is not committed to this repository.
The dataset is downloaded automatically when you run the notebook (Cell 2).
This file explains what gets downloaded and how to do it manually if needed.

---

## Dataset: Brugada-HUCA

| | |
|---|---|
| **Source** | PhysioNet |
| **DOI** | https://doi.org/10.13026/0m2w-dy83 |
| **Version** | 1.0.0 |
| **Size** | ~180 MB |
| **Format** | WFDB (.hea + .dat) |
| **Subjects** | 363 (76 Brugada, 287 Normal) |
| **Leads** | 12-lead ECG |
| **Duration** | 12 seconds per recording |
| **Sampling rate** | 100 Hz |

---

## Option A: Automatic (recommended)

Run the notebook top-to-bottom. Cell 2 handles everything:

```python
import wfdb
wfdb.dl_database('brugada-huca/1.0.0', dl_dir='data/')
```

No PhysioNet account required for this dataset (open access).

---

## Option B: Manual download

1. Go to https://physionet.org/content/brugada-huca/1.0.0/
2. Click **Files** tab
3. Download all files to `data/` in the repo root
4. Folder structure should look like:

```
data/
├── RECORDS
├── ANNOTATORS
├── brugada-huca.csv         # Labels: 0=Normal, 1=Brugada, 2=Brugada
├── 001.hea
├── 001.dat
├── 002.hea
├── 002.dat
└── ...
```

---

## Label Mapping

The dataset uses three numeric labels. This project merges them:

| Original label | Meaning | This project |
|---|---|---|
| 0 | Normal | Negative (0) |
| 1 | Brugada (type A) | Positive (1) |
| 2 | Brugada (type B) | Positive (1) |

---

## Citation (required)

> Cortez, N. C., & Iglesias, D. G. (2026). Brugada-HUCA: 12-Lead ECG Recordings
> for the Study of Brugada Syndrome (version 1.0.0). PhysioNet.
> https://doi.org/10.13026/0m2w-dy83

> Goldberger, A. L., et al. (2000). PhysioBank, PhysioToolkit, and PhysioNet.
> Circulation, 101(23), e215-e220.