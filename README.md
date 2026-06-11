# 🎨 Color Detection — Dominant Color Analyzer

> Upload any image and instantly detect its dominant colors with percentage breakdown using K-Means clustering.

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)
![Colab](https://img.shields.io/badge/Google%20Colab-Ready-orange?logo=googlecolab&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-KMeans-red?logo=scikit-learn&logoColor=white)

---

## 📸 Sample Output

```
========================================
        DOMINANT COLORS
========================================
darkslategray         : 28.3%  ██████████████
steelblue             : 21.7%  ██████████
goldenrod             : 16.4%  ████████
lightgray             : 14.2%  ███████
peru                  :  9.8%  ████
black                 :  9.6%  ████
========================================
```

---

## ✨ Features

- **Upload any image** — JPG, PNG, WEBP and more
- **K-Means clustering** — ML-powered dominant color detection
- **Human-readable names** — RGB values mapped to CSS3 color names (e.g. `goldenrod`, `steelblue`)
- **Visual palette** — color swatches with names, percentages, and RGB values
- **Segmentation map** — see which region of the image each color came from
- **Runs on Google Colab** — no local setup required

---

## 🚀 Quick Start
1. Open [Google Colab](https://colab.research.google.com)
2. Upload `color_detection.ipynb`
3. Run all cells with **Runtime → Run All**
4. Upload any image when prompted
   
---

## 🛠️ How It Works

```
Image Upload
     │
     ▼
Resize to 200×200       ← speeds up processing ~300x
     │
     ▼
Flatten to pixel list   ← shape: (40000, 3) — each row is [R, G, B]
     │
     ▼
K-Means Clustering      ← groups similar colors into K clusters
     │
     ▼
Count pixels/cluster    ← convert to percentage
     │
     ▼
Map RGB → Color Name    ← nearest CSS3 color via Euclidean distance
     │
     ▼
Print Report + Visualize
```

---

## 📦 Dependencies

| Library | Version | Purpose |
|---|---|---|
| `numpy` | ≥1.21 | Image as pixel arrays |
| `Pillow` | ≥9.0 | Open and process images |
| `scikit-learn` | ≥1.0 | K-Means clustering |
| `matplotlib` | ≥3.5 | Palette visualization |
| `webcolors` | ≥1.12 | RGB → color name mapping |

Install all at once:

```bash
pip install numpy pillow scikit-learn matplotlib webcolors
```

---

## ⚙️ Configuration

In **Step 4** of the notebook, you can tune two parameters:

```python
K = 6      # Number of dominant colors to detect (try 3–10)
N_INIT = 10  # KMeans restarts — higher = more accurate, slower
```

| K value | Best for |
|---|---|
| 3–4 | Broad color summary |
| 6 | Balanced (default) |
| 8–10 | Fine-grained palette |

---

## 🧠 Why K-Means?

K-Means is ideal for color detection because:

- **Unsupervised** — no labeled training data needed
- **Fast** — runs in seconds on 40K pixels
- **Intuitive** — clusters pixels by color similarity in 3D RGB space
- **Controllable** — K lets you decide how many colors to find

---

## 📁 Project Structure

```
color-detection/
│
├── color_detection.ipynb   # Main notebook (all steps with explanations)
└── README.md               # This file
```
