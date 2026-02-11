### Quantum Entanglement from Vector Similarity: An Entropy-analysis

Date: February 10th, 2026.

*Runtime: 21 min. CPU: 64 cores ($\approx$62.5% peak usage, sustained $\approx$40 cores). RAM: 256 GiB (
$\approx$1.95% usage, $\approx$5 GiB). Network: peak egress $\approx$391 KB/s. GPU: n/a.*

---

The dynamics of complexity and the distribution of information were analyzed in a 34-logical-qubit quantum system, generated from the projection of classical correlations. A model was implemented that maps the geometric similarity between pairs of random vectors (uniform distribution in $[0, 1)^{1024}$) to probability amplitudes. This mapping uses a parameterized rotation defined by $\theta = (\vec{u} \cdot \vec{v})(\pi - \delta)$ where $\delta$ introduces a uniform stochastic modulation ($\delta \in [0.075, 0.75]$), encoding the qubit state as $|\psi\rangle = \cos\left(\frac{\theta}{2}\right) |0\rangle + \sin\left(\frac{\theta}{2}\right) |1\rangle$.

The system architecture is structured into 17 disjoint pairs, where entanglement is explicitly induced through intra-pair CNOT gates, evolving in a composite Hilbert space of $2^{34}$ dimensions ($\mathcal{H}*{1} \otimes \dots \otimes \mathcal{H}*{34}$). To simulate realistic experimental conditions, a noise model based on the IBM Heron backend topology (via Qiskit Aer) was integrated, adding decoherence and gate errors to the intrinsic parametric uncertainty.

Analysis of the final wavefunction, performed through statistical sampling of $1.04 \times 10^6$ shots, revealed a high-dispersion regime with a Shannon entropy of $H \approx 15.71$ bits and an Inverse Participation Ratio (IPR) of $1.2 \times 10^{-4}$, with $261,661$ unique states observed. The absence of high IPR values suggests that the system does not exhibit localization ($\textit{"stability islands"}$), behaving predominantly as a robust entropy generator where information becomes extensively delocalized after wavefunction collapse.

---

Open-sourced software licensed under the MIT license.
