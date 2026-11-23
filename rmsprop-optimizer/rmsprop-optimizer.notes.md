**RMSprop (Root Mean Square Propagation)** is **an adaptive learning rate optimization algorithm that adjusts the step size for each parameter based on the magnitude of its recent gradients**.

**How It Works**

- **Tracks recent gradients:** It keeps a running average _s _of the squared gradients using a decay rate (`beta`, usually `0.9`), which forgets older gradients over time.
- **Scales the learning rate:** It divides the learning rate `lr`_ _by the square root of this running average (`sqrt(s + eps)`).
- **Balances updates:** Parameters with large, steep gradients get a **smaller** effective learning rate to prevent overshooting, while parameters with small, flat gradients get a **larger** learning rate to speed up learning.
- **Prevents division by zero:** A tiny constant (`eps`, usually `1e-8`) is added inside the square root for numerical stability.
- **Fixes AdaGrad's flaw:** Unlike AdaGrad—which sums all past squared gradients and eventually shrinks the learning rate to zero—RMSprop uses an exponentially decaying average so learning continues smoothly.