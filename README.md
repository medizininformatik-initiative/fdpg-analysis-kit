# FDPG – Federated Analysis Support Toolkit

Templates, guidelines and standardized test data for federated analyses within the
[German Portal for Medical Research Data (FDPG)](https://forschen-fuer-gesundheit.de)
of the Medical Informatics Initiative (MII).

In federated analyses, the analysis code travels to the data, not the data to the researchers:
scripts are executed locally at the participating Data Integration Centers (DICs), and only
aggregated, non-disclosive results leave the sites. This repository provides everything
researchers and sites need to run such projects in a standardized, traceable and efficient way.

---

## Repository structure

```
fdpg-fast/
├── test-data/      # Standardized synthetic test datasets in the FDPG input format
├── templates/      # Templates for project documentation (README, test report, ...)
├── guidelines/     # Analysis guide, process description and checklists
└── docs/           # Figures and further documentation (e.g. workflow diagram)
```

| Folder | Content | Used in |
|---|---|---|
| `test-data/` | Synthetic datasets that follow the standardized extraction format of the MII core data set. Use them to develop and test your scripts before submission. | Phase 1 |
| `templates/` | Templates for the analysis README and the pilot test report. | C1, C2 |
| `guidelines/` | Analysis guide for researchers, README checklist and the full process description. | All phases |

> **Note:** The test data are entirely synthetic and contain no real patient data. They reproduce
> the structure of the real extracts, not their statistical properties.

---

## Workflow

Every federated analysis project passes through four phases, each completed by a checkpoint
with a defined decision and documentation artefact. The total target duration is approximately
**12 weeks** from the signed data use contract to the delivery of results.

![Federated analysis workflow](docs/federated_process.png)

| Phase | Target duration | What happens | Checkpoint |
|---|---|---|---|
| **1 – Script development** | ~4 weeks | The FDPG recruits a pilot DIC. Researchers develop their analysis scripts using the test data, the analysis guide and the README checklist. The FDPG reviews script and README. | **C1** – Script & README review passed |
| **2 – Pilot validation** | ~2 weeks | The pilot DIC runs the scripts on real data and writes a test report, which the FDPG reviews. | **C2** – Pilot validation report accepted |
| **3 – Rollout & test runs** | ~4 weeks | All participating DICs review and test the scripts locally. The FDPG consolidates the feedback. Site-specific adjustments are made by the respective DIC, supported by the pilot DIC or, if needed, by the researchers. | **C3** – Coordinated release of data output |
| **4 – Data release** | ~2 weeks | The DICs release their results, after a local disclosure check. The DMSt aggregates, prepares and checks the results. | **C4** – Results handed over to researchers |

If a checkpoint is not passed, the scripts go back to the previous step for revision.

### Roles

| Role | Responsibilities |
|---|---|
| **Researchers** | Develop and revise analysis scripts and README. Support site-specific adjustments if the pilot DIC cannot resolve them. |
| **FDPG** | Coordinates the project, recruits the pilot DIC, reviews scripts and test reports, consolidates site feedback and initiates the data release. |
| **Pilot DIC** | Validates the scripts on real data before rollout, writes the test report and supports other sites with adjustments. |
| **Participating DICs** | Review, test and execute the scripts locally, check local results for disclosure risk and release them. |
| **DMSt** | Aggregates, prepares and checks the results before handing them over to the researchers. |

---

## Getting started (for researchers)

1. Read the analysis guide in [`guidelines/`](guidelines/).
2. Develop your analysis scripts against the synthetic data in [`test-data/`](test-data/).
3. Document your analysis using the README template in [`templates/`](templates/).
4. Check your submission against the README checklist in [`guidelines/`](guidelines/).
5. Submit scripts and README to the FDPG. Your project then enters the review at checkpoint C1.

---

## Communication

- **Zulip** is used for direct, day-to-day communication between researchers, FDPG and DICs.
- **GitHub issues** document decisions, identified problems and required adjustments. Each issue
  is assigned to a project and checkpoint, so that the project history stays traceable.

---

## Contributing

Improvements to the templates, guidelines and test data are welcome. Please open an issue to
discuss larger changes before submitting a pull request.

## License

[TODO: add license]

## Citation

If you use this repository, please cite:

> [TODO: add paper reference once published]

## Contact

[TODO: FDPG contact / Zulip stream]
