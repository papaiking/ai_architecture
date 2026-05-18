# Top 5 LLM Fine-Tuning Techniques

## Background

Traditional fine-tuning is impractical for LLMs (billions of params; 100s GB). Since this kind of compute isn't accessible to everyone, parameter-efficient finetuning (PEFT) came into existence.

LLM weights are matrices of numbers adjusted during finetuning. Most PEFT techniques involve finding a lower-rank adaptation of these matrices, a smaller-dimensional matrix that can still represent the information stored in the original.

## Techniques

### 1) LoRA (Low-Rank Adaptation)

- Add two low-rank trainable matrices, A and B, alongside weight matrices.
- Instead of fine-tuning W, adjust the updates in these low-rank matrices.
- Even for the largest of LLMs, LoRA matrices take up a few MBs of memory.

### 2) LoRA-FA (Frozen-A)

While LoRA significantly decreases the total trainable parameters, it requires substantial activation memory to update the low-rank weights.

LoRA-FA freezes matrix A and only updates matrix B.

### 3) VeRA (Vector-based Random Matrix Adaptation)

- In LoRA, low-rank matrices A and B are unique for each layer.
- In VeRA, A and B are frozen, random, and shared across all layers.
- Instead, it learns layer-specific scaling VECTORS (b and d) instead.

### 4) Delta-LoRA

- It tunes the matrix W as well, but not in the traditional way.
- Here, the difference (or delta) between the product of matrices A and B in two consecutive training steps is added to W.

### 5) LoRA+

- In LoRA, both matrices A and B are updated with the same learning rate.
- Authors of LoRA+ found that setting a higher learning rate for matrix B results in better convergence.

---

*Accessed: 2026-05-12*
