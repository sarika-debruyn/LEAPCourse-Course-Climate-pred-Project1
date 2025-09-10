# **The Many Faces of Hurricanes: The Influence of AMO, ENSO, and Higher-Order Moment Analysis**

## About
Climate Prediction Challenges with Machine Learning course at Columbia University. We analyze how the Atlantic Multidecadal Oscillation (AMO) and El Niño–Southern Oscillation (ENSO) shape hurricane frequency, intensity, and tracks in the North Atlantic (1950–2020). Using higher-order moment (“mass moment”) features of hurricane tracks and K-Means clustering, we uncover distinct storm archetypes and quantify phase-dependent differences. Results indicate AMO warm phases concentrate more frequent and more intense storms, while ENSO modulates yearly activity (La Niña ↑, El Niño ↓).

## Repo Structure

│── README.md

│── project1/

│     └── hurricanes.ipynb   # Full analysis and results

│     └── data/              # Raw and processed data

## Problem & Motivation
Hurricane behavior has shifted under warming: frequency, intensity, and trajectories vary in ways tied to basin-scale climate oscillations. Traditional statistics often miss non-linear, shape-based structure in tracks. We ask: How do AMO/ENSO phases relate to storm intensity distributions and track archetypes?

## Data
- Hurricanes: IBTrACS North Atlantic (1950–2020)
- AMO: Monthly SST anomaly index (smoothed)
- ENSO: Monthly SST anomaly with 5-month rule for El Niño / La Niña / Neutral classification

## Methods

1. Preprocessing
- Clean hurricane records; compute max intensity, track geometry, and phase labels (AMO, ENSO).

2. Higher-Order Moments (Mass Moments)
- Track features: centroid (E[x], E[y]), covariance (Var[x], Var[y], Cov[x,y]), skewness, kurtosis.

3. Clustering
- K-Means on standardized moment vectors; elbow/knee to pick k.
- Compare clusters across AMO warm vs. cold and ENSO (El Niño / La Niña / Neutral).

4. Visualization
- Phase-stratified track maps, category distributions, monthly seasonality, intensity distributions, correlation plots.

## Key Findings (1950–2020)

- AMO Warm > Cold (activity & intensity):
  - Higher annual storm counts in warm phases.
  - Major hurricanes (Cat 3–5) more frequent in warm phases.
  - Peak season (Aug–Oct) activity higher in warm phases.
- ENSO Modulation:
  - El Niño: Fewer Atlantic hurricanes (↑ shear).
  - La Niña: More and often stronger storms (↓ shear).
- Track Archetypes via Moments + Clustering:
  - Linear/short-lived vs. curved/long-lived patterns.
  - Nearshore vs. offshore intensification signatures.
  - Warm AMO phases show more westward, landfall-prone archetypes; La Niña favors longer-lived tracks.

## Limitations & Future Work
- Did not include other drivers (e.g., MJO, NAO, PDO, shear/humidity) due to scope.
- Track-shape features could be enriched with pressure, vorticity, energy dissipation.
- Future: add multi-factor models, seasonal forecasting, and deep learning baselines.
