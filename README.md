# NetGuardAI

FYP-1 work on network intrusion detection with the GeNIS dataset. This repository currently contains the Module 1 plan and a notebook for data ingestion, exploratory analysis, preprocessing, class balance reporting, and an unaugmented Random Forest baseline.

## Repository contents

- `docs/module1-plan.pdf` — Module 1 project plan and evaluation requirements.
- `notebooks/module1-data-ingestion-preprocessing.ipynb` — Module 1 workflow. The notebook uses GeNIS's official 60-second training CSV to create internal 70/15/15 development splits and leaves the official test CSV separate for later independent evaluation.

## Running the notebook

The notebook is designed for Google Colab or a local Jupyter environment. It downloads the GeNIS preprocessed archive from Zenodo in resumable 8 MB HTTP byte ranges, retries interrupted ranges and temporary HTTP 408/429/5xx responses (honoring numeric `Retry-After` headers), and validates the ZIP before extraction. If a connection fails after the retry limit, rerun the download cell; it resumes from the saved `.part` file. Install the dependencies in the setup cell, then run all cells from top to bottom. Saved notebook outputs have been cleared; rerunning generates fresh charts and metrics.

Do not commit downloaded dataset archives, extracted CSV files, generated charts, credentials, or environment-specific files. Dataset licensing and citation details are in the notebook and source dataset record.

## Current scope

This repository tracks Module 1. Module 2 augmentation comparisons and later dashboard work are planned separately. Results are empirical; no augmentation benefit is assumed in advance.
