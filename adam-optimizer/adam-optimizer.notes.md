**Adam (Adaptive Moment Estimation)** trains neural networks by combining **Momentum** (gradient direction) and **RMSProp** (per-parameter step scaling). It tracks running averages of gradients and squared gradients to automatically adapt learning rates for each weight, making it the fast, low-tuning default for Transformers, NLP, and noisy datasets.

**Key Insights**

- **Dual Moments:** Tracks gradient mean (momentum) and squared gradient mean (adaptive scaling).
- **Bias Correction:** Rescales early steps by \(1 - \beta^t\) to fix zero-initialization lag.
- **Scale Invariance:** Normalizes updates so steep and flat slopes move smoothly.
- **Low Tuning:** Defaults (α = 0.001, β₁ = 0.9, β₂ = 0.999) work reliably out of the box.
- **Memory Cost:** Stores two extra state tensors per weight (3× SGD memory).
- **AdamW Upgrade:** Decouples weight decay from adaptive scaling for better generalization.