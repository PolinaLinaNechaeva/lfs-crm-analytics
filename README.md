lfs-crm-analytics

End-to-end CRM analytics project for LfS (Learning for Success) — an online programming school.
The project covers full data cleaning, exploratory analysis, unit economics, metric tree design, and dashboarding.

Interactive dashboard (Tableau):
https://public.tableau.com/app/profile/polina.nechaeva/viz/Nechaeva_final_project/Dashboard1?publish=yes

⸻

Project Overview

This project analyses the complete customer journey inside the school’s CRM system:
	•	Contacts — lead characteristics
	•	Calls — communication history
	•	Deals — sales pipeline
	•	Spend — marketing investments

Objectives:
• identify bottlenecks in the funnel
• evaluate campaign efficiency
• analyse call performance
• increase revenue through insights and optimisation

⸻

Repository Structure

lfs-crm-analytics/
├─ master_cleaning.py — data cleaning pipeline
├─ notebooks/
│   └─ lfs_analysis.ipynb — exploratory analysis & charts
├─ docs/
│   └─ project_description.pdf — assignment & schema
├─ README.md
└─ requirements.txt

⸻

Source Data

Raw CRM data is not published due to confidentiality.

The cleaning script expects the following files in the project root:
	•	Spend (Done).xlsx
	•	DWW Deals Done.xlsx
	•	DWW Calls Done.xlsx
	•	DWW Contacts Done.xlsx

⸻

Data Cleaning Pipeline (master_cleaning.py)

Spend
	•	Normalises date formats
	•	Fills missing text values
	•	Removes full duplicates

Deals
	•	Converts IDs and amounts
	•	Removes “Duplicate” lost reasons
	•	Groups lost reasons into categories
	•	Normalises dates
	•	Fills missing SLA, numeric and text fields

Calls
	•	Normalises messy duration formats
	•	Extracts call date/time
	•	Fills missing contact IDs by owner mode
	•	Deduplicates parallel calls
	•	Removes duration outliers
	•	Categorises calls by duration

Contacts
	•	Splits timestamps into date/time
	•	Fixes CONTACTID format
	•	Removes full duplicates

Final Output

Creates projekt.xlsx with 4 sheets:
• spend
• deals
• calls
• contacts

⸻

Exploratory Analysis (lfs_analysis.ipynb)

Lead Quality
	•	Better German proficiency → higher conversion
	•	Lead quality varies strongly by source

Calls
	•	Most calls are very short (<2 minutes)
	•	Short calls have low conversion efficiency
	•	Manager behaviour varies significantly

Deals
	•	Biggest drop-off: Lead → Contacted, Follow-up → Closing
	•	Price-related lost reasons dominate

Marketing Spend
	•	Several campaigns generate volume but almost no conversion
	•	Some low-budget campaigns show best CPL

Unit Economics
	•	Products differ in profitability
	•	German-speaking audience increases LTV

⸻

Metric Tree

Revenue
├─ Number of Deals
│   ├─ Leads
│   ├─ Call Conversion
│   └─ Deal Conversion
└─ Average Deal Amount

⸻

Key Hypotheses

H1 — Increasing call duration improves conversion.
H2 — German-proficient leads generate higher revenue.
H3 — Consistent follow-ups increase closing probability.
H4 — Some campaigns drain budget with minimal return.
H5 — Manager call activity does not match student availability peaks.

Testing window: 1–2 weeks each.

⸻

Dashboard

Includes:
	•	Lead quality & structure
	•	Call distribution & efficiency
	•	Deal funnel & lost reason analysis
	•	Campaign performance
	•	Product and LTV analysis

Dashboard link:
https://public.tableau.com/app/profile/polina.nechaeva/viz/Nechaeva_final_project/Dashboard1?publish=yes

⸻

How to Run

Install dependencies:

pip install -r requirements.txt

Place input files in the project root.

Run the cleaning pipeline:

python master_cleaning.py

Open the analysis notebook:

notebooks/lfs_analysis.ipynb

⸻

Requirements

pandas
numpy
matplotlib
seaborn
openpyxl

⸻

Author

Polina Nechaeva
Data Analyst (BI)
LinkedIn: https://www.linkedin.com/in/polina-nechaeva-b3a67a349/

⸻

License

MIT License.
