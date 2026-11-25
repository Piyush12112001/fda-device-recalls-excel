# FDA Medical Device Recalls: Excel Analysis

## Question
Which companies have the most serious (Class I) medical device recalls, and are
serious recalls increasing over time?

## Data
- Source: openFDA device enforcement data (public domain / CC0), downloaded Nov 2026
- 40,481 recall records, 2012-2026, from 15,170 recall events
- Each row is one recall record for one product. Several records can belong to one
  recall event (event_id).

## What I did
1. Loaded the data and kept the 16 columns I needed.
2. Cleaned it (details in the "Cleaning Log" sheet):
   - Turned date text into real dates.
   - Flagged 1 impossible date (year 1930), 14 records classified before they
     started, and 1 record with no classification date. I did not change them.
   - Made a numeric quantity column from messy text, and kept the original.
   - Merged spelling variants of company names (3,011 names down to 2,819).
3. Built pivot tables and charts, and a one-page dashboard.

## Findings
1. Records and events tell different stories. Customed has the most Class I records
   (412), but they come from only 2 events. Baxter has the most Class I events (30),
   then Medline (27) and Smiths Medical (25).
2. Class I recall events grew from 66 in 2022 to 135 in 2025.
3. Class I is 3,680 of 40,481 records (about 9%), from 998 events.

## Limits
- 2012 and 2026 are partial years.
- The data only includes recalls classified from mid-2012.
- Companies were merged for spelling only. Related companies (for example
  Teleflex LLC and Teleflex Medical) are still counted separately.
- The data shows what happened, not why.
- Quantity is the first number found in a text field, so it is approximate. It
  repeats across records of the same event and should not be summed.

## Files
- fda_device_recalls.xlsx: cleaned data, cleaning log, pivot tables, dashboard
- dashboard.png: screenshot of the dashboard

## Tools
Excel (Power Query, formulas, pivot tables, Data Model, charts)
