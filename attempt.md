Assignment 3: Two Averages, One Argument
Descriptive analytics — referee's note
Dataset: teaching_prices_clean(1).csv
Period: 1 January 2026 to 19 March 2026 (12 weekly dates)
Coverage: four illustrative items, two cities, 96 item-city-date observations.
Unit: PKR per kg (illustrative).
1. Statistics
For the item-level table below, I pooled the 12 weekly observations from City 1 and City 2 for each item (24 values per item). The first-to-last percentage change compares the average of the two cities on the first date with their average on the last date.
Item	Mean (PKR/kg)	Median (PKR/kg)	First date avg	Last date avg	First-to-last change (%)	Observations
Oil B	324.83	324	301	347	15.28%	24
Pulse C	205.92	206	203	210.5	3.69%	24
Staple A	111.17	111.75	104	117.5	12.98%	24
Sweetener D	166.75	166.75	152	181.5	19.41%	24


City-level results are included to show that the pooled average does not hide the difference between the two city series:
Item	City	Mean	Median	First	Last	Change (%)
Oil B	City 1	321.83	321	298	344	15.44%
Oil B	City 2	327.83	327	304	350	15.13%
Pulse C	City 1	202.92	202.5	200	207.5	3.75%
Pulse C	City 2	208.92	208.5	206	213.5	3.64%
Staple A	City 1	108.17	107.75	101	114.5	13.37%
Staple A	City 2	114.17	113.75	107	120.5	12.62%
Sweetener D	City 1	163.75	163.75	149	178.5	19.80%
Sweetener D	City 2	169.75	169.75	155	184.5	19.03%


2. Referee's note
O — Observation: In this teaching dataset, the mean price of all four items is higher than the first-date average by the final date. The largest first-to-last percentage increase is Sweetener D (19.41%), followed by Oil B (15.28%), Staple A (12.98%), and Pulse C (3.69%). Pulse C changes the least over the period. City 2 is consistently PKR 6/kg above City 1 for every item and date.

O — Observation: The mean and median are close for each item. For example, Staple A has a pooled mean of PKR 111.17/kg and a median of PKR 111.75/kg. Oil B has a mean of PKR 324.83/kg and a median of PKR 324.00/kg.

E — Possible explanation (not established by this dataset): The close mean and median may indicate that no single unusually large or small observation is strongly pulling the average away from the middle. The regular PKR 6 difference between the two city series may reflect how the teaching data were constructed; the file does not tell us why the difference exists.

C — Causal claim not supported: These numbers do not show that a particular policy, supplier, shortage, tax, transport cost, or market event caused prices to rise. The dataset contains no information about those factors, and it is explicitly labelled illustrative rather than actual PBS observations.

Referee's conclusion: The data support a limited descriptive statement: in this illustrative sample, all four items finish above their first-date levels, but the size of the change differs by item. They do not establish why prices changed, whether the pattern represents Pakistan generally, or whether consumers' overall cost of living rose by the same percentages. A real-world conclusion would require verified price observations, a defined representative basket, and evidence about possible causes.
3. Week 2 comparison: flagged value check
The assignment asks for the mean and median of one item with and without a flagged value. I checked both uploaded CSVs. They contain the same 96 date-item-city-price observations. The second file has only the four core columns; the first adds unit and data_label. Neither file contains a flag column, a flagged-row marker, or a separate indication of which value should be excluded.

Therefore, a valid with/without-flag calculation cannot be made from the supplied files without inventing which observation is flagged. For reference, the pooled Week 2-file values for Staple A are mean PKR 111.17/kg and median PKR 111.75/kg (24 observations). These are the unfiltered statistics; they are not a with/without-flag comparison. The flagged-value part remains unresolved until the instructor's flagged observation or Week 2 version containing the flag is supplied.
4. Interpretation audit
Below is an example AI interpretation and a claim-by-claim audit. The interpretation is deliberately separated from the verified calculations.

AI interpretation to audit:
“Prices rose sharply across the two cities during the period. Sweetener D was the worst affected, increasing by about 19.4%, while Pulse C was comparatively stable at about 3.7%. The mean and median are almost identical, proving there were no outliers. The consistent gap between cities shows that City 2 has higher transport costs. These increases were probably caused by inflation and supply-chain pressure, so households faced a major rise in their cost of living.”
AI claim	Colour	Check	Decision
Sweetener D rose about 19.4% from first to last date.	Green	Recomputed using the two-city average on the first and last dates: 19.41%.	Accept, as a description of this teaching dataset.
Pulse C rose about 3.7%.	Green	Recomputed first-to-last change: 3.69%.	Accept, with the same limitation.
The mean and median are close.	Green	Recomputed for all four items; the values are close.	Accept.
Close mean and median prove there were no outliers.	Amber	Similar mean and median do not prove that no outlier exists. A distribution plot or robust outlier check would be needed.	Reject the word “proving”; at most say there is no large mean-median separation.
City 2's gap is caused by higher transport costs.	Red	The file records prices and city labels, not transport costs or causes.	Reject as unsupported causal claim.
Inflation and supply-chain pressure caused the increases.	Red	No inflation series, supply data, policy information, or causal design is included.	Reject as unsupported causal claim.
Households faced a major rise in cost of living.	Red	Four illustrative item series are not a representative household basket; no weights or household expenditure data are supplied.	Reject as a conclusion from these data.


5. Confused-classmate excerpt
Classmate: “If the mean is higher than the median, doesn't that automatically mean prices are going up?”

Response: “No. Mean versus median describes the distribution of the observations, not the direction of change over time. To describe whether prices went up, compare prices across dates. For example, Staple A's two-city average moves from PKR 104.00/kg on the first date to PKR 117.50/kg on the last date, a 12.98% increase. Its mean of PKR 111.17 and median of PKR 111.75 answer a different question: what are the average and middle values across all recorded observations?”

Classmate: “So can we say the higher prices happened because transport became expensive?”

Response: “Not from this file. We can report the difference between City 1 and City 2, but the dataset does not include transport costs. A difference is an observation; transport cost is only a possible explanation unless we have evidence.”
6. Reflection
My first draft could have gone beyond the data by treating the increases as proof of inflation, supply shortages, or higher transport costs. The dataset only records illustrative prices, dates, items, and cities. It does not measure causes or represent a weighted household basket. I therefore kept the final conclusion descriptive, labelled possible explanations as explanations, and rejected causal statements that the available variables cannot test.
Method and limitations
- Mean and median use all 24 observations per item (12 dates × 2 cities).
- First-to-last percentage change is calculated as ((last-date two-city average / first-date two-city average) - 1) × 100.
- All prices are explicitly marked illustrative, not actual PBS observations.
- The two CSV files have identical core observations; the additional columns in one file are metadata only.
- No flagged value is identified in either file, so the requested outlier sensitivity comparison cannot be completed honestly from these uploads.
