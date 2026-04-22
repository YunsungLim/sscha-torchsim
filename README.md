### SSCHA Development Backup

Modification of source files for the [SSCHA](https://www.sscha.eu) (Stochastic Self-Consistent Harmonic Approximation) to implement [torch-sim](https://github.com/TorchSim/torch-sim) and compatibility with [phonopy] (https://github.com/phonopy/phonopy).

#### Modified Files

`cellconstructor/Methods.py`
Crystal structure utility library. Patches include:
- Improved compatibility with recent Phonopy/Phono3py APIs

`cellconstructor/calculators.py`
Calculator interface for energy/force/stress computation. New features:
- **TorchSim integration**: GPU-accelerated batch calculations via PyTorch
- Unified `get_results_batch()` for running many atomic configurations in parallel on GPU

`python-sscha/Ensemble.py`
- Align with `cellconstructor/calculators.py`

These files are meant to **replace** the corresponding files in the installed upstream packages. After installing the upstream packages, copy the modified files to the appropriate locations:
