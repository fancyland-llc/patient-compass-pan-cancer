# The Patient Compass

**Domain Walls, Oxygen Gating, and the 3-D Survival Manifold of 198,862 Tumors**

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19561701.svg)](https://doi.org/10.5281/zenodo.19561701)

## Overview

Somatic mutation data from 198,862 tumors across 378 independent studies (cBioPortal) were mapped to the eight hallmarks of cancer using a 48-gene panel. A pair-completeness hypothesis was systematically tested, extended, and ultimately falsified as a survival framework. Three findings survived the falsification cascade:

1. **Domain walls predict survival.** Re-projecting the 8-bit hallmark vector into domain-wall coordinates yields the dominant survival features. The frustrated proliferation phenotype (proliferative signaling without invasion) is the single strongest hallmark-derived predictor (HR ≈ 1.61 in hypoxic tissue at p < 10⁻¹⁰⁰). PS3 resolved growth suppression and death evasion increase hazard by 32%; hypoxic causing (simultaneous immortality and metabolism), a massively protective (HR ≈ 0.40).
2. **Tissue oxygenation gates all hallmark effects.** Oxygenation is the strongest independent survival predictor in the multivariate Cox model. The survival effect of Genome Instability inverts by oxygenation: harmful in normoxic tissue, protective in hypoxic tissue.
3. **Eight hallmarks collapse to three dimensions.** A random-matrix analysis finds exactly 3 eigenvalues above the noise threshold. A 3-coordinate score captures 98.5% of the predictive power of the full 36-parameter interaction model with zero meaningful overfitting.

## Repository Structure

```
paper/
  PATIENT_COMPASS.md     ← Full paper (markdown)
  PATIENT_COMPASS.pdf    ← Preprint PDF
  PATIENT_COMPASS.tex    ← LaTeX source (pandoc-generated)
  header.tex             ← pandoc build helper
scripts/
  compass_reproduce.py   ← Reproduction script (lifelines Cox model)
  patient_compass_validate.js  ← Validation test suite (21,308 assertions)
demo/
  patient_compass.html   ← Interactive bilingual (EN/ES) compass report
data/                    ← Reserved for supplementary data
```

## Reproducing the Cox Model

Requires **Python ≥ 3.10** and **lifelines ≥ 0.30**.

```bash
pip install lifelines numpy
python scripts/compass_reproduce.py
```

The script fits the 12-covariate Cox model (8 wall features + O₂_high + O₂_low + 2 interaction terms) on the 48,675-patient subset and verifies all 10 coefficients match the paper to 6 decimal places.

## Running the Validation Suite

Requires **Node.js ≥ 18**.

```bash
node scripts/patient_compass_validate.js
```

Runs 21,308 assertions against the embedded study data, checking gene-to-hallmark mappings, survival statistics, and domain-wall arithmetic.

## Interactive Demo

Open `demo/patient_compass.html` in any modern browser. No server or installation required. The demo renders all findings as a bilingual clinical report. It contains no patient-identifiable information.

## Companion Papers

- **Active Transport on the Prime Gas** — DOI: [10.5281/zenodo.19243268](https://doi.org/10.5281/zenodo.19243268)
- **The Arithmetic Black Hole** — DOI: [10.5281/zenodo.19443006](https://doi.org/10.5281/zenodo.19443006)
- **The Unity Clock** — DOI: [10.5281/zenodo.19478727](https://doi.org/10.5281/zenodo.19478727)

## Citation

```bibtex
@article{matos2026patientcompass,
  title   = {The Patient Compass: Domain Walls, Oxygen Gating, and the
             3-D Survival Manifold of 198,862 Tumors},
  author  = {Matos, Antonio P.},
  year    = {2026},
  doi     = {10.5281/zenodo.19561701},
  note    = {Preprint v1.0}
}
```

## License

Code: [MIT](LICENSE)  
Paper: [CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/) (via [Zenodo](https://doi.org/10.5281/zenodo.19561701))

---

*Fancyland LLC — Lattice OS research infrastructure.*
