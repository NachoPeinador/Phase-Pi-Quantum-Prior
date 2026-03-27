# 🌀 Phase-Pi-Quantum-Prior

### Topological Superselection $\mathbb{Z}/6\mathbb{Z}$: Analytical Phase Derivation and Dissipative Stabilization for FTQC Cryptanalysis
[![Read in Spanish](https://img.shields.io/badge/Lang-Leer%20en%20Español-red?style=flat&logoColor=white&color=B31B1B)](https://github.com/NachoPeinador/Phase-Pi-Quantum-Prior/blob/main/README_es.md)
[![Python 3.10+](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.xxxxxxxx.svg)](https://doi.org/10.5281/zenodo.xxxxxxxx)
[![ORCID](https://img.shields.io/badge/ORCID-0009--0008--1822--3452-A6CE39?style=flat&logo=orcid&logoColor=white)](https://orcid.org/0009-0008-1822-3452)
[![X](https://img.shields.io/badge/X-%40todos__lumpen-000000?style=flat&logo=x&logoColor=white)](https://twitter.com/todos_lumpen)
[![Papers](https://img.shields.io/badge/Paper-Read_PDF-B31B1B?style=flat&logo=latex&logoColor=white)](https://github.com/NachoPeinador/Phase-Pi-Quantum-Prior/blob/main/Paper/Topological_Z6Z_Superselection.pdf)

---

## 🎯 TL;DR – The Essentials

### 🔬 **Theoretical Breakthroughs**

* 📐 **Analytical Phase Discovery:** Proof that the optimal initialization phases ($\phi_1, \phi_2$) are not heuristic. $\phi_2 = \pi$ emerges from the unit group isomorphism $(\mathbb{Z}/6\mathbb{Z})^{\times} \cong \mathbb{Z}/2\mathbb{Z}$ acting as a non-commutative Berry Holonomy. 
* 🔄 **Renormalization Group (RG) Origin:** The thermodynamic phase $\phi_1 \approx R_{\text{fund}}/10$ is strictly derived as an infrared fixed point of the Callan-Symanzik beta function, coupled to the Euler-Kronecker invariant.
* ⚡ **Polynomial Complexity:** Exact state preparation via **Matrix Product States (MPS)** with constant topological bond dimension $\chi \le 6$, avoiding the exponential $\mathcal{O}(2^n)$ overhead of arbitrary distributions.
* 🛡️ **Parent Lindbladian & NEE Phase:** Construction of a frustration-free dissipative superoperator with a non-collapsing Liouvillian gap $\Delta = \Omega(1)$. Bounded by the **Modified Logarithmic Sobolev Inequality (MLSI)**, this guarantees strict rapid mixing, proving the system enters a **Non-Ergodic Extended (NEE) phase** that defeats Eigenstate Thermalization (ETH).

### 📊 **Computational Validation (N=60 Qubits)**

* 📉 **Dissipative Area Law:** Under a depolarizing noise rate of $p=0.015$, the MPDO bipartite entropy $S_2$ strictly saturates at $\approx 1.65$ bits, defying the Ergodic Volume Law (30 bits).
* 🧪 **Robustness Plateau:** Sensitivity analysis confirms the NEE phase is structurally stable against gauge fluctuations in the range $\phi_1 \in [0, 0.1]$ rad.
* 🚀 **FTQC Resource Gain:** Structural search space reduction (66.6% purge) enabling a massive reduction in the Toffoli gate pre-factor (**~189 Billion T-gates saved** for RSA-2048). This drastically compresses the space-time volume of **Surface Code** syndrome cycles ($\tau$), relaxing magic state distillation thresholds.

---

## 🔍 Research Overview: Beyond Uniform Superposition

Standard quantum algorithms (e.g., Shor, Grover) initialize registers in a state of maximum ignorance: the uniform superposition $H^{\otimes n}|0\rangle$. While easy to prepare, this forces the oracle to process an exponential volume of arithmetically impossible trajectories, demanding impossible coherence times.

This research introduces the **$\mathbb{Z}/6\mathbb{Z}$ Topological Prior**, a structured Quantum State Preparation (QSP) protocol that injects arithmetic intelligence into the vacuum state. By aligning the quantum amplitude with the modular density of prime numbers, we transform integer factorization from a blind search into a **topologically tuned resonance**, optimized for Noisy Intermediate-Scale Quantum (NISQ) and early Fault-Tolerant (FTQC) hardware.

---

## 🧭 Conceptual Framework

```mermaid
graph TD
    A["Arithmetic Topology<br>Z/6Z Ring"] --> B["Modular Superselection<br>Resonant Channels 1 & 5"]
    C["Group Isomorphism<br>(Z/6Z)× ≅ Z/2Z"] --> D["Non-Commutative Gauge<br>φ₂ = φ₁ + π"]
    E["Information Thermodynamics<br>RG Flow & Vacuum Impedance"] --> F["Infrared Fixed Point<br>φ₁ ≈ R_fund/10"]
    
    B --> H["Topological Prior State<br>|ψ_top⟩"]
    D --> H
    F --> H
    
    H --> NEE["Parent Lindbladian & MLSI<br>NEE Phase (Area Law)"]
    H --> MPS["MPS Compilation<br>χ ≤ 6 | O(poly(n)) Depth"]
    H --> CRYP["Surface Code FTQC<br>Massive T-Count Reduction"]

    style H fill:#f96,stroke:#333,stroke-width:3px
    style NEE fill:#bbf,stroke:#333,stroke-width:2px
    style CRYP fill:#bfb,stroke:#333,stroke-width:2px
````

---

## 📊 Experimental Results & Macroscopic Scaling

The following tables summarize the thermodynamic and computational performance of the $\mathbb{Z}/6\mathbb{Z}$ state under open-system dynamics (Lindblad Master Equation) using **Matrix Product Density Operators (MPDO)** up to $N=60$ qubits:

### 1\. Thermodynamic Resilience (N=60, p=0.015)

| Metric | Modular Prior (NEE Phase) | Uniform Baseline (Ergodic ETH) | Advantage |
| :--- | :--- | :--- | :--- |
| **Bipartite Entanglement ($S_2$)** | **1.6495 bits** | **30.0 bits** | **94.5% Reduction** |
| **Scaling Law** | Area Law ($S \le \log_2 \chi$) | Volume Law ($S \sim N/2$) | Thermal Immunity |
| **Liouvillian Gap ($\Delta$)** | $\Omega(1)$ (Rapid Mixing) | $\to 0$ (Slow Mixing) | Frustration-Free |

### 2\. FTQC Resource Projection (RSA-2048)

| Metric | Classic Shor ($H^{\otimes n}$) | MST Adaptive Strategy | Impact |
| :--- | :--- | :--- | :--- |
| **Search Space Entropy** | 100% (All channels) | 33.3% (Resonant only) | **Zero-Leakage Purge** |
| **Estimated T-Count** | $\sim 2.83 \times 10^{11}$ gates | $\sim 9.45 \times 10^{10}$ gates | **\~1.89e11 Gates Saved** |
| **Hardware Implication** | Deep FTQC Required | Shallow FTQC / Late NISQ | **Threshold Relaxation** |

---

## 🚀 Reproducibility and Computational Lab

The empirical validation suite is divided into three comprehensive Jupyter Notebooks. Each notebook is meticulously designed to prove the theoretical claims of the manuscript through functional code, exact tensor contractions, and thermodynamic simulations.

### 📓 Notebook I: Arithmetic and Thermodynamic Foundations
**File:** [`Arithmetic_and_Thermodynamic_Foundations_of_Z_6Z_Superselection.ipynb`](./Arithmetic_and_Thermodynamic_Foundations_of_Z_6Z_Superselection.ipynb)

This notebook provides the experimental framework and empirical validation for the **$\mathbb{Z}/6\mathbb{Z}$ Topological Prior**. It demonstrates how to break away from the traditional, maximum-entropy uniform superposition (used in algorithms like Shor's) by confining the quantum amplitude strictly to resonant arithmetic channels.

**Key Validations & Discoveries:**
* **Arithmetic Confinement (Zero-Leakage):** Proves that **100%** of prime numbers $p > 3$ reside exclusively in the $1 \pmod 6$ and $5 \pmod 6$ congruence classes, completely nullifying amplitudes in sterile channels ($0, 2, 3, 4$).
* **Informational Impedance ($R_{\text{fund}}$):** Derives and validates the thermodynamic constants governing the mapping of ternary arithmetic topology onto binary qubits. To isolate channel 1 with **99.98%** fidelity, the system strictly requires the phase $\phi_1 \approx R_{\text{fund}}/10$.
* **Dual Phase Optimum & Isomorphic Transfer:** Demonstrates that absolute isolation for class 5 is achieved at $\phi_2 = \pi$. Transitioning between channels requires no system recalibration, only the injection of this pure geometric phase, confirming the multiplicative inverse duality ($5 \equiv -1 \pmod 6$).
* **Discrete Symmetry and Modular Parity:** Numerically validates the $\pi$-periodicity of the partition function $Z(\phi)$ and the exact duality $P_1(\phi) = P_5(\phi+\pi)$. The preservation of the modular parity invariant $\langle \hat{P} \rangle$ ensures holonomic rotations are fundamentally stable and entropy-free.

**Conclusion:** This framework enables quantum state preparation using **Matrix Product States (MPS)** with a bounded bond dimension ($\chi \le 6$). This strictly evades the $\mathcal{O}(2^n)$ exponential depth limit and protects the system from decoherence via the Non-Ergodic Extended (NEE) Phase.

---

### 📓 Notebook II: The NISQ Hardware Challenge and MPS Compression
**File:** [`The_NISQ_Hardware_Challenge_and_MPS_Compression.ipynb`](./The_NISQ_Hardware_Challenge_and_MPS_Compression.ipynb)

In this notebook, we transition from abstract mathematics to **Quantum Hardware Engineering**. We demonstrate that the $\mathbb{Z}/6\mathbb{Z}$ Topological Prior is not merely a theoretical construct, but a valid, unitary quantum state vector that can be encoded into the density matrix of a real-world quantum computer, overcoming the historical exponential circuit depth $\mathcal{O}(2^n)$ typically required for sparse state preparation.

**Key Validations & Discoveries:**
* **Perfect Unitarity & Zero-Leakage (via Qiskit):** Proves that the exact phases $\phi_1 = R_{\text{fund}}/10$ and $\phi_2 = \pi$ generate a physically valid quantum state that perfectly nullifies amplitudes in sterile channels, strictly bounding entanglement complexity.
* **The Path to MPS Compression:** Demonstrates that the superselection rules act as a 6-state finite automaton. This allows the state to be compiled using **Matrix Product States (MPS)** with a maximum bond dimension $\chi \le 6$, guaranteeing an efficient polynomial circuit depth $\mathcal{O}(\text{poly}(n))$.
* **Steady-State Uniqueness ($\lambda_0 = 0$):** Through exact spectral analysis, we confirm that the dominant eigenvalue is exactly zero, proving the MPS state is the unique "dark state" of the Parent Lindbladian.
* **Macroscopic Protection & Rapid Mixing ($\Delta = \Omega(1)$):** Shows that the Liouvillian spectral gap does not collapse in the thermodynamic limit ($N \to \infty$). Instead, the topological penalty scales additively ($\Delta \propto N$), guaranteeing ultra-fast relaxation into the protected subspace and evading the Eigenstate Thermalization Hypothesis (ETH).

**Conclusion:** The $\mathbb{Z}/6\mathbb{Z}$ topological subspace acts as a strictly stable, frustration-free dissipative attractor. The Non-Ergodic Extended (NEE) phase is not a pre-thermal transient or a finite-size artifact, but an asymptotic macroscopic reality that mathematically protects the hardware from decoherence.

---

### 📓 Notebook III: Hybrid Cryptanalysis and Optimal Adaptive Strategy
**File:** [`Hybrid_Cryptanalysis_and_Optimal_Adaptive_Strategy.ipynb`](./Hybrid_Cryptanalysis_and_Optimal_Adaptive_Strategy.ipynb)

In this final notebook, we translate our thermodynamic and hardware-level discoveries into the domain of **Applied Cryptanalysis**. We simulate the orthogonal partitioning of the Hilbert space against target cryptographic moduli (e.g., RSA), rigorously quantifying the net reduction in oracle evaluations compared to the maximum-entropy initialization of standard Shor's algorithm.

**Key Validations & Discoveries:**
* **The Optimal Adaptive Strategy:** Validates a fault-tolerant, two-round search protocol exploiting chiral inversion symmetry and the modular parity invariant ($\langle \hat{P} \rangle$). Round 1 injects $\phi_1 \approx R_{\text{fund}}/10$ to collapse amplitude onto channel $1 \pmod 6$. If unsuccessful, Round 2 applies a holonomic rotation $\Delta\phi = \pi$ to integrally transfer the probability mass to channel $5 \pmod 6$ with **zero algorithmic leakage**.
* **FTQC Resource Compression:** Proves that purging 66.66% of sterile search trajectories *before* the first oracle call directly reduces the polynomial pre-factor of the search algorithm by 2/3.
* **Massive T-Count Reduction (RSA-2048):** Projects the strategy onto a macroscopic RSA-2048 modulus. While standard Shor initialization demands $\sim 2.83 \times 10^{11}$ T-gates, the Modular Search Strategy (MST) circumvents roughly **189 billion** of these highly expensive operations.
* **Coherence Threshold Relaxation:** Demonstrates that the drastic reduction in logical depth significantly lowers the required gate fidelity and extends the effective coherence time needed for a successful factorization.

**Conclusion:** The MST strategy transcends a mere mathematical speedup. It provides a thermodynamic and structural "shortcut" that depressurizes error correction thresholds, making Shor's algorithm feasible on Fault-Tolerant Quantum Computing (FTQC) hardware with significantly higher noise floors than previously estimated.

---

## 📂 Repository Structure

\<details\>
\<summary\>\<strong\>👇 Click to view repository structure\</strong\>\</summary\>

```text
.
├── 📂 docs/               # Theoretical Documentation
│   ├── 📄 Phase_Pi_Gold.pdf # The definitive peer-reviewed manuscript
│   └── 📝 Phase_Pi_Gold.tex # LaTeX source
│
├── 📂 notebooks/          # Experimental Validation Suites
│   ├── 📓 01_Geometric_Phase_Validation.ipynb
│   ├── 📓 02_MPDO_Lindblad_NEE_Scaling.ipynb
│   └── 📓 03_FTQC_Cryptanalysis_TCount.ipynb
│
├── 📜 LICENSE             # Dual scheme: Apache 2.0 / CC-BY 4.0
└── 📜 CITATION.cff        # Academic citation metadata
```

\</details\>

---

## ⚖️ Licensing & Citation

This project utilizes a **dual-licensing scheme**:

  * **Code and Algorithms:** [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).
  * **Theoretical Content & Manuscript:** [Creative Commons Attribution 4.0 International (CC-BY-4.0)](https://creativecommons.org/licenses/by/4.0/).

**BibTeX Citation:**

```bibtex
@software{Peinador_Phase_Pi_2026,
  author = {Peinador Sala, José Ignacio},
  title = {El Origen Analítico de la Fase π: Simetría, Dualidad y Preparación de Estados en la Superselección Topológica Z/6Z},
  url = {[https://github.com/NachoPeinador/Phase-Pi-Quantum-Prior](https://github.com/NachoPeinador/Phase-Pi-Quantum-Prior)},
  year = {2026},
  doi = {10.5281/zenodo.xxxxxxxx}
}
```

---

## 🔭 Philosophical Context

> *"The analytical phase is not an adjustment; it is the geometric penalty for trying to squeeze the continuous vacuum into a discrete binary register."*

This work establishes that arithmetic is not a random sequence, but a **deterministic wave structure** encoded in the $\mathbb{Z}/6\mathbb{Z}$ topology. Recognizing this allows us to fundamentally rewrite the rules of quantum cryptanalysis and hardware initialization for the FTQC era.

---

\<div align="center"\>

**Last Update:** March 2026 | **Status:** Gold Version | Built with ⚛️ & 🐍

\</div\>

