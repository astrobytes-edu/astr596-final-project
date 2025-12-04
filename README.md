# Final Project: From Simulation to Surrogate
**ASTR 596: Modeling the Universe**  
**Instructor:** Dr. Anna Rosen  
**Due:** Thursday, December 18, 2025, 11:59 PM

---

## ⚠️ Important Deadline

**This repository will lock automatically at the deadline. No late submissions accepted.**

Your complete submission must include:
- All implementation code (installable package)
- Research memo (PDF or Markdown)
- All required figures
- Scripts that reproduce your results

---

## 📚 Project Documentation

**Refer to the course website for all project requirements and specifications:**

- **[Project Description](https://astrobytes-edu.github.io/astr596-modeling-universe/final-project-nn-emulator-description/)** - Complete requirements, physics background, code skeletons, and rubric

---

## 🗂️ Repository Structure

See the [Project Description](https://astrobytes-edu.github.io/astr596-modeling-universe/final-project-nn-emulator-description/) for the complete required package structure.

Your package should be installable with:
```bash
pip install -e .
```

---

## 🚀 Quick Start

```bash
# Clone your repository
git clone <your-github-classroom-repo-url>
cd astr596-final-project

# Install your package in development mode
pip install -e .

# Generate training data
python scripts/generate_data.py

# Train emulator
python scripts/train_emulator.py

# Run inference
python scripts/run_inference.py
```

---

## 📦 Required Packages

Install these before starting:

```bash
pip install jax jaxlib equinox optax numpyro scipy
```

You'll also need your N-body package from Project 5:
```bash
pip install -e /path/to/your/nbody_package
```

---

## ⚡ Critical: JAX Precision Configuration

**JAX defaults to float32, but N-body simulations require float64.**

Add this to the **top of every module** before any JAX imports:

```python
import jax
jax.config.update("jax_enable_x64", True)
```

Without this, your training data will have poor energy conservation.

---

## 📖 Key Resources

| Package | Documentation | Start Here |
|---------|---------------|------------|
| **Equinox** | [docs.kidger.site/equinox](https://docs.kidger.site/equinox/) | "Getting Started" → "Your first neural network" |
| **Optax** | [optax.readthedocs.io](https://optax.readthedocs.io/) | "Getting Started" |
| **NumPyro** | [num.pyro.ai](https://num.pyro.ai/) | "Getting Started" + "Bayesian Regression" |
| **Latin Hypercube** | [scipy.stats.qmc.LatinHypercube](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.qmc.LatinHypercube.html) | API reference + examples |

### 🎥 Recommended Videos

**[3Blue1Brown: Neural Networks](https://www.youtube.com/playlist?list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi)** — Strongly recommended before starting. Videos 1–4 cover exactly what you need: what NNs are, gradient descent, backpropagation, and how learning works.

---

## ❓ Questions?

- Check the [Project Description](https://astrobytes-edu.github.io/astr596-modeling-universe/final-project-nn-emulator-description/) first for detailed specifications
- Post in the course Slack channel for clarifications
- Attend office hours for implementation help

Good luck with your final project! 🚀
