# Quantum_protein_folding_exam
# CVaR-VQE — APRLRFY

This notebook implements a hybrid quantum-classical algorithm for protein folding
based on the CVaR-VQE approach described in:

> Robert et al., *Resource-efficient quantum algorithm for protein folding*,
> npj Quantum Information (2021). https://doi.org/10.1038/s41534-021-00368-4

The peptide studied is the 7 amino acid neuropeptide **APRLRFY**.

---

## Structure

The notebook is organization:

1. **Environment setup** — installation of all required libraries
2. **Data encoding** — the protein sequence is encoded into a qubit Hamiltonian
   using [QuPepFold](https://doi.org/10.1371/journal.pone.0342012) and converted
   to a `SparsePauliOp` via Qiskit
3. **CVaR-VQE (baseline)** — the algorithm is run on the full 36-dimensional
   parameter space using `EfficientSU2` ansatz, COBYLA optimizer, and
   `StatevectorSampler` with `aggregation=0.1`
4. **3D structure visualization** — the optimal fold is reconstructed and plotted
5. **PCA on parameter space (original contribution)** — the variational parameter
   space is reduced to 2D and 5D via PCA, and CVaR-VQE is re-run in the reduced
   space to evaluate the trade-off between speed and precision

---

## Requirements

```bash
pip install qupepfold
pip install pylatexenc
pip install qiskit
pip install qiskit-aer
pip install qiskit-algorithms
pip install scikit-learn
pip install matplotlib
pip install numpy
pip install seaborn
```

---

## Notes

- The notebook is designed to run on Google Colab
- The energy values are dimensionless 
- For a detailed description of the methodology and results, see the report
  (to be added)
