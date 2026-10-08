MGT353 Forecasting Milestone 1: Nestlé Pakistan, Fruita Vitals 200ml
Company-Calibrated Synthetic Dataset for Academic Analysis — illustrative figures, calibrated to Nestle Pakistan's disclosed scale, not actual company records.
	
Student	Muhammad Ziyam
ERP ID	28359
Course	Supply Chain Analytics (MGT-353), Portfolio Milestone 1: Forecasting Intelligence Dashboard & Decision Story
Instructor	Faisal Jalal
Version date	8 October 2026

What this package contains
File	What it is	Brief deliverable
..._Synthetic_Dataset.xlsx	Four sheets: README (live data checks), Data (104 weekly rows, 12 fields, 1 Jan 2024 – 22 Dec 2025), Data_Dictionary (12 fields), Assumption_Log (18 items)	1. Synthetic dataset
..._Analysis_workbook_notebook.ipynb	Colab notebook in eight sections: setup and data checks, demand profile, error metrics, models and comparison, regression, holdout validation, stress test, summary. Saved outputs and charts are included	2. Analysis workbook / notebook
..._Forecasting Dashboard_v1.html	Self-contained interactive dashboard (zones A–H). Opens in any browser, no internet needed	3. Forecasting Dashboard v1
..._Decision_Storyboard.pptx	Six-slide management storyboard, from decision to action	4. Decision storyboard
..._Executive_Decision_Memo.docx	One-page memo: recommendation, evidence, risk, review trigger	5. Executive decision memo
..._AI_Use_Log.docx	Tools used, prompt and output log, AI errors found and corrected, prompt appendix	6. AI use log
..._Validation_note.docx	Holdout design, leakage check, five largest errors and diagnosis	7. Validation note
..._Final_Report.docx	Consolidated report with every mandatory table (data dictionary, model comparison, regression, stress test, quality gates)	Supporting document

The decision
How many Fruita Vitals 200ml packs should we plan to supply over 29 Dec 2025 – 22 Mar 2026, and how much should we commit now versus keep flexible?
Recommendation: plan about 9.4 million packs (realistic range 8.9–9.8 million). Commit firm orders to 100% of the forecast, hold about 1.2 million packs (1.5 weeks) of opening stock, and keep flexible supply for up to 10% of weekly volume. Reforecast if the first two weeks fall outside 1.22–1.49 million packs, the tracking signal leaves ±4, four-week demand is more than 10% off forecast, a packaging delivery slips by more than a week, or the Ramadan or Eid date moves.
Headline results (12 unseen holdout weeks, Error = Actual − Forecast)
Model	MAPE	WAPE	MAD (packs)	Bias (packs/week)	Tracking signal
Regression (planned inputs)	6.2%	6.4%	46,868	+15,436	+4.0
Seasonal index + event	9.0%	9.2%	67,466	−3,662	−0.7
Naive	10.8%	10.8%	79,300	−22,900	−3.5
Exponential smoothing (α = 0.6)	13.5%	13.1%	96,342	−56,984	−7.1
Moving average (4-week)	14.9%	14.3%	105,113	−74,525	−8.5
Exponential smoothing (α = 0.3)	15.4%	14.7%	108,213	−80,727	−9.0
Seasonal naive (52)	16.7%	17.0%	125,325	+76,858	+7.4
Positive bias and tracking signal mean under-forecast; negative means over-forecast.
How to use each file

•	Dashboard: double-click the .html file. Use the metric buttons in the accuracy panel, the scenario dropdown in the stress-test panel, and hover over chart points for values.

•	Notebook: open in Google Colab (File ▸ Upload notebook), choose Runtime ▸ Run all, and upload the dataset as a CSV when asked. The notebook expects a file named fruita_vitals_200ml_weekly_synthetic.csv containing the 12 data columns from the Data sheet (columns A–L). A re-exported CSV may show a different SHA-256 hash from the one printed in the saved outputs, because of formatting only; the values are the same.

•	Documents and slides: open in Word and PowerPoint. Suggested reading order: Executive Decision Memo, Decision Storyboard, Dashboard, Final Report, Validation Note, AI Use Log.

Data and integrity notes
•	All data are synthetic, built from a seeded generator calibrated to Nestlé Pakistan's disclosed revenue (PKR 199,069 million), and frozen before modelling (SHA-256 begins 5bdda4d12a2008f0). Driver effects were built in by design, so results demonstrate method, not real-world proof.
•	Models were fitted on weeks 1–92 and scored on weeks 93–104. Replacing the holdout demand with random numbers changed no forecast (maximum change 0.0), and no recursive forecasting was used.
•	The regression results are associations, not proven causes. Price cannot be separated from the long-run trend in this data.
•	Cost, capacity and flexible-supply parameters in the stress test are assumptions, and the scenarios are not probability-weighted.

Known limitations
An unexplained December under-forecast; promo and event coefficients that differ across halves of the data; no event weeks or stockouts in the holdout; and the historical forecast is a simulation that used part of the true effect sizes.

AI use
Claude (Anthropic) assisted with planning, code, drafting and review. An independent audit prompt re-checked leakage, formulas and coefficients, and the corrections are listed in the AI Use Log.

