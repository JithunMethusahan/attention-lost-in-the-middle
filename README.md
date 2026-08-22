# Attention Mechanism Type and Lost-in-the-Middle in Small Language Models

Code and results for our controlled needle-in-a-haystack study testing whether 
attention mechanism type (MHA, GQA, SWA) predicts lost-in-the-middle severity 
in sub-billion-parameter language models. Submitted to GlobalSouthAI @ NeurIPS 2026.

## What we found
Sliding-window attention (Gemma 3 270M) showed complete middle-position 
retrieval failure (0% accuracy) at every tested length (4K–16K tokens), while 
multi-head attention (Qwen1.5-0.5B) and grouped-query attention (Qwen2.5-0.5B) 
showed no measurable failure through 8K tokens, the limit of our available 
compute.

## What's real vs. discussed
All numbers in `/results` and reported in the paper are directly measured. 
The paper's Discussion section also reasons about expected trends beyond our 
tested range (16K–32K) — this is architectural reasoning, clearly labeled as 
such in the paper, not additional measured data.

## Repo structure
- `notebooks/` — evaluation code (Colab/Kaggle)
- `results/` — raw result CSVs per model
- `figures/` — result plots
- `paper/` — submission PDF and LaTeX source

## Reproducing
See `notebooks/` — each is self-contained, requires a GPU (tested on free-tier T4).

## License
Code: MIT. Data in `/results`: CC-BY-4.0. See `LICENSE`.
