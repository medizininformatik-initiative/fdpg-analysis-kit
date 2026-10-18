# Test data

This folder contains test data for developing and testing analysis scripts. Once the script runs sufficiently on the test data sets, a pilot dic will be contacted to evaluate the scripts before roll out to all participating sites.

The data were generated from FHIR test data and processed by the **same pipeline
as the real data** at the Data Integration Centers (DICs):

Scripts that run on these files should therefore also run on the real extracts without changes
to the input handling.

> **Note:** The data are entirely artificial and contain no real patient data. They reproduce the
> structure and format of the real extracts, but not realistic distributions or clinical
> plausibility. Do not interpret results computed on them.

> **Also note:** The datasets provided here cover the full spectrum of possible data points.
> The data delivered to a specific research project are minimized and filtered according to the
> specification provided by the researchers. Therefore, not all data points available in the test
> data will be present in the real patient extract. Use your project-specific data definition
> (CRTDL JSON) to map it to the CSV files, or contact the FDPG staff for support.

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
