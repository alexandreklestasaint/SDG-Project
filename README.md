# Does democracy favour green growth? The Environmental Kuznets Curve across political regimes

Course project for *Programming with Application to SDGs* (M2 International Economics and Development, Paris Dauphine-PSL, 2025), by Alexandre Saint and Keyhan Gelas.

We test whether the Environmental Kuznets Curve (EKC), the inverted-U relationship between income and CO2 emissions, differs between democracies, anocracies and autocracies.

- **Report:** [`EKC-Political-Regimes-Report.pdf`](EKC-Political-Regimes-Report.pdf)
- **Code and output:** [`EKC-Political-Regimes-Code.Rmd`](EKC-Political-Regimes-Code.Rmd), rendered in [`EKC-Political-Regimes-Code.pdf`](EKC-Political-Regimes-Code.pdf)

## Data

- **World Development Indicators** (World Bank): CO2 emissions per capita, GDP per capita, renewable energy share, industry value added, urban population, rule of law, corruption.
- **Polity V** (revised combined polity score, -10 to +10), used to classify countries as democracies (6 to 10), anocracies (-5 to 5) or autocracies (-10 to -6).

After merging and cleaning, the panel covers 164 countries over 2000-2018 (3,049 observations). Both raw files are in `Data/`.

## Method

- Two-way fixed effects panel regressions of CO2 emissions per capita on GDP per capita and its square, with controls (rule of law, renewable energy, industry), estimated on the full sample and separately for each regime type.
- Random effects estimates and specification tests: Hausman, Wald tests of differences between regimes, Breusch-Pagan, Breusch-Godfrey and Jarque-Bera.
- Driscoll-Kraay and cluster-robust (Arellano) standard errors, and robustness checks on the period and sample.

## Main findings

- An EKC appears in the full sample and among autocracies, but only a few countries, mostly very rich or oil-exporting, actually reach the turning point.
- In democracies and anocracies the relationship is concave, but the turning point lies beyond observed income levels.
- Renewable energy lowers emissions in all regimes. The rule of law lowers emissions in democracies but has the opposite sign in authoritarian contexts.
- After 2015, an EKC emerges more clearly among anocracies, possibly linked to the Paris Agreement.

## Reproducing the analysis

Open `EKC-Political-Regimes-Code.Rmd` in RStudio and knit it to PDF (a LaTeX distribution with XeLaTeX is required). Packages are loaded with `pacman`, and file paths are relative to the project root through `here`. The main packages used are `plm`, `lmtest`, `sandwich`, `tidyverse`, `readxl`, `stargazer` and `kableExtra`.

```
├── Data/
│   ├── POLITY5_PRC_POLITY2.csv
│   └── world_development_indicators.xlsx
├── EKC-Political-Regimes-Code.Rmd
├── EKC-Political-Regimes-Code.pdf
├── EKC-Political-Regimes-Report.pdf
└── README.md
```
