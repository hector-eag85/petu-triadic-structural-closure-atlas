# RUN_ORDER

## Recommended reproduction sequence

This file gives a recommended sequence for inspecting and attempting to reproduce the PETU public release.

## Step 1: Review public records

Review the three public DOI records:

* Preprint DOI: https://doi.org/10.5281/zenodo.20821557
* Data/Code DOI: https://doi.org/10.5281/zenodo.20820252
* Formal mathematical companion DOI: https://doi.org/10.5281/zenodo.20859713

Review the GitHub repository:

https://github.com/hector-eag85/petu-triadic-structural-closure-atlas

## Step 2: Review availability documentation

Review:

* `DATA_AVAILABILITY.md`
* `CODE_AVAILABILITY.md`
* `PUBLIC_RELEASE_LINKS.md`
* `DOI_RECORDS_MAP.md`
* `ZENODO_METADATA_VERIFICATION_v1.md`

## Step 3: Review manuscript-facing materials

Review:

* main manuscript
* Supplementary Information
* Supplementary Tables
* main figures
* extended data figures
* figure source tables

## Step 4: Prepare environment

Install the required environment from the available dependency files, where applicable:

* `requirements.txt`
* `environment.yml`

If both are present, use the environment file that best matches the script being re-run.

## Step 5: Retrieve public datasets

Use the data-source documentation and script headers to retrieve the original public datasets where raw data are not redistributed.

Raw data are redistributed only where permitted by the original data-source license, archive policy, or access rules.

## Step 6: Run domain scripts

Run domain scripts in `scripts/` where available.

Recommended order:

1. micro-domain scripts
2. meso-domain scripts
3. macro-domain scripts
4. independent tier-1 validation scripts
5. figure-generation scripts
6. audit/check scripts

## Step 7: Verify outputs

Verify or regenerate, where possible:

* Supplementary Tables ST0-ST15
* source tables
* processed outputs
* packaged logs
* main figures
* extended data figures
* checksums

## Step 8: Compare against packaged release

Compare regenerated outputs against the packaged source tables, logs, figures, and audit files.

Expected public-release audit status:

PASS FINAL LOG AUDIT WITH SCOPE NOTE.

The packaged source-table and log audit passed with:

* 272 numerical checks
* 0 numerical failures
* 0 critical placeholder failures

## Scope note

This run order supports independent inspection, reproduction attempts, and critical reanalysis.

The packaged audit verifies consistency across available source tables, logs, manuscript-facing outputs, figures, supplementary materials, and public-release metadata.

The packaged audit does not replace full third-party raw-data re-execution.

Independent re-execution, peer review, external replication, and adversarial testing remain appropriate next steps.

## Claim status

PETU is presented as a candidate cross-domain empirical principle.

This repository does not claim that PETU is a completed universal law, a theory of everything, a metaphysical proof, or a theological proof.

## Status

Status: PASS_FINAL_RUN_ORDER_WITH_SCOPE_NOTE / PASS_FINAL_LOG_AUDIT_WITH_SCOPE_NOTE.

