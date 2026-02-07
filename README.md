# SDG Project - Environmental Kuznets Curve Analysis

Econometric analysis of the Environmental Kuznets Curve (EKC) across political regimes.

## Description

This research project examines the relationship between economic development (GDP) and CO2 emissions across different types of political regimes (democracies, anocracies, and autocracies). The objective is to determine whether the Environmental Kuznets Curve (the inverted U-shaped relationship between income and pollution) varies according to a country's political system.

## Authors

- Alexandre SAINT
- Keyhan GELAS

## Project Structure

```
SDG Project/
├── EKC-Political-Regimes-Code.Rmd              # Main analysis (R Markdown)
├── SDG_Project___Alexandre_et_Keyhan.pdf  # Results document
├── Data/
│   ├── POLITY5_PRC_POLITY2.csv        # Political regime data
│   └── world_development_indicators.xlsx  # World Bank indicators
└── README.md
```

## Data Sources

### POLITY5 (Polity Database)
- **Source**: World Bank Data360 / Polity Database
- **Coverage**: 1800-present
- **Measure**: Revised Combined Polity Score (-10 to +10)
- **Regime Classification**:
  - Democracy: score 6 to 10
  - Anocracy: score -5 to 5
  - Autocracy: score -10 to -6

### World Development Indicators (World Bank)
Analyzed indicators:
- CO2 emissions (metric tons per capita)
- GDP (log-transformed)
- Renewable energy (% of total energy)
- Oil consumption
- Industrial value (% of GDP)
- Urban population (% of total population)
- Rule of law index
- Corruption perception index

## Methodology

### Analysis Period
2000-2018 (19 years)

### Econometric Approach
1. **Fixed effects (FE) panel regression**
2. **Random effects (RE) panel regression**
3. **Specification tests**:
   - Hausman test (FE vs RE)
   - Wald test (differences between regimes)
   - Breusch-Pagan test (heteroscedasticity)
   - Breusch-Godfrey test (autocorrelation)
   - Jarque-Bera test (residual normality)
4. **Robust standard errors** (Arellano, SCC)

## Requirements

### R and Required Packages

```r
install.packages(c(
  "tidyverse",
  "plm",
  "lmtest",
  "sandwich",
  "tseries",
  "WDI",
  "readxl",
  "writexl",
  "skimr",
  "naniar",
  "broom",
  "stargazer",
  "GGally",
  "ggplot2",
  "here",
  "knitr",
  "kableExtra",
  "formatR",
  "gridExtra",
  "car"
))
```

## Usage

1. Clone the repository
2. Open `EKC-Political-Regimes-Code.Rmd` in RStudio
3. Ensure the data files are present in the `Data/` folder
4. Run the R Markdown document (Knit to HTML)

## Results

The analysis results are available in the generated PDF file. The study examines:
- The CO2-GDP relationship by political regime type
- The moderating effect of rule of law, renewable energy, and industrialization
- The existence and shape of the EKC curve across political systems

## License

Academic project - Educational use
