# TSA Week 2 — Learning Log

**Student:** Sopheak Phalka
**Dataset:** Phnom Penh monthly precipitation (NASA POWER, PRECTOTCORR_SUM, 2015–2025)
**Source note:** Downloaded CSV contains only YEAR, 12 month columns, and ANN — full NASA metadata (units, exact coordinates, parameter header) is not included. Filename implies ~11.56°N, 104.93°E. Units are presumed mm but must be confirmed against the NASA header.

## Key Observations

- **Coverage:** 132 monthly observations (2015-01 to 2025-12). No missing months, no duplicate dates, no missing values. Monthly sums match the ANN column exactly (max difference = 0.0).
- **Seasonal pattern:** A clear annual cycle exists. Wet season runs roughly May–October; dry season runs November–April. September has the highest monthly mean (227.46), February the lowest (12.19). The gap between them is 215.27 units.
- **Trend:** The time plot does not show a clear long-term increase or decrease across the 11 years — rainfall fluctuates year to year without a strong trend.
- **Variability:** The seasonal plot shows peak size varies a lot between years. Some years have much larger wet-season totals than others.
- **Extreme value:** The largest single monthly value is **June 2020 = 703.62**. This is a genuine outlier in the record, but an unusual value is not automatically an error — natural climate variability can produce extreme months.
- **ACF / seasonality:** Annual cycle is confirmed by the pattern in the plots; wet/dry months are consistent across years.

## Concepts Covered

- Time plot (FPP §2.2)
- Seasonal plot — all years overlaid on Jan–Dec (FPP §2.4)
- Seasonal subseries plot — one mini panel per month with month-mean line (FPP §2.5)
- Reading ACF for evidence of annual seasonality
- Distinguishing "unusual observation" from "measurement error"

## Challenges / What Was Tricky

- Understanding that a **seasonal plot** and a **seasonal subseries plot** answer different questions: one compares years side-by-side on a shared monthly axis, the other shows each month's distribution across years.
- Deciding whether the extreme June 2020 value (703.62) is a real climate anomaly or a data issue. Without full NASA metadata, we can flag it as unusual but cannot claim it is an error.
- Confirming the measurement units. The downloaded CSV does not include the NASA header, so units (mm) are presumed rather than verified.
- Handling the wide-to-long reshape without accidentally treating ANN as a 13th month.

## Limitations

- Source metadata (units, exact coordinates, parameter confirmation) needs independent verification before any publication use.
- Only 11 years of monthly data — limited for long-term trend conclusions.
- These are gridded estimates, not a local rain-gauge measurement.
