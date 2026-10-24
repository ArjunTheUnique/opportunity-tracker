# Opportunity Tracker

Scholarships, internships, government notifications, live exam notifications, career-magazine coverage and study pathways for students and job-seekers in India, with a strong **Andhra Pradesh** focus.

Everything here is compiled from official portals and published coverage, then organised into four datasets. Each dataset comes as an **Excel workbook** (filterable), a **CSV** (reusable anywhere) and an **interactive HTML page** — and every HTML page now includes a **personal eligibility check**.

Last updated: **25 October 2026**.

---

## Check your own eligibility

The three opportunity tools have a **"Filters & my profile"** panel at the top. Enter your **age** and tick your **community/caste** and **education** (and optionally gender), and every card immediately shows one of:

- **Eligible** — you pass every check the data can make
- **Not eligible** — with the reason, e.g. *"Age: this needs 18 to 25 years; you entered 31"*
- **Check details** — nothing disqualifies you, but the notice doesn't state an age limit (or gives a birth-date window), so you must confirm it yourself

There's a **"Hide items I am not eligible for"** toggle, and the results bar counts how many items match your profile. Age limits are read from what each notice actually states — the tool never guesses a number. **Brahmin is treated as OC** (as in Andhra Pradesh's reservation categories), and items marked *open to all* count as eligible for every community.

---

## Repository structure

```
opportunity-tracker/
├── newspapers/               Press notifications log (Apr-Oct 2026)
├── career-magazines/         8 career / exam magazines (Apr 2025 - Oct 2026)
├── live-exam-notifications/  Live AP state + central exam notifications (refreshed twice weekly)
└── study-pathways/           "What to study next" after each education level
```

### 1. `newspapers/` — press notifications log

Coverage: **April – October 2026**, compiled from Eenadu (Pratibha), Sakshi (Education), Andhrajyothy, The Hindu and Times of India coverage, cross-checked against official portals.

`Notifications_Log_Apr-Sep_2026.xlsx` · `scholarships.csv` (33) · `internships.csv` (36) · `govt-jobs-exams.csv` (33) · `Opportunity_Finder.html` (102 entries, with eligibility check)

### 2. `career-magazines/` — 8 career & exam magazines

Coverage: **April 2025 – October 2026**. One Excel workbook per magazine, each with its own Overview and Log sheet. Sections: **scholarships & fellowships, internships, admissions / entrance exams** (government job recruitment deliberately excluded).

Magazines: Employment News · Pratiyogita Darpan · Competition Success Review · Civil Services Chronicle · Banking Services Chronicle · Samanya Gyan Darpan · Success Mirror · Udyoga Sopanam

`<Magazine>_Log_Apr2025-Sep2026.xlsx` (8 files) · `career-magazines-log.csv` (225 entries) · `Career_Magazine_Finder.html` (225 entries, with eligibility check)

### 3. `live-exam-notifications/` — live AP state + central exams

Currently open and recently closed recruitment and entrance-exam notifications, verified against official portals: APPSC, AP SLPRB, AP CET portals (EAPCET, ECET, ICET, PGECET, EdCET, LAWCET, POLYCET, PGCET, DEECET), AP High Court, Dr NTR UHS, UPSC, SSC, RRB, IBPS, SBI, RBI, NTA and defence bodies.

`live-exam-notifications.csv` · `Live_Exam_Notifications.xlsx` · `Live_Exam_Notifications.html` (74 notifications, with eligibility check)

Age limits here are taken **directly from each notification**, so the eligibility verdict is reliable. Where a notice gives only a birth-date window (or the age clause is in a detailed notice not yet published), the range is left blank rather than guessed.

### 4. `study-pathways/` — what to study next

For each level completed — Class 10, Intermediate, ITI, Diploma, any Degree, B.Tech, Law, Medicine, PG — the courses you can pursue next, with entrance exams, eligibility, AP routes and career outcomes.

`Study_Pathways_By_Level.xlsx` · `study-pathways.csv` · `Study_Pathways_Finder.html` (114 pathways)

---

## Automatic refresh

A scheduled job runs **twice a week (Mondays and Thursdays, 09:00 IST)**. Each run:

1. Scrapes the 8 career magazines and the AP/central official portals for anything new
2. Adds genuinely new entries (skipping duplicates, but keeping new cycles of a scheme as separate rows)
3. Rebuilds the Excel, CSV and HTML files
4. Pushes the updated files here and reports what was added

## Method and caveats

- Print/scanned archives of these publications are not publicly accessible in bulk, so entries come from each publication's own website or web edition where available, plus official notification portals elsewhere.
- Each row's **Source(s)** column links where the facts were verified; the **Notes** column says whether appearance in a specific magazine issue was directly verified or inferred from that magazine's normal coverage.
- **Deadlines, fees and vacancy counts change.** Always verify on the official link in each row before relying on any date.
- This is an information compilation, not an endorsement, and not personal career or financial advice. Never apply through third-party paid agents — apply only on the official portals.

## Using the tools and CSVs

Open any `.html` file in a browser (desktop or mobile) — everything runs locally, nothing is sent anywhere. The filter panel is collapsible and starts collapsed on small screens. The CSVs load straight into Excel, Google Sheets, `pandas.read_csv` or any database.
