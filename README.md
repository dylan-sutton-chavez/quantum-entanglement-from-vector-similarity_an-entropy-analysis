### Quantum Entanglement from Vector Similarity: An Entropy-analysis

Date: February 10th, 2026.

*Runtime: 21 min. CPU: 64 cores (≈62.5% peak usage, sustained ≈40 cores). RAM: 256 GiB (≈1.95% usage, ≈5 GiB). Network: peak egress ≈391 KB/s. GPU: n/a.*

---

The dynamics of complexity and the distribution of information were analyzed in a 34-logical-qubit quantum system, generated from the projection of classical correlations. A model was implemented that maps the geometric similarity between pairs of random vectors (uniform distribution in [0, 1)¹⁰²⁴) to probability amplitudes. This mapping uses a parameterized rotation defined by θ = (u · v)(π - δ) where δ introduces a uniform stochastic modulation (δ ∈ [0.075, 0.75]), encoding the qubit state as |ψ⟩ = cos(θ/2) |0⟩ + sin(θ/2) |1⟩.

The system architecture is structured into 17 disjoint pairs, where entanglement is explicitly induced through intra-pair CNOT gates, evolving in a composite Hilbert space of 2³⁴ dimensions (ℋ₁ ⊗ ⋯ ⊗ ℋ₃₄). To simulate realistic experimental conditions, a noise model based on the IBM Heron backend topology (via Qiskit Aer) was integrated, adding decoherence and gate errors to the intrinsic parametric uncertainty.

Analysis of the final wavefunction, performed through statistical sampling of 1.04 × 10⁶ shots, revealed a high-dispersion regime with a Shannon entropy of H ≈ 15.71 bits and an Inverse Participation Ratio (IPR) of 1.2 × 10⁻⁴, with 261,661 unique states observed. The absence of high IPR values suggests that the system does not exhibit localization (*"stability islands"*), behaving predominantly as a robust entropy generator where information becomes extensively delocalized after wavefunction collapse.

---

Open-sourced software licensed under the MIT license.
