# Sealing Temperature Forecast

## Overview

Sealing Temperature Forecast is an interdisciplinary project that utilizes advanced data analytics and forecasting models to predict sealing machine temperatures. This project is part of *Kalbe Digital Lab* within the **AI and IoT** team, specifically for the **Bintang Toedjoe** use case in predictive maintenance. This repository contains the collective work of several team members integrating models built in Google Colab, analytics from Trendz, and data orchestration via ThingsBoard.

## Project Structure

```plaintext
Sealing-Temperature-Forecast/
├── data/                   # Dataset for this project
├── docs/                   # Project documentation and setup guides
│   ├── data-preprocessing/
│   └── installation/
│       ├── thingsboard/
│       └── trendz/
├── models/                 # Forecasting models and their evaluations
└── trendz/                 # Trendz analytics related content
    ├── custom analytics/
    └── default analytics/
```

## Installation

Detailed installation instructions for each component are provided in the `docs` directory. This includes setup for Trendz on Windows using Docker and ThingsBoard installation on Ubuntu using Java.

- [Trendz Analytics Setup on Windows](docs/installation/trendz/Trendz-Installations.md)
- [ThingsBoard Installation on Ubuntu](docs/installation/thingsboard/ThingsBoard-Installation.md)

## Forecasting Models

We employ various forecasting models such as Fourier Transformations, ARIMA, SARIMAX, and Prophet. Each model is located in its respective sub-directory within `models/`.

- [Fourier](models/fourier.ipynb)
- [Prophet](models/prophet.ipynb)
- [SARIMAX](models/sarimax.ipynb)
- [ARIMA](models/arima.ipynb)

## Analytics with Trendz

Trendz Analytics provides state-of-the-art tools for our time-series prediction tasks. Check out the `trendz/` directory for both custom and default analytics configurations and visualizations.

## Getting Started

To get started with the project:

1. Install Docker and Docker Compose.
2. Follow the setup instructions in the `docs/installation/` directory.
3. Explore the forecasting models in the `models/` directory.
4. Analyze model predictions and visualizations in the `trendz/` directory.

## Acknowledgements

We acknowledge the hard work and contributions from all AI and IoT team members and support from Bintang Toedjoe that made this project possible.
