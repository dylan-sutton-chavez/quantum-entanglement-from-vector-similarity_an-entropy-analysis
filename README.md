## Quantum Entanglement from Vector Similarity: An Entropy Analysis

A 34-qubit quantum simulation in Python that derives entangled states from classical vector similarity, analysed through Shannon entropy and IPR under a realistic IBM Heron noise model.

## Structure

```
main.ipynb
logs.txt
```

## Model

Random vector pairs (uniform distribution in $[0, 1)^{1024}$) are compared via dot product. Their similarity is mapped to a rotation angle that encodes a single-qubit state on the Bloch sphere:

$$
\theta = (\vec{u} \cdot \vec{v})(\pi - \delta), \quad \delta \sim \mathcal{U}(0.075,\ 0.75)
$$

$$
|\psi\rangle = \cos\!\left(\tfrac{\theta}{2}\right)|0\rangle + \sin\!\left(\tfrac{\theta}{2}\right)|1\rangle
$$

Each of the 17 vector pairs produces a two-qubit state (via Kronecker product), yielding a composite 34-qubit system in ℋ₁ ⊗ ⋯ ⊗ ℋ₃₄. Intra-pair CNOT gates introduce explicit entanglement between each qubit pair.

## Simulation

The circuit is transpiled and run on a noisy `AerSimulator` configured with a 156-qubit `GenericBackendV2` backend (IBM Heron topology), using the matrix product state method over 1,048,576 shots.

## Results

| Metric | Value |
|---|---|
| Shannon entropy | H ≈ 15.71 bits |
| Max. possible entropy | 34 bits |
| Unique states observed | 261,661 |
| Inverse Participation Ratio (IPR) | 1.2 × 10⁻⁴ |

The low IPR and near-uniform state distribution indicate the system operates in a high-dispersion regime with no localization. Information becomes extensively delocalized after wavefunction collapse — the system behaves as a robust entropy generator rather than exhibiting stability islands.

## Runtime

*21 min. CPU: 64 cores (≈62.5% peak, sustained ≈40 cores). RAM: 256 GiB (≈1.95% usage, ≈5 GiB). Network: peak egress ≈391 KB/s. GPU: n/a.*

## Usage

```bash
jupyter notebook main.ipynb
```

## Requirements

```txt
qiskit
qiskit-aer
numpy
```
