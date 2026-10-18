# Test data

This folder contains synthetic test data for developing and testing analysis scripts before
submission to the FDPG.

The data were generated from synthetic FHIR test data and processed by the **same pipeline
as the real data** at the Data Integration Centers (DICs):

```
synthetic FHIR data → extraction → pseudonymization → fhir2csv
```

Scripts that run on these files should therefore also run on the real extracts without changes
to the input handling.

> **Note:** The data are entirely synthetic and contain no real patient data. They reproduce the
> structure and format of the real extracts, but not realistic distributions or clinical
> plausibility. Do not interpret results computed on them.

## Things to keep in mind

- **One CSV per module:** Each module of the MII core data set (e.g. Person, Diagnosis,
  Laboratory) is exported to its own CSV file. No data are lost in this step; link the files
  via the pseudonymized patient identifiers.
- **Timestamp formats may differ:** FHIR allows dates of varying precision (e.g. `2024`,
  `2024-05`, `2024-05-17`, `2024-05-17T08:30:00+02:00`). Parse dates robustly and do not assume
  a single format.
- **Multiple rows per patient:** Repeating elements (e.g. several diagnoses or lab values) appear
  as multiple rows. Aggregate deliberately rather than assuming one row per patient.
- **Missing values are expected:** Not every field is filled at every site. Make sure your
  scripts handle empty values without failing.
