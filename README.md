# Vision Transformer (CIFAR-10) + Text-Driven Segmentation (SAM 2)


**Repository contents (required):**
- `q1.ipynb` — Vision Transformer on CIFAR-10 (PyTorch, Colab-ready)
- `q2.ipynb` — Text-driven segmentation using CLIPSeg → SAM 2 (Colab-ready)
- `README.md` — This file


## How to run (Colab)
1. Open the notebook (`q1.ipynb` or `q2.ipynb`) in Google Colab.
2. Runtime → Change runtime type → GPU
3. Run all cells top-to-bottom. Install cells are at the top of each notebook.


---


## Q1 — Vision Transformer on CIFAR-10
**Best config (fill this after experiments):**
- Patch size: 8x8
- Depth (num encoder blocks): 8
- Embedding dim: 384
- Num heads: 6
- Optimizer: AdamW
- LR / scheduler: 3e-4, cosine warmup
- Augmentations: RandomCrop, RandomHorizontalFlip, RandAugment, MixUp
- Epochs: 120


**Results**
| Model | Test accuracy (%) |
|---|---:|
| ViT (starter) | **PLACEHOLDER** |


**Tiny analysis (1–3 paragraphs)**
- Summarize the influence of patch size, depth, augmentations, optimizer choices.
- Note trade-offs between compute and accuracy.


---


## Q2 — Text-driven segmentation (single image)
**Pipeline**
1. Use CLIPSeg (or GroundingDINO) to convert text prompt → region heatmap / box proposals.
2. Convert seeds (points or boxes) to prompts for SAM 2.
3. Run SAM 2 predictor → obtain mask(s) → display overlay.


**Limitations**
- SAM 2 weights may not be publicly available; you may need to use a compatible SAM checkpoint or the open-source Segment Anything implementation.
- Text-to-region step quality determines final mask quality; ambiguous prompts may fail.


---


## Submission
- Ensure repo contains *only* `q1.ipynb`, `q2.ipynb`, `README.md`.
- Submit the best CIFAR-10 test accuracy (%) and repo link via the provided Google Form.
