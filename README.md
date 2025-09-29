# Machine Learning From Scratch

Re‑implementing core ML algorithms with minimal dependencies to build deep understanding. Each subproject includes derivations, vectorized NumPy implementations, experiments, and a short write‑up.

> Guiding principle: **first principles, then libraries.** Prove it works with math and tests, then compare to scikit‑learn or PyTorch.

---

## 📦 Repository Structure

```
machine-learning-from-scratch/
  README.md
  CONTRIBUTING.md            # conventions, commit hygiene, PR process
  LICENSE
  docs/
    roadmap.md               # week-by-week plan and links
    references.md            # papers, docs, videos used
    changelog.md
  linear_regression/
    src/
    notebooks/
    figures/
    README.md
  logistic_regression/
    ...
  knn/
    ...
  decision_trees/
    ...
  kmeans_pca/
    ...
  neural_networks/
    ...
```

Each module folder contains:

* `README.md` (problem statement, derivation sketch, how to run, results)
* `src/` (pure NumPy implementation; vectorized; small functions)
* `notebooks/` (derivation walkthroughs and experiments)
* `figures/` (loss curves, decision boundaries, etc.)

---

## ✅ Learning Goals

* Implement classic ML algorithms from scratch (no high-level ML libraries in the core training loop).
* Derive gradients and update rules; explain assumptions and limitations.
* Benchmark against standard libraries and analyze discrepancies.
* Practice clean code, reproducible experiments, and concise documentation.

---

## 🔧 Environment

* Python ≥ 3.12
* Core deps: `numpy`, `matplotlib`, `pandas` (for data loading/EDA only)
* Optional: `scikit-learn` for baselines and datasets

Create and activate a virtual environment, then:

```bash
pip install -r requirements.txt
```

> Each subproject may include a `requirements.txt` specific to its experiments.

---

## 🗺️ Roadmap (12 Weeks)

* **Week 1:** Python foundations + project hygiene (done elsewhere; this repo starts W2)
* **Week 2:** Linear Regression (GD + normal equation)
* **Week 3:** Stats & Probability + KNN
* **Week 4:** Data Cleaning + Logistic Regression
* **Week 5:** Model Evaluation + Decision Trees
* **Week 6:** Ensembles (Bagging/Boosting) – baseline only, scratch for trees remains
* **Week 7:** Unsupervised: k‑Means, PCA
* **Week 8:** Numpy MLP (2‑layer NN)
* **Week 9:** CNN (concepts + minimal PyTorch baseline for comparison)
* **Week 10:** NLP: sentiment baseline + TF‑IDF vs. embeddings
* **Week 11:** Explainability (SHAP/LIME) on tabular baseline
* **Week 12:** Capstone summary + portfolio polish

Details evolve week‑to‑week; see `docs/roadmap.md`.

---

## 📚 Projects Checklist

* [ ] `linear_regression/` — GD, closed form, normalization ablation, sklearn parity
* [ ] `logistic_regression/` — binary classification, decision boundary plots
* [ ] `knn/` — classifier & regressor, KD‑tree optional
* [ ] `decision_trees/` — CART (Gini/Entropy), pruning basics
* [ ] `kmeans_pca/` — k‑Means (elbow, silhouette), PCA from SVD
* [ ] `neural_networks/` — 2‑layer MLP: forward/backprop, activations, loss

Stretch (optional):

* [ ] `svm/` (hinge loss GD) | [ ] `naive_bayes/` | [ ] `gaussian_mixture/`

---

## 🧪 How to Run (per module)

```bash
cd linear_regression
python -m src.train --lr 0.01 --epochs 2000 --normalize
# or run notebooks in notebooks/
```

Common flags:

* `--seed`: reproducibility
* `--normalize`: standardize features using train statistics
* `--plot`: save figures under `figures/`

---

## 📈 Reporting & Artifacts

Each module should produce:

* `figures/loss_curves.png` and key plots relevant to the algorithm
* `README.md` with: objective, derivation highlights, experiments, results, limitations, next steps
* A short comparison table vs. sklearn (metrics and, where applicable, parameters)

---

## 🧭 Code Standards

* Small, pure functions; single responsibility; clear names
* Vectorized NumPy; avoid Python loops over samples
* Docstrings with shapes; type hints
* No side effects in `src/` modules (I/O handled in `train.py` or notebooks)
* Deterministic runs with `seed`

---

## 🧩 Evaluation Rubric (self‑check)

* **Correctness:** math derivation matches implementation; gradients verified on toy examples
* **Clarity:** code is readable; modules cohesive; docstrings present
* **Reproducibility:** environment specified; seeds fixed; notebooks run top‑to‑bottom
* **Analysis:** results interpreted; failure modes discussed
* **Comparisons:** baseline parity within a reasonable tolerance

---

## 🧵 Learning Log

Maintain a running log in `docs/changelog.md` or as weekly entries in the top‑level README:

```
### Week N – Topic
- Learned:
- Decisions made:
- Evidence of working:
- Next micro‑goal:
- Stretch backlog:
```

---

## 📎 References

* Roadmap: roadmap.sh — Machine Learning Roadmap
* Linear Algebra & Calculus: 3Blue1Brown series
* NumPy broadcasting and vectorization guides
* scikit‑learn user guide (for baselines and datasets)

---

## 📜 License

Choose a permissive license (MIT recommended) and include it at the repo root.

---

## 🤝 Contributing

This is a personal learning repo. PRs welcome if they:

* Include a clear problem statement and derivation notes
* Keep core training loops library‑free (except NumPy/Matplotlib)
* Provide a minimal comparison against a standard library
