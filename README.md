<h1 align="center">Geometry-Aware Architectural Image Editing</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54" alt="Python" />
  <img src="https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white" alt="PyTorch" />
  <img src="https://img.shields.io/badge/Stable_Diffusion_XL-ff3b71?style=for-the-badge&logo=HuggingFace&logoColor=white" alt="SDXL" />
</p>

> Generative AI pipeline utilizing Stable Diffusion XL (SDXL) combined with dual ControlNets (Depth and MLSD/Canny) and CLIPSeg auto-masking to edit architectural images while rigorously preserving target geometric constraints. 

## 🏗️ Technical Highlights

* **Automated Semantic Masking:** Employs **CLIPSeg** to dynamically generate inference-ready binary masks from simple text prompts, removing the need for manual occlusion generation.
* **Dual ControlNet Integration:** Leverages both structural guides (MLSD/Canny edge maps) and depth constraints (MiDaS normalized maps) fused directly into the SDXL Inpainting pipeline to govern geometric warping.
* **Metric-Driven Results:** Developed custom evaluations, reducing geometric distortion (in structural edge fidelity) by **58.5%** over standard inpainting implementations and improving perceptual LPIPS scores by 26.6%.

---

## 📂 Repository Structure

```text
📦 Geometry-Aware-Image-Editing
 ┣ 📂 notebooks
 ┃ ┣ 📜 01_baseline_mvp.ipynb         # MVP using SD Inpainting and basic masks
 ┃ ┣ 📜 02_mlsd_integration.ipynb     # Injecting MLSD ControlNets for structural consistency
 ┃ ┗ 📜 03_complete_pipeline.ipynb    # Full pipeline: CLIPSeg + Dual ControlNet + SDXL
 ┣ 📂 docs
 ┃ ┣ 📜 Technical_Report.pdf          # Full methodology, metrics, and ablation studies
 ┃ ┗ 📜 research_prompts.txt          # Raw prompt engineering references
 ┣ 📜 .gitignore
 ┗ 📜 README.md
```

## 🚀 Quick Start (Running Notebooks)

1. **Environment Setup:** Ensure you have an environment capable of running transformers, diffusers, and torch (Nvidia GPU strongly recommended).
2. **Launch Jupyter:**
   ```bash
   jupyter notebook notebooks/03_complete_pipeline.ipynb
   ```
3. **Execution:** The notebook handles the dynamic downloading of Hugging Face weights (SDXL, Depth ControlNet, Canny ControlNet, MiDaS, and CLIPSeg) upon execution.

---
*Created by [Muhammad Mahad Khan](https://github.com/Mahad811)*
