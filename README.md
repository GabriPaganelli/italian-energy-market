# Tra Vecchie e Nuove Fonti: Modellazione Econometrica del Mercato Energetico Italiano
# *Econometric Modelling of the Italian Energy Market*

---

## Italiano

### Panoramica

Progetto universitario di analisi delle relazioni dinamiche tra il PUN (Prezzo Unico Nazionale),
il prezzo del gas naturale e la produzione da fonti rinnovabili nel mercato elettrico italiano
nel periodo 2021–2025, nell'ambito del corso di Modelli Statistici per Dati Economici (gennaio 2026).

### Metodologia

L'analisi impiega una suite di modelli di serie storiche:

- **SARIMA** — modellazione univariata del PUN con componente stagionale
- **Transfer Function** — effetto del prezzo del gas sulle variazioni del PUN
- **VECM** (Vector Error Correction Model) — relazioni di cointegrazione di lungo periodo
- **VAR** (Vector Autoregression) — dinamiche di breve periodo tra le tre serie

I dati coprono il periodo 2021–2025 a frequenza settimanale/mensile.

### Struttura del Repository

```
italian-energy-market/
├── README.md
├── LICENSE
├── energy_market_report.pdf   # Report pre-compilato
├── energy_analysis.Rproj      # RStudio project
├── analysis/
│   └── report.Rmd             # Documento principale
├── data/
│   ├── prezzi/                # Prezzi orari PUN (GME, Anno_YYYY_12.xlsx)
│   ├── gas/                   # Prezzi gas MGP (GME, Annotermico_*.xlsx)
│   └── rinnovabili/           # Produzione rinnovabile (Terna, Rinnovabili_YYYY.xlsx)
└── output/                    # PDF rigenerato (non tracciato da git)
```

### Installazione

R ≥ 4.0 e RStudio. Aprire `energy_analysis.Rproj` in RStudio per attivare la
gestione automatica dei path.

```r
install.packages(c("here", "forecast", "dplyr", "readxl", "lubridate",
                   "tidyverse", "vars", "dynlm", "urca", "lmtest",
                   "MTS", "knitr", "kableExtra"))
```

### Esecuzione

```r
# Per compilare il report PDF
rmarkdown::render("analysis/report.Rmd", output_dir = "output")
```

### Risultati

Il report pre-compilato è disponibile in `energy_market_report.pdf` per la visualizzazione diretta.
Nuove compilazioni vengono salvate in `output/report.pdf` (cartella non tracciata da git).

Il report include:
- Analisi di stazionarietà e test di cointegrazione
- Stime e diagnostiche dei modelli SARIMA, Transfer Function, VECM e VAR
- Funzioni di risposta all'impulso (IRF) e decomposizione della varianza
- Interpretazione economica delle relazioni tra le tre serie

### Autori

**Giorgia Caicchiolo, Gabriele Paganelli** — Academic Portfolio
Modelli Statistici per Dati Economici, Università di Padova, gennaio 2026.

**Fonti dei dati:**
- **PUN**: [GME — Dati Storici MGP](https://www.mercatoelettrico.org/it-it/Home/Esiti/Elettricita/MGP/Statistiche/DatiStorici)
- **Gas**: [GME — Dati Storici MGS](https://www.mercatoelettrico.org/en-us/Home/Results/Gas/MGS/StatisticalData/HistoricalData)
- **Rinnovabili**: [Terna — Download Center](https://dati.terna.it/en/download-center#/load/total-load)

---

## English

### Overview

University project analysing the dynamic relationships between the PUN (Italian
National Electricity Price), natural gas prices, and renewable energy production
in the Italian electricity market over the period 2021–2025. Developed for the
Statistical Models for Economic Data course (January 2026).

### Methodology

The analysis employs a suite of time-series models:

- **SARIMA** — univariate modelling of the PUN with seasonal component
- **Transfer Function** — effect of gas prices on PUN fluctuations
- **VECM** (Vector Error Correction Model) — long-run cointegration relationships
- **VAR** (Vector Autoregression) — short-run dynamics among the three series

Data cover the period 2021–2025 at weekly/monthly frequency.

### Repository Structure

```
italian-energy-market/
├── README.md
├── LICENSE
├── energy_market_report.pdf   # Pre-compiled report
├── energy_analysis.Rproj      # RStudio project
├── analysis/
│   └── report.Rmd             # Main document
├── data/
│   ├── prezzi/                # Hourly PUN prices (GME, Anno_YYYY_12.xlsx)
│   ├── gas/                   # Gas spot prices (GME, Annotermico_*.xlsx)
│   └── rinnovabili/           # Renewable production (Terna, Rinnovabili_YYYY.xlsx)
└── output/                    # Regenerated PDF (not tracked by Git)
```

### Installation

R ≥ 4.0 and RStudio. Open `energy_analysis.Rproj` in RStudio to enable
automatic path management.

```r
install.packages(c("here", "forecast", "dplyr", "readxl", "lubridate",
                   "tidyverse", "vars", "dynlm", "urca", "lmtest",
                   "MTS", "knitr", "kableExtra"))
```

### Usage

```r
# Compile the PDF report
rmarkdown::render("analysis/report.Rmd", output_dir = "output")
```

### Results

A pre-compiled report is available at `energy_market_report.pdf` for direct viewing.
New renders are saved to `output/report.pdf` (directory not tracked by git).

The report includes:
- Stationarity analysis and cointegration tests
- Estimation and diagnostics for SARIMA, Transfer Function, VECM, and VAR models
- Impulse response functions (IRF) and variance decomposition
- Economic interpretation of the relationships among the three series

### Author

**Giorgia Caicchiolo, Gabriele Paganelli** — Academic Portfolio
Statistical Models for Economic Data, University of Padova, January 2026.

**Data sources:**
- **PUN**: [GME — Historical MGP Data](https://www.mercatoelettrico.org/it-it/Home/Esiti/Elettricita/MGP/Statistiche/DatiStorici)
- **Gas**: [GME — Historical MGS Data](https://www.mercatoelettrico.org/en-us/Home/Results/Gas/MGS/StatisticalData/HistoricalData)
- **Renewables**: [Terna — Download Center](https://dati.terna.it/en/download-center#/load/total-load)
