# Commute Times: Snow Emergency RDD

This project analyzes whether a snow emergency system reduced average commute times using a regression discontinuity design (RDD).

## Overview

A city issues a snow emergency whenever snowfall reaches 4 inches in 24 hours. During emergencies, car traffic is restricted to major roads and public transit is free. This project uses RDD to estimate whether that policy reduced commute times during snowy weather.

## Files

- `notebook.Rmd`: R Markdown notebook with the analysis.
- `snow.csv`: Dataset containing snowfall, emergency status, commute time, and date.

## Requirements

You will need the following R packages:

- `ggplot2`
- `dplyr`
- `rdd`

## Setup

Install the required packages if needed:

```r
install.packages("ggplot2")
install.packages("dplyr")
install.packages("rdd")
```

Make sure `snow.csv` is in the same folder as `notebook.Rmd`.

## Usage

1. Open `notebook.Rmd` in RStudio.
2. Run the chunks in order.
3. View the plots and RDD output in the notebook.
4. Interpret the treatment effect at the 4-inch snowfall cutoff.

## Method

This analysis uses a sharp RDD because treatment is assigned directly by the snowfall threshold.

- Forcing variable: `snowfall`
- Cutpoint: `4`
- Treatment: `emergency`
- Outcome: `minutes`

The model estimates the local average treatment effect near the cutoff.

## Interpretation

The project estimates whether snow emergencies lowered commute times near the 4-inch threshold. The estimated effect is local to observations near that cutoff, not all snowfall events.

## Notes

- The bandwidth is selected to focus on observations near the cutoff.
- Plots are used to visually check the discontinuity.
- The results are most valid for snowfall amounts close to the threshold.

## License

Add a license here if needed.
