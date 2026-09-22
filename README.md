# Propeller Optimisation with a Genetic Algorithm

> **Academic coursework deliverable**

This repository contains the practical assignment **“Optimización de un modelo de ingeniería usando un algoritmo genético”**, completed by Sergio Martínez Olivera and Daniel Roldán Serrano. The project applies a custom genetic algorithm (GA) to the black-box optimisation of propeller designs.

## Project overview

The notebook explores how propeller parameters affect simulated thrust, power, efficiency, and blade-tip Mach number. It represents candidate designs as chromosomes, decodes gene values into physical parameters, and evaluates them with alternative fitness functions.

The optimised or evaluated parameters include:

- rotational speed (`omega`)
- forward speed (`vz`)
- propeller radius (`R`)
- blade count (`b`)
- collective pitch (`theta0`)
- torsion and chord-distribution parameters

The notebook compares:

- two mutation strategies
- non-destructive crossover
- alternative fitness functions for cruise and take-off objectives
- different tournament pressures, mutation probabilities, and generation counts

The committed notebook includes executed cells and recorded outputs from these experiments. The reported runs show the expected trade-offs between thrust, power, efficiency, radius, and constraint handling; they are illustrative coursework results, not a benchmark or production optimisation guarantee.

## Repository contents

| Path | Description |
| --- | --- |
| `GASergio_Daniel.ipynb` | Spanish-language coursework notebook containing the explanation, implementation, plots, experiments, and saved outputs |
| `LICENSE` | Repository license |

## Requirements and reproducibility

The notebook uses:

- Python 3
- NumPy
- Matplotlib
- Jupyter Notebook or JupyterLab

The standard-library modules `math` and `random` are also used. No dependency manifest is currently included, so the versions used for the original execution are not recorded.

To open the notebook after installing those general-purpose dependencies:

```bash
jupyter notebook GASergio_Daniel.ipynb
```

### Important: external model dependency

This repository is **not self-contained**. The notebook imports:

```python
from modelo.helice import *
```

The `modelo` package and its `helice` module are not included in this repository. They provide the `calcular_helice` black-box propeller model used by the plots and optimisation runs. As a result, a fresh checkout cannot reproduce the notebook from start to finish without obtaining that external coursework dependency separately.

The notebook also contains an embedded documentation cell describing the expected `calcular_helice` interface and its outputs. That documentation does not replace the missing implementation.

## Method

The implementation uses integer gene values decoded into physically meaningful parameter ranges. A population is evolved through tournament selection, crossover, mutation, and fitness-based survivor selection. The coursework experiments focus on how design choices affect convergence and constraint trade-offs rather than on producing a single universal optimum.

The main fitness experiments include:

- maximising thrust while considering propeller radius
- balancing take-off thrust with power at a specified forward speed
- observing the effect of mutation probability and tournament pressure
- observing the effect of increasing the number of generations

## Scope and limitations

This is an educational notebook and should be read in that context:

- results depend on stochastic initial populations and mutation;
- the external propeller model is unavailable in this repository;
- the notebook does not provide a packaged API, automated test suite, or command-line entry point;
- dependency versions, random seeds, and a complete environment specification were not preserved;
- the saved outputs document representative runs rather than a statistically replicated study.

## Credits

Developed collaboratively by [Sergio Martínez Olivera](https://github.com/sergiio8) and [Daniel Roldán Serrano](https://github.com/danirold) as an academic genetic-algorithms assignment.
