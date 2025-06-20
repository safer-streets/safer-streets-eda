# Safer Streets EDA

A place for prototyping and exploration. Not intended to be polished or complete in any way, and subject to change without notice

Using data from:

- [police.uk](https://data.police.uk/) bulk downloads/API
- ONS for census geographies (e.g. https://geoportal.statistics.gov.uk/datasets/ons::lower-layer-super-output-areas-december-2021-boundaries-ew-bsc-v4-2/about)
- [Nomisweb](https://www.nomisweb.co.uk/) for demographic data (requires an API key)

## Setup

This repo is *not* a package. Create a venv and install from `requirements.txt`. [uv](https://docs.astral.sh/uv/) is highly recommended for managing the environment, e.g.:

```sh
uv venv --python 3.12
uv pip install -r requirements.txt
```

Set the env var `NOMIS_API_KEY` with your Nomis API key. Ideally put it in a `.env` file.

## Content

Primarily jupyter notebooks:

- [X] `police-api.ipynb`: general exploration and visualisation of the police data for West Yorkshire
- [X] `kde-sampling.ipynb`: spatial crime sampling using KDE
- [X] `poisson-gamma.ipynb`: negative binomial approach in Mohler (2019)
- [X] `nomisweb.ipynb`: adding demographic data
- [X] `lorenz-curve.ipynb`: compute Lorenz curves for different crime types
- [X] `street-network.ipynb`: sampling on a street network
- [X] `area-ranking.ipynb`: looking at temporal variability of spatial rankings for different spatial units
- [ ] `similarity.ipynb`: measuring spatial similarity at different times

## TODO

- Spatial units/scales:
  - [X] MSOA
  - [X] LSOA
  - [X] OA
  - [X] Grid,
  - [X] Hex Grid
  - [X] Street segments
  - [ ] Other spatial geometries

- Spatial sensivity
  - [ ] unit size
  - [ ] unit positioning
  - [ ] Seasonality of **crime concentration**

- Demographics:
  - [ ] Resident population
  - [ ] Workplace population

- Statistical tests
  - [X] Spearman rank correlation
  - [X] Rank-biased ordering... https://towardsdatascience.com/rbo-v-s-kendall-tau-to-compare-ranked-lists-of-items-8776c5182899/
  - [ ] 2d Kolmogorov-Smirnov
  - [ ] SPPT (Malleson 2019)


## Resources

https://geopandas.org/en/stable/docs/user_guide/geometric_manipulations.html