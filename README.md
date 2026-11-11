# Scenario or Model: What Drives Uncertainty in Future Warming?

DSC 106, Project 3 (interactive visualization). Team CCC: Mac Dang, Athena Lin, Gian Cortez, Christopher Nguyen.

An interactive D3.js chart of CMIP6 climate model projections. It compares how much future warming depends on the
emissions scenario versus which climate model you ask.

## Run it locally

The page loads `data/global_tas.csv`, so it needs a local web server (opening the file directly will not work):

```
python3 -m http.server 8000
```

Then open http://localhost:8000

## Files

- `index.html` - the visualization and write-up (D3 v7 loaded from a CDN, no other plotting library)
- `data/global_tas.csv` - annual global-mean temperature anomaly (C, vs each model's 1850-1900 mean), one row per model, scenario and year
- `cmip6_data_prep.ipynb` - the Colab/Jupyter notebook that produced the CSV from the public CMIP6 archive

## Data

CMIP6 monthly near-surface air temperature (`tas`) from the public Google Cloud CMIP6 dataset.
Models: CESM2, CanESM5, GFDL-ESM4, IPSL-CM6A-LR, MPI-ESM1-2-HR (one ensemble member each).
Runs: historical (1850-2014) and the SSP1-2.6, SSP2-4.5 and SSP5-8.5 scenarios (2015-2100).
Monthly values were averaged to annual means with area (cosine-latitude) weights, then converted to anomalies relative
to each model's own 1850-1900 historical mean.
