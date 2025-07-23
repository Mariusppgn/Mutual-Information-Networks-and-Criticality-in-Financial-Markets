# Mutual Information Networks and Criticality in Financial Markets

This project explores the propagation of market movements and collective transitions in financial systems by leveraging mutual information as a dependency measure between assets. The approach draws on concepts from statistical physics, including the Binder cumulant, to analyze cascades, network symmetry, and the emergence of critical points analogous to phase transitions.

## Context and Motivation

- **Goal:** Investigate how financial shocks and trends propagate through networks of assets, using mutual information to capture both linear and non-linear dependencies.
- **Novelty:** Go beyond classical correlation analysis by incorporating information-theoretic measures and tools from complex systems physics to detect critical phenomena.

## Theoretical Framework

### 1. Asset Returns

Let \( P_i(t) \) be the price of asset \( i \) at time \( t \). The logarithmic return over a time step \( \Delta t \) is defined as:

$$
r_i(t) = \frac{P_i(t+\Delta t) - P_i(t)}{P_i(t)}
$$

---

### 2. Mutual Information (General Case)

$$
I(X, Y) = \iint p_{XY}(x, y) \log \left( \frac{p_{XY}(x, y)}{p_X(x)p_Y(y)} \right) dx\, dy
$$

where \( p_{XY}(x, y) \) is the joint probability density and \( p_X, p_Y \) are the marginal densities.

#### Gaussian Case

If \( X \) and \( Y \) are jointly Gaussian, the mutual information reduces to:

$$
I(X, Y) = \frac{1}{2} \log \left( \frac{|K_X|\,|K_Y|}{|K_{XY}|} \right)
$$

with \( K_X \), \( K_Y \) being the determinants of the covariance matrices of \( X \) and \( Y \), and \( K_{XY} \) the determinant of their joint covariance matrix.

---

### 3. Shannon Entropy

$$
H(X) = -\sum_x p(x) \log p(x)
$$

---

### 4. Mutual Information Network

- **Nodes:** financial assets
- **Edge weights:** mutual information \( I(X, Y) \) between each pair of assets.
- Optionally, the network can be filtered (e.g., by thresholding or using the minimum spanning tree).

---

### 5. Cascade Size

The cascade size refers to the number of assets significantly affected by a propagated movement or event in the network. The precise definition may depend on the methodology (e.g., cluster activation size during a shock).

---

### 6. Binder Cumulant (Detecting Criticality)

The Binder cumulant, adapted from statistical physics, is used to identify critical transitions:

$$
U = 1 - \frac{\langle M^4 \rangle}{3 \langle M^2 \rangle^2}
$$

where \( M \) is an observable (such as mean cascade size or mean mutual information). The crossing of \( U \) curves for different averaging windows or subsystem sizes may indicate a critical point (phase transition analogue).

---

## Methodology

1. Extract and window financial time series data.
2. Compute mutual information for each pair of assets and compare to the Gaussian case.
3. Construct the mutual information network at each time window.
4. Detect and quantify cascades of market movements.
5. Analyze temporal and spatial evolution of observables: mutual information, entropy, cascade size.
6. Compute the Binder cumulant for varying window sizes.
7. Visualize and interpret the results.

---

## Repository Structure

---

## References

- R. N. Mantegna, "Hierarchical structure in financial markets", *Eur. Phys. J. B* 11, 193–197 (1999)
- Kraskov, Stögbauer, Grassberger, "Estimating mutual information", *Phys. Rev. E* 69, 066138 (2004)
- Bouchaud, J.-P., Potters, M., "Theory of Financial Risk and Derivative Pricing"
- Tumminello et al., "A tool for filtering information in complex systems", *PNAS* 102, 10421 (2005)

---
