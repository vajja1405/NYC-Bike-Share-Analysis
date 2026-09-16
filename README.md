# NYC Bike Share Analysis

Exploratory analysis and demand forecasting on **735,502 Citi Bike trips** from New York City,
built as a data-analytics capstone. Tableau for the visual analysis, Python for the modelling.

> **A New Hint to Transportation — Analysis of the NYC Bike Share System**
> SmartBridge Data Analytics final project · VIT · Team-165

---

## The data

| | |
|---|---|
| Trips | **735,502** |
| Period covered | **September 2015 – March 2017** (~18 months) |
| Unique start stations | 51 |
| Unique end stations | 114 |
| Distinct bikes | 677 |
| Mean trip duration | 15.6 minutes |

Fields: trip duration, start and end station, start time, bike ID, user type, gender, birth year.

The combined extract is committed here as `NYC-BikeShare-2015-2017-combined.hyper` (19 MB).

## What's in this repository

| File | What it is |
|---|---|
| `nyc-bikeshare-dashboard.twb` | Tableau workbook — four worksheets and a story |
| `NYC-BikeShare-2015-2017-combined.hyper` | The data extract the workbook reads |
| `NYC-BikeShare-Final-Report.docx` | Full written report — methodology, figures, findings |

## The Tableau workbook

Four worksheets, assembled into one story:

- **Bar** — measure values by end station, to find where trips terminate
- **Bubble** — start station against start time, showing when each station is under load
- **Table** — bike ID against trip duration, for per-bike utilisation
- **Treemap** — trip duration against rider birth year, for age-group behaviour

## Modelling

Four regression algorithms were compared for demand forecasting, evaluated by **RMSLE**
(root mean squared logarithmic error — chosen because demand counts are skewed and RMSLE
penalises under-prediction more evenly across magnitudes than RMSE).

A **tuned Random Forest** performed best of the four.

> **Note on reproducibility:** the comparison is described in the written report, but the
> numeric RMSLE scores were not preserved in this repository. The ranking is documented;
> the exact values are not, so no score is quoted here.

## My contribution

**V Rahul Chowdary (20MID0018)** — one of four team members. My work was on the data
preparation and the Tableau analysis: combining the trip files into a single extract,
cleaning and engineering the fields used for the visual analysis, and building the
worksheets above.

Full team: Kanugo Krishna Ganesh, Yenigandla Venislaus Ashish, V Rahul Chowdary,
Akash Kulkarni.

## Honest notes

- **This is a four-person student project**, not individual work.
- The accompanying Flask component served a **static informational website**, not a
  model-serving API. The original site is at
  [krishnaganesh01.github.io/Analysis-of-the-NYC-bike-share-system](https://krishnaganesh01.github.io/Analysis-of-the-NYC-bike-share-system/).
- The extract covers roughly **eighteen months**, not the full 2015–2017 calendar span the
  filename might suggest.
- The modelling code is not in this repository — what is preserved here is the data
  extract, the Tableau workbook and the written report.

## Opening the workbook

Requires Tableau Desktop or Tableau Public. Open `nyc-bikeshare-dashboard.twb`; it reads the
`.hyper` extract from the same directory, so keep both files together.
