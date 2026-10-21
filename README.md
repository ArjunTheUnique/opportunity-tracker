# Opportunity Tracker

Scholarships, internships, government notifications, career-magazine coverage and study pathways for students and job-seekers in India, with a strong **Andhra Pradesh** focus.

Everything here was compiled from official portals and published news coverage, then organised into three datasets. Each dataset is available in three formats: an **Excel workbook** (filterable), a **CSV** (reusable in any tool), and an **interactive HTML page** (click filters, results update instantly — just open the file in a browser).

Compiled: **28 September 2026**.

---

## Repository structure

```
opportunity-tracker/
├── newspapers/          Notifications, internships & scholarships from the press
├── career-magazines/    Coverage from 8 career / exam magazines
└── study-pathways/      "What to study next" after each education level
```

### 1. `newspapers/` — press notifications log

Coverage window: **April – September 2026**. Compiled from Eenadu (Pratibha), Sakshi (Education), Andhrajyothy, The Hindu and Times of India coverage, cross-checked against official portals.

| File | What it is |
|---|---|
| `Notifications_Log_Apr-Sep_2026.xlsx` | Workbook with separate sheets for Scholarships, Internships, and Govt Jobs & Exams |
| `scholarships.csv` | 27 scholarships (central, AP state, private/CSR) |
| `internships.csv` | 32 internship programmes |
| `govt-jobs-exams.csv` | 26 government job and exam notifications |
| `Opportunity_Finder.html` | Interactive filter tool — filter by type, community/caste, education, gender, status; includes search |

### 2. `career-magazines/` — 8 career & exam magazines

Coverage window: **April 2025 – September 2026 (18 months)**. One Excel workbook per magazine, each with its own Overview and Log sheet. Sections logged: **scholarships & fellowships, internships, and admissions / entrance exams** (government job recruitment was deliberately excluded).

Magazines: Employment News · Pratiyogita Darpan · Competition Success Review · Civil Services Chronicle · Banking Services Chronicle · Samanya Gyan Darpan · Success Mirror · Udyoga Sopanam

| File | What it is |
|---|---|
| `<Magazine>_Log_Apr2025-Sep2026.xlsx` | One workbook per magazine (8 files) |
| `career-magazines-log.csv` | All 170 entries combined, with a `Magazine` column for filtering |
| `Career_Magazine_Finder.html` | Interactive filter tool — filter by magazine, type, community/caste, education, gender, coverage year, status; includes search |

### 3. `study-pathways/` — what to study next

For each education level completed — **Class 10, Intermediate, ITI, Diploma, any Degree, B.Tech, Law, Medicine, PG** — the courses and programmes you can pursue next, with entrance exams, eligibility, AP-specific routes and career outcomes.

| File | What it is |
|---|---|
| `Study_Pathways_By_Level.xlsx` | 114 pathways, colour-coded by starting level |
| `study-pathways.csv` | Same data as CSV |
| `Study_Pathways_Finder.html` | Interactive filter tool — filter by starting level, field, course type, and whether an entrance exam is needed |

---

## How the data is organised

Every row in every dataset carries the fields you need to judge eligibility at a glance: the education background it suits, caste/community where the scheme specifies one, gender, income limit, age limit, the cycle (annual / monthly / one-time / rolling), award or stipend, application mode, deadline, status and the official website.

Two conventions worth knowing:

- **Community filter logic.** Items marked *open to all* are eligible for every community, so the filter tools include them for any community you select (for example, SC). A **strict mode** toggle narrows results to items specifically earmarked for that community. **Brahmin is treated as OC** (as in Andhra Pradesh's reservation categories).
- **Status colours.** Green = open to apply now · Blue = rolling · Amber = upcoming · Grey = dates to be announced · Red = closed for the year. Closed items are retained because most exams and scholarship cycles are annual and repeat — the dates show you when to expect the next cycle.

## Method and caveats

- Print/scanned archives of these publications are not publicly accessible in bulk. Entries were compiled from each publication's own website or web edition where available, and from official notification portals and reputable coverage elsewhere.
- Each row's **Source(s)** column links where the facts were verified. Where an item's appearance in a specific magazine issue could not be directly sighted, the **Notes** column says so — the item is included because it falls within that magazine's normal coverage and was verified against primary sources.
- **Deadlines, fees and vacancy counts change.** Always verify on the official website listed in each row before relying on any date.
- This is an information compilation, not an endorsement, and not personal career or financial advice. Never apply through third-party paid agents — apply only on the official portals.

## Using the HTML tools

No installation needed. Download or open any `.html` file in a browser (desktop or mobile) and click the filters — results update instantly. The filter bar is collapsible and starts collapsed on small screens so results are immediately readable. Everything runs locally in the browser; nothing is sent anywhere.

## Using the CSVs

Straightforward to load in Excel, Google Sheets, Python (`pandas.read_csv`), or any database. The magazine CSV includes a `Magazine` column; the newspapers CSVs are one per category.
