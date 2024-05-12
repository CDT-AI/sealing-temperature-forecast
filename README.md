# Sealing Temperature Forecast    
A collaboration project for **AI/ML Manufacturing 4.0** use cases in **PT Kalbe Farma, Tbk.**
<p float="left">
  <img src="https://lwfiles.mycourse.app/63eb3286a3d29f4734f29995-public/bfb0de295c11c3a6901f2c5c8c9310f3.png" width="350" />
  <img src="https://indonesiahannovermesse.id/assets/uploads/exhibitors/pt-bintang-toedjoe.png" width="250" /> 
</p>

## Overview
<p float="left">
  <img src="https://github.com/KalbeDigitalLab/sealing-temperature-forecast/blob/bbf55da1f53d1794c493932c04ad137ec3faaf91/trendz/images/default%20model/forecast_VA%20temp.png" width="700" />
</p>

**Sealing Temperature Forecast** is an interdisciplinary project that utilizes advanced data analytics and forecasting models to predict sealing machine temperatures. This project is part of **Kalbe Digital Lab** within the **AI and IoT** team, specifically for the **Bintang Toedjoe** use case in predictive maintenance. 

This repository contains the collective work of several team members integrating models built in Google Colab, analytics from Trendz, and data orchestration via ThingsBoard.

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
<p float="left">
  <img src="https://github.com/KalbeDigitalLab/sealing-temperature-forecast/blob/bbf55da1f53d1794c493932c04ad137ec3faaf91/trendz/images/default%20model/vertical%20bawah%2026-29%20march%20line.png" width="700" />
</p>
Trendz Analytics provides state-of-the-art tools for our time-series prediction tasks. Check out the `trendz/` directory for both custom and default analytics configurations and visualizations.


## Getting Started

To get started with the project:

1. Install Docker and Docker Compose.
2. Follow the setup instructions in the `docs/installation/` directory.
3. Explore the forecasting models in the `models/` directory.
4. Analyze model predictions and visualizations in the `trendz/` directory.

## Acknowledgements

We acknowledge the hard work and contributions from all AI and IoT team members and support from Bintang Toedjoe that made this project possible.
