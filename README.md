# Data for: Energy shocks and financial market resilience: the impact of the Strait of Hormuz crisis on V4 economies

[![DOI](https://zenodo.org/badge/1393386055.svg)](https://doi.org/10.5281/zenodo.23023787)

This repository contains the derived data series used in the article:

> Brożyna, J., Strielkowski, W. *Energy shocks and financial market resilience: the impact of the Strait of Hormuz crisis on V4 economies.* Manuscript submitted to *Humanities and Social Sciences Communications*.

Contact: Jacek Brożyna, PhD, Rzeszów University of Technology, jacek.brozyna@prz.edu.pl

## Contents

| File | Description |
|------|-------------|
| `data/log_returns.csv` | Daily log returns of 18 financial series, 3 January 2025 – 27 March 2026 (318 trading days). Used in the event study and the DCC-GJR-GARCH estimation. |
| `data/cross_section_data.csv` | Country-level structural and macroeconomic variables and cumulative abnormal returns for 7 countries. Used in the cross-sectional vulnerability analysis. |

## 1. `log_returns.csv`

Daily log returns, r_t = 100 × ln(P_t / P_{t−1}), expressed in **percent**. Column `Date` is the trading date (YYYY-MM-DD). Series are aligned on a common trading calendar; one missing value (STOXX600, 3 January 2025) is left blank.

| Column | Instrument | Ticker | Source |
|--------|------------|--------|--------|
| Brent | ICE Brent crude oil, front-month futures (USD/bbl) | BZ=F | Yahoo Finance |
| WTI | NYMEX WTI crude oil, front-month futures (USD/bbl) | CL=F | Yahoo Finance |
| STOXX600 | STOXX Europe 600 | ^STOXX | Yahoo Finance |
| DAX | DAX 40 (Germany) | ^GDAXI | Yahoo Finance |
| CAC40 | CAC 40 (France) | ^FCHI | Yahoo Finance |
| FTSEMIB | FTSE MIB (Italy) | FTSEMIB.MI | Yahoo Finance |
| IBEX35 | IBEX 35 (Spain) | ^IBEX | Yahoo Finance |
| WIG20 | WIG20 (Poland) | WIG20 | Stooq |
| BUX | BUX (Hungary) | ^BUX | Stooq |
| PX | PX (Czech Republic) | ^PX | Stooq |
| OilGas_ETF | Energy Select Sector SPDR Fund | XLE | Yahoo Finance |
| Travel_ETF | U.S. Global Jets ETF | JETS | Yahoo Finance |
| Utilities_ETF | Utilities Select Sector SPDR Fund | XLU | Yahoo Finance |
| VIX | CBOE Volatility Index | ^VIX | Yahoo Finance |
| EURUSD | EUR/USD exchange rate | EURUSD=X | Yahoo Finance |
| EURPLN | EUR/PLN exchange rate | EURPLN=X | Yahoo Finance |
| EURHUF | EUR/HUF exchange rate | EURHUF=X | Yahoo Finance |
| EURCZK | EUR/CZK exchange rate | EURCZK=X | Yahoo Finance |

Raw price levels are not redistributed because of the data providers' terms of use; they can be obtained from the sources listed above using the tickers given.

**Event study design used in the article:** event date 28 February 2026 (onset of the Strait of Hormuz crisis, a Saturday; day 0 is mapped to the nearest trading day, 27 February 2026); estimation window [−250, −30] trading days; event window [−5, +15] trading days relative to the event date.

## 2. `cross_section_data.csv`

One row per country (V4: Poland, Hungary, Czech Republic; LEU4: Germany, France, Italy, Spain).

| Column | Definition | Unit | Source |
|--------|------------|------|--------|
| index | Equity index representing the country | – | – |
| country | Country name | – | – |
| hormuz_share | Share of crude oil imports (by mass) originating from Persian Gulf producers (Iraq, Kuwait, Saudi Arabia, United Arab Emirates, Iran, Qatar, Bahrain), 2024 | fraction (0–1) | Eurostat, `nrg_ti_oil` (crude oil, partner breakdown) |
| fossil_share | Share of fossil fuels (solid fossil fuels, peat, oil shale, oil and petroleum products excl. biofuels, natural gas) in gross available energy, 2024 | fraction (0–1) | Eurostat, `nrg_bal_c` |
| spr_days | Total oil stocks, January 2026 | days of net imports | IEA, *Oil stocks of IEA countries* |
| gas_elec_share | Share of natural gas in gross electricity production, 2024 | fraction (0–1) | Eurostat, `nrg_bal_peh` |
| gdp_pc | GDP per capita, PPP, 2024 | current international $ | IMF, *World Economic Outlook* (`PPPPC`) |
| ca_balance | Current account balance, 2024 | % of GDP | IMF, *World Economic Outlook* (`BCA_NGDPD`) |
| debt_ratio | General government gross debt, 2024 | % of GDP | Eurostat, `gov_10dd_edpt1` |
| CAR | Cumulative abnormal return over the event window [−5, +15] (market model, STOXX Europe 600 benchmark) | % | Authors' calculation from `log_returns.csv` |

`hormuz_share` is an upper-bound proxy: part of Saudi Arabian exports is shipped from Red Sea terminals and part of UAE exports from Fujairah, neither of which transits the Strait of Hormuz. For Germany, imports from the United Arab Emirates are confidential in Eurostat and are therefore not included.

Country-level indicators were re-verified against the official sources listed above at the time of deposit; some values differ from those reported in the submitted manuscript and will be updated in the revised version.

## License

The data in this repository are released under the [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) license.

## Citation

If you use these data, please cite the article above (full reference will be added upon publication) and this dataset:

> Brożyna, J., Strielkowski, W. (2026). *Data for: Energy shocks and financial market resilience: the impact of the Strait of Hormuz crisis on V4 economies* [Data set]. Zenodo. https://doi.org/10.5281/zenodo.23023787

This DOI always resolves to the latest version. To cite a specific version, use its version DOI listed on Zenodo (e.g. v1.0.0: https://doi.org/10.5281/zenodo.23023788).
