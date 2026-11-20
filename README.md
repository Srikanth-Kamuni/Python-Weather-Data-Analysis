# Weather data analysis with Python

A question-driven exploratory analysis of hourly weather observations using pandas in Visual Studio Code. The project answers 15 questions through data inspection, descriptive statistics, conditional filtering, and grouped summaries.

## Dataset

The supplied CSV contains **8,784 rows and 8 columns**, covering **1 January–31 December 2012**, with one observation per hour. The timestamps are unique and consecutive; no missing values or duplicate rows were found.

| Column | Description | Unit |
| --- | --- | --- |
| Date/Time | Observation timestamp | Timezone unspecified |
| Temp_C | Air temperature | °C |
| Dew Point Temp_C | Dew point temperature | °C |
| Rel Hum_% | Relative humidity | % |
| Wind Speed_km/h | Wind speed | km/h |
| Visibility_km | Visibility | km |
| Press_kPa | Atmospheric pressure | kPa |
| Weather | Recorded weather label | Text |

The notebook renames `Weather` to `Weather Condition` during analysis. Location, original publisher, and dataset licence are not identified in the supplied files. Confirm redistribution rights before publishing the CSV.

## Questions explored

1. Which wind speeds occur in the dataset?
2. How many observations have the exact weather label `Clear`?
3. How many observations have wind speed exactly 4 km/h?
4. Are any values missing?
5. How can the weather column be renamed?
6. What is the mean visibility?
7. What is the sample standard deviation of pressure?
8. What is the sample variance of relative humidity?
9. Which observations record snow, including mixed conditions?
10. When is wind speed above 24 km/h and visibility exactly 25 km?
11. What are the mean numeric measurements for each weather condition?
12. What are the minimum and maximum values by weather condition?
13. Which observations have the exact label `Fog`?
14. When is the weather `Clear` or visibility above 40 km?
15. When is the weather `Clear` with humidity above 50%, or visibility above 40 km?

## Verified results

| Measure | Result |
| --- | ---: |
| Distinct weather labels | 50 |
| Distinct wind speeds | 34 |
| Most frequent label: Mainly Clear | 2,106 observations |
| Exact Clear label | 1,326 observations |
| Exact Snow label | 390 observations |
| Exact Fog label | 150 observations |
| Wind speed exactly 4 km/h | 474 observations |
| Mean visibility | 27.6644 km |
| Sample pressure standard deviation | 0.8440 kPa |
| Sample relative humidity variance | 286.2486 percentage points squared |
| Temperature range | −23.3 to 33.0 °C |

Counts refer to hourly observations, not separate weather events. Exact labels exclude compound labels: `Snow` differs from `Snow,Fog`, and `Clear` differs from `Mainly Clear`.

## Files

- `Weather_datasets.ipynb`: portable copy of the supplied analysis notebook.
- `1. Weather Data.csv`: supplied observations, unchanged.
- `BUILD_GUIDE.md`: step-by-step implementation and GitHub upload guide.
- `requirements.txt`: notebook dependencies.
- `LINKEDIN_POST.md`: ready-to-paste project caption.

## Run locally

Extract the project folder, open a terminal there, and create a virtual environment:

```bash
python -m venv .venv
```

Activate it on Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

Or on macOS/Linux:

```bash
source .venv/bin/activate
```

Install dependencies:

```bash
python -m pip install -r requirements.txt
```

Open the project folder in Visual Studio Code. Install the Microsoft Python and Jupyter extensions, open `Weather_datasets.ipynb`, select the virtual environment through **Select Kernel**, and choose **Run All**. Keep the CSV beside the notebook. The packaged copy replaces the original Windows-specific CSV path with a relative path and clears saved outputs for a fresh run.

## Skills demonstrated

Data profiling, missing-value checks, categorical frequency analysis, Boolean indexing, text matching, descriptive statistics, and group-by aggregation.

## Scope and next steps

This project produces tables and filtered records. It does not currently implement charts, forecasting, a dashboard, or a predictive model. Possible extensions include monthly temperature summaries, weather-frequency charts, and analysis of visibility during fog.

The original notebook leaves timestamps as text; its grouped timestamp minima and maxima therefore compare strings. Use the datetime conversion in the build guide for chronological comparisons. Numeric summaries are unaffected.

## Author

Srikanth Kamuni
