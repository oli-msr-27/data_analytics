# MEP Data Analytics (w.BA.XX.3DA-WIN.XX, HS26): Exam Analysis & 20-Hour Study Plan

> **Basis:** only the files in this codespace (as of 24.09.2026). Nothing from Moodle, the web or memory.
> **Legend:** **FACT** = stated in a document (source given). **ASSESSMENT** = my conclusion from the facts (German: *Einschätzung*).
> **Source format:** `file` + page (p.) / question (Q) / task (T) / notebook cell. "SC" = small class (Kleinklasse), "LC" = large class (Grossklasse).
> The old exams are cited by their PDF page, i.e. the page number of the file itself. This is the number you type in a PDF viewer, not the printed "Page x of y".

---

## 0. TL;DR: the 10 things that matter most

1. **The exam blueprint has been identical for 3 years (FACT).** Each exam has 30 single-choice questions worth 2 points each (60 points), split into 10 printed sections in week order. The questions per section were 3–4 / 4–5 / 4 / 4 / 2 / 2 / 3 / 3 / 2 / 2 in all three exams (Section 5.2).
2. **24 question types appeared in *every* exam, covering 85 of 90 questions (94 %) (FACT, counted).** If you can solve the ~25 recurring types, you cover almost the whole exam (Table B).
3. **The first ~40 % of the exam is Python/pandas code (FACT).** Sections S2 + S3 have 26 questions over the 3 exams. 25 of them are Application questions ("predict the output of this code"): `type()`, list/tuple/set/dict, `concat`/`merge`/`groupby`/`pivot_table`, `dropna`/`.loc`/`.iloc`, regex.
4. **The rest is interpretation and hand calculation (FACT).** 14 of 90 questions are hand calculations: sample standard deviation, relative and expected frequencies, regression prediction, confusion-matrix metrics. The rest interpret something: boxplots, heatmaps, R², ROC/AUC, elbow and silhouette plots, TF-IDF.
5. **Only 7 % of questions are pure reproduction (definitions) (FACT: 6/90).** Understanding is 41 % and Application 52 %.
6. **Never tested in 90 questions (FACT):** neural networks, Flask/Dash, ANOVA, simulation/bootstrapping, SQL, regression trees (RT), matplotlib code, QGIS, sentiment classifiers.
7. **Neural networks are officially excluded (FACT).** [`tasks_large_classes_week_11.md`](../Week_LC/LC_11/tasks_large_classes_week_11.md) Task 1 says *"knowledge about the functionality of neural networks is not part of the written exam"*. NN is also missing from the HS26 Module description.
8. **Exercise content shows up almost 1:1 in the exams (FACT).** Examples: HS24 Q17 uses the same address as Week 5 T1, HS23/HS25 Q18 the same GeoAdmin code as the Week 5 notebook, HS25 Q11 the same `str.contains` pattern as Week 3, and HS24 Q12 the same regex loop as Week 2. This confirms the Semester program's statement that the exercises "will be part of the written exam".
9. **The biggest data gap is the lecture slides (FACT).** They are not in the codespace, although exercise PDFs for Weeks 2–13 point to them ("see slides"). Several recurring question types (scales of measurement/Likert, XPath, WKT/GeoJSON, Gini, precision/recall formulas, SSE/SST) have **no material in the repo**. You need the slides for these (Section E).
10. **Time plan (ASSESSMENT):** 14.5 h on the 26 🟢 topics, 1.5 h on 🟠, 0 h on 🔴, 3 h doing the 3 old MEPs under exam conditions, and 1 h writing the 2-page summary = **20 h**.

---

## 1. Inventory: what is in the codespace

### 1.1 Files found

| File(s) | Type | Year / semester | Size | Completeness / notes |
|---|---|---|---|---|
| `MEP/23_BA.3DA-WIN-3.pdf` | Old MEP (scan, no text layer) | HS23, exam **25.01.2024** 08:00–09:00 (p.1) | 21 p. | Complete: cover sheet, answer sheet, 18 question pages, **Q1–Q30 all present**. **No answer key**; the answer grid on p.3 is blank. Q24 is faint but readable. |
| `MEP/24_BA.3DA-WIN-2.pdf` | Old MEP (scan) | HS24, exam **20.01.2025** 14:00–15:00 (p.1) | 23 p. | Complete, Q1–Q30. **No answer key.** Q10 has faint digits in the price list; Q24 option b has small fractions (probably a typo in the exam). |
| `MEP/25_BA.3DA-WIN.pdf` | Old MEP (scan) | HS25, exam **22.01.2026** 10:00–11:00 (p.1) | 24 p. | Complete, Q1–Q30. **No answer key.** Q3 is a low-contrast code screenshot, some heatmap values in Q19 are hard to read, and the axis ticks in Q28 are only partly legible. |
| `MEP/DataAnalytics_ModuleDescription_w.BA.XX.3DA-WIN.XX.pdf` | Module description | **valid from 2026.HS** (p.1) | 4 p. | Complete, has a text layer. |
| `MEP/DataAnalytics_Semesterprogram_w_BA_XX_DA_HS26.pdf` | Semester program | HS26 (p.1) | 4 p. | Complete. The exam date is **not** given ("End-of-module exams – –", p.3). |
| `MEP/DataAnalytics_General information.pdf` | General course information | no semester printed (PDF metadata: created 14.09.2026) | 6 p. | Complete. Deals mostly with project grading. |
| `Week_01 … Week_13/Excercises_Week_XX.pdf` | Small-class exercise sheets | current repo (HS26 week numbering) | 2–4 p. each | 13/13 present. **No solutions.** |
| `Week_01 … Week_12/*.ipynb` (27 notebooks) | Demo/template notebooks used by the exercises | — | 1,036 cells incl. LC notebooks (see below) | Present. These are the "run this notebook step by step" material, **not** exercise solutions. |
| `Week_13/*` (Flask / Dash apps, `.py`) | Demo web apps | — | — | Present (no notebooks). |
| `Week_LC/LC_01 … LC_13` (13 task `.md` files, 12 notebooks) | Large-class exercises | — | — | 13/13 task files. **Solutions only for LC_01 and LC_02.** |
| `Week_14/README.txt` | — | — | **0 bytes (empty)** | Week 14 is presentations only (Semester program p.3). |
| `Agentic_Data_Analytics_Experiment_LangGraph/` | LangGraph multi-agent demo | — | — | Not listed in the Semester program. **ASSESSMENT:** not exam material. |
| CSV/XLSX/DB/geodata/image files in the week folders | Datasets | — | — | Used by the notebooks. Not analyzed in detail; not needed for the exam. |

### 1.2 Expected files that are missing
| Missing | Evidence it exists | Impact |
|---|---|---|
| **Lecture slides, Weeks 1–13** | The exercise PDFs for Weeks 2–13 say "(see slides of week 01)" (Figure 1 on p.1); Week 1 says "(see lessons)". `Week_08/linear_regression.ipynb` cell 24 says "see slides of lessons". | **High.** Depth of teaching can't be measured by slide count, and several exam question types have no repo source (see E). |
| **Answer keys for the 3 MEPs** | Answer sheets are blank (p.3 of each MEP). | Medium. You can't check your answers against an official key. |
| **Solutions to the small-class exercises** | The Module description p.2 lists "Practice and Application Exercises (with Key)" | Medium. |
| **MEPs before HS23 / a HS26 sample exam** | None found | Low–medium. The pattern rests on 3 exams only. |
| Leaflet "Utilities" / "Guidelines on Supplementary Materials" (permitted calculator) | Module description p.3; MEP covers p.1 | Low. You need it to know which calculator is allowed. |
| QGIS tutorial videos `qgis_tutorial_01–03.mp4` (Moodle) | `Excercises_Week_05.pdf` T2–T3 | Low (QGIS never tested). |

---

## 2. Step 1: Module description & Semester program

### 2.1 Exam facts (all FACT)
| Item | Value | Source |
|---|---|---|
| Form | Written exam, **open book**, **60 min**, **60 %** of module grade | Module description p.3; Semester program p.1; General information p.2 |
| Question type | **Single-choice only, 4 options, exactly one correct** | Semester program p.1; General information p.2 |
| Scope | "cover the **entire material** of the module" | Semester program p.1; General information p.2 |
| Language | English | Module description p.1 |
| Allowed aids | Calculator according to leaflet "Utilities"; dictionary | Module description p.3 |
| Scoring (old MEPs) | Multiple answers or no answer → 0 marks for that question. **No penalty for a wrong answer is mentioned.** | HS23 p.4, HS24 p.4, HS25 p.4 |
| Weekly exercises | "must not be submitted on Moodle; they serve as preparation for **and will be part of** the written exam" | Semester program p.1 |
| Which rules apply | "Only the current module description is relevant with regard to the exam and composition of final grade" | Semester program p.1; General information p.2 |
| Other 40 % | Project work (20 % submission + 20 % concept presentation). Deadline 10.01.2027 | Semester program p.1 |

**ASSESSMENT:** Never leave a question blank. A guess costs nothing and has a 25 % chance of being right.

### 2.2 Module content HS26 (FACT, Module description p.2), mapped to weeks (FACT, Semester program p.2–3)
| # | Module content (Module description) | Week | Old MEP section (FACT, printed headers) |
|---|---|---|---|
| 1 | Introduction: basic concepts, methods, applications | W1 | S1 Categorization of Data & Data Collection Methods |
| 2 | Data sources & collection: OpenData, web scraping, web APIs | W1 | S1 |
| 3 | Data types & structures in Python, file formats | W2 | S2 Data Types, Data Structures & File Formats in Python |
| 4 | Import/export; SQL databases | W2 | S2 (SQL never asked) |
| 5 | Clean, organize, enrich, create & **simulate** data | W3 (+W6 simulation) | S3 Data Preparation & Combining & Organizing Data |
| 6 | Graphical & non-graphical EDA | W4 | S4 Exploratory Data Analysis |
| 7 | Geographical data | W5 | S5 Representation & Analysis of Geographical Data |
| 8 | Hypothesis testing (I): paired & unpaired sample tests, contingency tables | W6 (+W7) | S6 Statistical Hypothesis Testing |
| 9 | Hypothesis testing (II): correlation, ANOVA | W7 (+W6) | S6 (and correlation inside S4) |
| 10 | Regression (linear regression, regression trees) | W8 | S7 Regression Analysis |
| 11 | Classification (classification trees, random forests) | W9 | S8 Classification Analysis |
| 12 | Clustering (k-means) | W10 | S9 Cluster Analysis |
| 13 | Text mining & sentiment analysis | W11 | S10 Text Mining & Sentiment Analysis |
| 14 | Presenting & sharing results | W13 | — (no section) |
| — | *(not in Module description)* Introduction to Neural Networks | W12 | — (no section) |

### 2.3 Contradictions and changes (FACT unless marked)
1. **Grade weighting changed.** All three old MEPs print 70 % exam / 30 % project plus a pass/fail requirement to submit at least 10 weekly exercises (answer sheet p.2 of HS23, HS24 and HS25). HS26 is **60 % / 40 %** with **no submission** (Module description p.3; Semester program p.1). The exam format itself did not change: 60 min, open book, 30 single-choice questions, 60 points.
2. **Exercises: "part of the exam" vs "preparation".** The Semester program p.1 says "serve as preparation for **and will be part of** the written exam". `DataAnalytics_General information.pdf` p.1 only says "serve as preparation for the written exam". Your fact matches the Semester program. **ASSESSMENT:** the old MEPs support the stronger wording (see pattern P7).
3. **Neural networks.** They are in the Semester program (W12) but not in the Module description content or learning objectives (p.2). `Week_LC/LC_11/tasks_large_classes_week_11.md` Task 1 (lines 20–21) says NN functionality "is not part of the written exam". The Module description is binding (Semester program p.1).
4. **Old submission text in all 13 exercise PDFs.** Each intro still says "Results of the exercises must be uploaded … on Moodle". Notebook footers say "please always provide this at the end of each submitted notebook". Both contradict the HS26 program ("must not be submitted").
5. **Hypothesis-testing split.** The Module description puts contingency tables in Part I and ANOVA in Part II. The materials do the opposite: W6 has t-test + ANOVA, W7 has chi-squared + correlation. Only the order differs, not the content.
6. **Paired tests.** The Module description names "paired & unpaired sample tests", but the repo only contains `stats.ttest_ind` (unpaired) in `Week_06/unpaired_two_sample_t-test.ipynb`. HS23 Q19 asks about unpaired vs paired t-tests. → The paired t-test is only in the slides (data gap).
7. **Exercise keys.** The Module description p.2 promises "Practice and Application Exercises (with Key)". No keys for the small-class exercises are in the repo.

### 2.4 Interim result, Step 1
- **FACT:** The HS26 exam format (60 min, open book, 30 single-choice questions, whole module, English) is identical to HS23–HS25. Only the grade weighting changed. So the old exams are fully usable as a template.
- **FACT:** The binding HS26 content list covers all 10 old exam sections. NN (W12) is excluded by a course document, and "Presenting & sharing" (W13) has never had an exam section.

---

## 3. Step 2: Teaching materials & exercises

> **Limitation (FACT):** no slide decks or scripts are in the codespace. Depth of teaching is therefore measured with **proxies**: number of exercise tasks and subtasks, number of notebooks and cells, and in how many weeks a topic appears as a core/secondary/mentioned topic. All counts come from reading every exercise PDF, notebook and LC task file.

### 3.1 Depth per week (FACT, counted)
| Week | HS26 topic (Semester program) | SC exercise: tasks / subtasks | LC: tasks / subtasks | Notebooks / cells | Core topics (taxonomy) | Key Python functions listed |
|---|---|---|---|---|---|---|
| W1 | Introduction to Data Analytics, Categorization of Data, Data Sources & Data Collection Methods | 3 / 18 | 5 / 13 | 3 / 36 | T01, T02, T24 | 24 |
| W2 | Data Types, Data Structures, File Formats, Character Encoding, Import and Export of Data in Python | 4 / 27 | 4 / 8 | 8 / 181 | T03, T04, T05, T06 | 42 |
| W3 | Data Preparation, Combining & Organizing Data | 3 / 19 | 3 / 10 | 2 / 66 | T06, T07 | 28 |
| W4 | Exploratory Data Analysis (EDA) | 4 / 14 | 3 / 5 | 3 / 114 | T09, T10 | 36 |
| W5 | Representation & Analysis of Geographical Data | 3 / 15 | 3 / 4 | 1 / 19 | T11 | 21 |
| W6 | Statistical Hypothesis Testing (Part I) | 3 / 14 | 3 / 2 | 4 / 74 | T08, T12, T13, T14 | 23 |
| W7 | Statistical Hypothesis Testing (Part II) | 3 / 14 | 2 / 7 | 3 / 76 | T12, T15, T16 | 19 |
| W8 | Regression Analysis (OLS, RT) | 2 / 10 | 3 / 9 | 3 / 82 | T17, T18 | 27 |
| W9 | Classification Analysis (CT, RF) | 2 / 8 | 6 / 3 | 2 / 66 | T08, T19, T25 | 23 |
| W10 | Cluster Analysis (k-means) | 2 / 15 | 4 / 0 | 2 / 77 | T20 | 27 |
| W11 | Text Mining & Sentiment Analysis | 2 / 8 | 3 / 0 | 3 / 119 | T21 | 27 |
| W12 | Introduction to Neural Networks | 4 / 17 | 5 / 8 | 5 / 126 | T22 | 27 |
| W13 | Presenting and Sharing Data Analysis Results | 3 / 16 | 3 / 3 | 0 / 0 | T23 | 27 |

**Totals:** 38 small-class tasks with 195 subtasks, 47 large-class tasks with 72 subtasks, 39 notebooks with 1,036 cells.

### 3.2 What appears repeatedly vs only in passing (FACT, counted over the 13 weeks)
| Topic (taxonomy) | Weeks as **core** | Weeks as secondary | Weeks only mentioned | # weeks touched |
|---|---|---|---|---|
| T06 Data preparation / cleaning (dropna, regex, filtering) | W2, W3 | W4, W6, W7, W8, W9, W10, W11 | W1, W5 | 11 |
| T08 Simulation, sampling, bootstrapping | W6, W9 | W7, W10 | W11, W13 | 6 |
| T12 Hypothesis-testing fundamentals | W6, W7 | — | W4, W8 | 4 |
| T24 General Python programming | W1 | W5, W7 | W2, W3, W4, W6, W8, W9, W10, W11, W12, W13 | 13 |
| T10 Graphical EDA (histogram, boxplot) | W4 | W2, W6, W7, W8, W9, W10, W11, W12, W13 | — | 10 |
| T01 Intro DA / categorization of data (scales, Likert, structured vs unstructured) | W1 | — | W2, W3, W4, W5, W6, W7, W8, W9 | 9 |
| T05 Import/export & SQL databases | W2 | W3, W5 | W4, W6, W7, W10 | 7 |
| T07 Combining & organizing (merge, concat, groupby, pivot) | W3 | W2, W4, W6, W7, W9, W11 | — | 7 |
| T03 Python data types & data structures | W2 | W10, W12 | W1, W3, W7 | 6 |
| T09 Non-graphical EDA (std, quartiles, frequency tables) | W4 | W2, W7 | W6, W10, W11 | 6 |
| T02 Data collection: web scraping (XPath) & web APIs | W1 | W4, W5 | W12, W13 | 5 |
| T25 ML fundamentals | W9 | W8, W11, W12, W13 | — | 5 |
| T11 Geographical data (WKT/GeoJSON, CRS, geocoding) | W5 | W1 | W3, W4 | 4 |
| T19 Classification (CT, RF, confusion matrix, ROC) | W9 | W11, W12, W13 | — | 4 |
| T04 File formats (JSON/XML/CSV) & encoding | W2 | W1, W11 | — | 3 |
| T16 Correlation analysis | W7 | W4 | — | 2 |
| T17 Linear regression (OLS) | W8 | — | W4 | 2 |
| T22 Neural networks | W12 | W11 | — | 2 |
| T13 t-tests | W6 | — | — | 1 |
| T14 ANOVA | W6 | — | — | 1 |
| T15 Contingency tables & chi-squared | W7 | — | — | 1 |
| T18 Regression trees / RF regression | W8 | — | — | 1 |
| T20 Clustering (k-means, elbow, silhouette) | W10 | — | — | 1 |
| T21 Text mining / NLP / sentiment | W11 | — | — | 1 |
| T23 Presenting & sharing results (Flask/Dash) | W13 | — | — | 1 |
| T99 Other | — | W13 | W1, W3, W4, W5, W7, W8, W9 | 8 |

### 3.3 Observations (FACT unless marked)
- **Data preparation runs through the whole course.** It is core in W2–W3 and reappears as secondary in 7 more weeks: every modelling notebook starts with `rename`/`dropna`/`drop_duplicates`/`.loc` filtering. Graphical EDA also appears in 10 of 13 weeks.
- **One dataset thread:** most small-class notebooks use the **rental apartments** data (Winterthur/Zürich, `price_per_m2`, `pop_dens`, `bfs_name`). The large-class notebooks use cars (autoscout24), smartphones, stock data and simulated data.
- **Teaching gives most time to** W2 (27 subtasks, 8 notebooks, 181 cells), W3 (19), W1 (18), W12 NN (17) and W13 Flask/Dash (16). **ASSESSMENT:** teaching depth and exam weight are clearly *not* the same. W12 and W13 are among the most practised weeks but had 0 exam questions.
- **Interpretation rules written out in the material** (these are what the exam asks about):
  - `p < 0.05 → reject H0` for the t-test (`Week_06/unpaired_two_sample_t-test.ipynb` cell 10), ANOVA (`analysis_of_variance_ANOVA.ipynb` cell 12) and chi-squared (`Week_07/analysis_of_contingency_tables.ipynb` cell 24).
  - R² = "share of variation of the target explained", and `P>|t| < 0.05` = the variable is significant (`Week_08/linear_regression.ipynb` cell 24; `Excercises_Week_08.pdf` T1 d).
  - Inertia = WCSS (`Week_10/k-means_clustering.ipynb` cell 13).
  - Text preprocessing order: lowercase → remove punctuation → tokenize → remove stopwords → lemmatize (`Week_11/NLP_text_preprocessing.ipynb` cell 5).
  - TF = count/len(doc), IDF = log10(N/df) (same notebook, cells 23–25).
- **Only in passing or LC-only:** Jupyter magics (LC_01), yfinance (LC_04), Google Earth/KML (LC_05), CBOW word embeddings (LC_11), object detection (LC_12), fear-and-greed app (LC_13), cross-validation (LC_09).

### 3.4 Interim result, Step 2
- **FACT:** The material is heaviest in data wrangling (W2–W3), EDA (W4), hypothesis tests (W6–W7) and the modelling weeks (W8–W11). NN and web apps (W12–W13) are practised heavily too.
- **FACT:** Several concepts that the exams ask about have **no source in the repo** (XPath, scales of measurement/Likert, WKT/GeoJSON, paired t-test, Gini, precision/recall/F1 formulas, SSE/SST). **ASSESSMENT:** these are taught on the missing slides.

---

## 4. Step 3: Old MEPs

### 4.1 The three exams (FACT)
| Exam | Date (p.1) | PDF pages | Questions | Points | Answer key | Grade weighting printed (p.2) |
|---|---|---|---|---|---|---|
| HS23 | 25.01.2024 | 21 | 30 (Q1–Q30, p.5–21) | 60 (2 per Q) | none | 70 % exam / 30 % project + pass/fail exercises |
| HS24 | 20.01.2025 | 23 | 30 (p.5–23) | 60 | none | same |
| HS25 | 22.01.2026 | 24 | 30 (p.5–24) | 60 | none | same |

**Recency weighting (as requested):** HS23 × 1.00, HS24 × 1.25, HS25 × 1.50 (+25 % per year, sum 3.75). A "weighted Q per exam" is Σ(weight × questions) / 3.75. **ASSESSMENT:** because the blueprint is so stable, the weighting hardly changes any ranking. It mainly matters for the few types that appear in only 1–2 exams.

### 4.2 Pattern P1: fixed section blueprint (FACT)
All three exams have the **same 10 printed section headers in the same order** (week order):

| Section (printed header) | HS23 | HS24 | HS25 | Weighted Q/exam |
|---|---|---|---|---|
| S1 Categorization of Data & Data Collection Methods | 4 (Q1–4) | 3 (Q1–3) | 3 (Q1–3) | 3.27 |
| S2 Data Types, Data Structures & File Formats in Python | 4 (Q5–8) | 5 (Q4–8) | 5 (Q4–8) | 4.73 |
| S3 Data Preparation & Combining & Organizing Data | 4 (Q9–12) | 4 (Q9–12) | 4 (Q9–12) | 4.00 |
| S4 Exploratory Data Analysis | 4 (Q13–16) | 4 (Q13–16) | 4 (Q13–16) | 4.00 |
| S5 Representation & Analysis of Geographical Data | 2 (Q17–18) | 2 | 2 | 2.00 |
| S6 Statistical Hypothesis Testing | 2 (Q19–20) | 2 | 2 | 2.00 |
| S7 Regression Analysis | 3 (Q21–23) | 3 | 3 | 3.00 |
| S8 Classification Analysis | 3 (Q24–26) | 3 | 3 | 3.00 |
| S9 Cluster Analysis | 2 (Q27–28) | 2 | 2 | 2.00 |
| S10 Text Mining & Sentiment Analysis | 2 (Q29–30) | 2 | 2 | 2.00 |

**ASSESSMENT:** Since HS24 the split has been fixed at 3/5/4/4/2/2/3/3/2/2. A HS26 exam built the same way gives **~40 % of the points to Weeks 1–3** (Python, data formats, pandas) and **~60 % to Weeks 4–11**. No section exists for Weeks 12–13.

### 4.3 Pattern P2: recurring question types (FACT, counted)
See Table B (Section 5B). 24 question types appear in all 3 exams and cover 85/90 questions. The other 5 questions are regex (HS24 Q12, HS25 Q11), t-test (HS23 Q19, HS24 Q20) and Web API code (HS25 Q3).

### 4.4 Pattern P3: level and format per section (FACT, counted from the verified classification)
| Section | #Q (3 exams) | Reproduction | Understanding | Application | Code/markup shown | Hand calculation | Dominant formats |
|---|---|---|---|---|---|---|---|
| S1 Categorization of Data & Data Collection Methods | 10 | 0 | 7 | 3 | 4 | 0 | evaluate statements (7), choose code or function (3) |
| S2 Data Types, Data Structures & File Formats in Python | 14 | 0 | 1 | 13 | 14 | 0 | predict code output (11), choose code or function (2) |
| S3 Data Preparation & Combining & Organizing Data | 12 | 0 | 0 | 12 | 12 | 0 | predict code output (12) |
| S4 Exploratory Data Analysis | 12 | 0 | 7 | 5 | 0 | 4 | interpret output or figure (7), calculate value (4) |
| S5 Representation & Analysis of Geographical Data | 6 | 2 | 4 | 0 | 3 | 0 | evaluate statements (4), interpret output or figure (1) |
| S6 Statistical Hypothesis Testing | 6 | 1 | 2 | 3 | 0 | 3 | calculate value (3), interpret output or figure (2) |
| S7 Regression Analysis | 9 | 0 | 6 | 3 | 0 | 3 | calculate value (3), evaluate statements (3) |
| S8 Classification Analysis | 9 | 1 | 5 | 3 | 0 | 3 | interpret output or figure (4), calculate value (3) |
| S9 Cluster Analysis | 6 | 2 | 4 | 0 | 0 | 0 | interpret output or figure (4), definition or fact (2) |
| S10 Text Mining & Sentiment Analysis | 6 | 0 | 1 | 5 | 1 | 1 | other (3), calculate value (1) |
| **Total** | **90** | **6** (7%) | **37** (41%) | **47** (52%) | **34** | **14** | |

- **FACT:** Code or markup appears almost only in S1–S3 (HS23: Q2, Q5–Q12, Q18; HS24: Q3–Q12, Q18, Q30; HS25: Q2–Q12, Q18). From Q13 on, questions use figures, tables or given numbers.
- **FACT:** Negated stems ("Which statement is NOT correct?"): HS23 12, HS24 15, HS25 10, so **37/90 (41 %)**. Combination items ("which of statements 1–4 are correct"): HS23 Q25, HS25 Q16, Q25.
- **FACT:** The same 5 hand calculations appear in all three exams: sample SD (n−1), relative frequencies from a contingency table, expected frequencies for chi-squared, prediction from a regression equation, and a confusion-matrix metric (accuracy HS23 / precision-recall-F1 HS24 / recall HS25).
- **ASSESSMENT:** "Reproduction" is almost absent. Even definition topics (scales, WKT, k-means) are asked as "which statement is NOT correct" about a given table or snippet. Learn **rules you can apply**, not definitions to recite.

### 4.5 Pattern P4: near-identical repeats across years (FACT)
- **Text preprocessing:** HS23 Q29 and HS24 Q29 use the **same sentence** ("Paul wanted a better job."). HS25 Q29 uses the same format with "Lisa bought an expensive car."
- **R² = 1 ⇒ r?** Asked almost word for word in HS23 Q23 and HS25 Q22.
- **GeoAdmin geocoding code in parts (1)–(4):** HS23 Q18 and HS25 Q18.
- **XPath on a `div/ul/li class='product'` page:** HS23 Q2 and HS24 Q3. HS25 Q2 uses an HTML table instead.
- **Likert = ordinal:** HS23 Q4 and HS24 Q2. **Scales table:** Q1 in all three exams (smartphones / cars / bicycles).
- **Random-forest statements (bootstrap sample, random feature subset):** HS23 Q25 and HS25 Q25.
- **Silhouette plot + table of average silhouette scores for k = 3–6:** HS23 Q28 and HS25 Q28.
- **One contingency table reused in two questions:** HS24 Q14/Q19 and HS25 Q13/Q20 (relative frequencies, then expected frequencies).

### 4.6 Pattern P5: questions taken from the exercises (FACT, found by the verification pass)
| Exam question | Course material it mirrors |
|---|---|
| HS24 Q17 (Winterthur, Theaterstrasse 17, Swiss vs WGS84 coordinates) | `Excercises_Week_05.pdf` T1 a)–c) (same address, same coordinate tool) |
| HS23 Q18, HS25 Q18 (GeoAdmin SearchServer code) | `Week_05/geocoding_addresses.ipynb` |
| HS24 Q12 (regex `re.findall('[0-9]+', …)` + try/except loop) | `Week_02/apartments_data_preparation_*.ipynb` |
| HS25 Q11 (`str.contains(pattern).astype(int)` dummy) | `Week_03/apartments_data_preparation_zuerich.ipynb` ("luxurious" example) |
| HS25 Q3 (Overpass API, `requests.get`, `json.dump`) | `Week_01/getting_supermarket_locations_WebAPI.ipynb` |
| HS24 Q7/Q8 (OSM Coop JSON, `pd.read_json`) | `Week_02/supermarkets.json`, `supermarkets_data.ipynb` |
| HS23 Q20, HS24 Q19, HS25 Q20 (expected frequencies) | `Excercises_Week_07.pdf` T2 c) (write a function for expected frequencies); `analysis_of_contingency_tables.ipynb` |
| HS24 Q30 (`WordNetLemmatizer`, `pos='v'`) | `Week_11/NLP_text_preprocessing.ipynb`, `NLP_hotel_reviews_sentiment_prediction.ipynb` |
| HS25 Q16 (grouped boxplot of smartphone prices by brand) | `Week_LC/LC_06` T2 (grouped boxplots, `orient='h'`) |
| HS23 Q28, HS24 Q28, HS25 Q28 (silhouette plots) | `Week_10/silhouette.py`, `k-means_clustering.ipynb` |

### 4.7 Pattern P6: what is never asked (FACT, 0 of 90 questions)
Neural networks (W12), Flask/Dash/Colab (W13), ANOVA, simulation/sampling/bootstrapping, SQL/SQLite, regression trees / RF regression, matplotlib/seaborn code, QGIS/folium/KML, sentiment classification models, POS tagging, the process model / business objectives, and Jupyter tooling.

### 4.8 Trend HS23 → HS25 (FACT; interpretation is ASSESSMENT)
- The regression prediction question moved from a **simple** equation (HS23 Q21, HS24 Q21) to a **multiple** one with 3 variables (HS25 Q23). Coefficient interpretation has used multiple regression since HS24 (HS24 Q22, HS25 Q21).
- New in HS25: a Web API code question (Q3), a TF-IDF matrix (Q30), grouped boxplots (Q16), and 3 data-structure questions in a row (Q5–Q7).
- No t-test in HS25; its hypothesis-testing section had a correlation heatmap (Q19) and chi-squared (Q20).
- **ASSESSMENT:** expect multiple regression, TF-IDF and more Python data-structure questions. Don't drop t-tests (2/3 exams, and still in the Module description).

### 4.9 Patterns I looked for and did **not** find
- **Distribution of answer letters:** can't be analysed, because there is no answer key.
- **Question order within a section** changes between years. There is no fixed position per type, except that the scales-of-measurement question is always Q1 and the two text-mining types are always Q29 and Q30.

### 4.10 Interim result, Step 3
**FACT:** The exam is highly predictable: a fixed 10-section blueprint, 24 recurring question types (94 % of questions), a code-heavy first third, and interpretation or hand calculation afterwards. **FACT:** Weeks 12–13 and several practised techniques (ANOVA, SQL, RT, simulation) have never been tested.

---

## 5. Step 4: Study plan

### A) Important topics according to the teaching materials
Ranked by depth in the repo (FACT, counts from 3.1/3.2; no slides available):

| Rank | Topic | Evidence of depth |
|---|---|---|
| 1 | Data preparation & cleaning (regex, missing values, duplicates, `.loc`) | Core W2 + W3 (SC 27 + 19 subtasks), secondary in 7 more weeks |
| 2 | Python data types/structures, file formats, import/export, SQLite | W2: 4 SC tasks / 27 subtasks, 8 notebooks / 181 cells |
| 3 | EDA (describe, quantiles, histogram/boxplot, heatmap) | W4: 4 SC tasks / 14 subtasks, 114 cells; graphical EDA used in 10/13 weeks |
| 4 | Combining & organizing (merge, pivot_table, groupby) | W3 SC T2–T3 (14 subtasks); pivot_table in 5 weeks |
| 5 | Hypothesis testing (t-test, ANOVA, chi-squared, Pearson + p-values) | W6 + W7: 6 SC tasks / 28 subtasks, 150 cells |
| 6 | k-means (elbow, silhouette) | W10: 15 subtasks, 77 cells |
| 7 | Text mining (preprocessing, BoW, TF-IDF, lemmatization) | W11: 119 cells (8 SC subtasks) |
| 8 | Regression (OLS, R², coefficients; RT/RF) | W8: 10 SC + 9 LC subtasks, 82 cells |
| 9 | Classification (tree, RF, confusion matrix, ROC/AUC) | W9: 8 SC subtasks + 6 LC tasks, 66 cells |
| 10 | Geodata (geocoding API, coordinates, QGIS) | W5: 15 subtasks (10 of them QGIS) |
| (11) | NN (W12: 17 subtasks) and Flask/Dash (W13: 16 subtasks) | Heavily practised, but see B and C |

### B) Important topics according to the old MEPs (x/3 exams, number of questions)
| Rank | Question type | x/3 exams | #Q (HS23/HS24/HS25) | Weighted Q per exam | Where (exam Q, PDF page) |
|---|---|---|---|---|---|
| 1 | R11 Combining & organizing: concat, merge, groupby, pivot_table (predict output/shape) | 3/3 | 8 (3/3/2) | 2.60 | HS23 Q9,10,12 (p.9,9,11); HS24 Q9,10,11 (p.9,10,11); HS25 Q10,12 (p.11,12) |
| 2 | R06 Data structures list/tuple/set/dict: literals, indexing, keys()/values()/get() | 3/3 | 6 (2/1/3) | 2.07 | HS23 Q6,7 (p.7,8); HS24 Q5 (p.7); HS25 Q5,6,7 (p.8,8,8) |
| 3 | R01 Scales of measurement (nominal/ordinal/interval/ratio) & Likert scale | 3/3 | 5 (2/2/1) | 1.60 | HS23 Q1,4 (p.5,6); HS24 Q1,2 (p.5,5); HS25 Q1 (p.5) |
| 4 | R07 File formats JSON/XML (structure, semi-structured) & choosing pd.read_* / read_json | 3/3 | 5 (2/2/1) | 1.60 | HS23 Q3,8 (p.6,8); HS24 Q7,8 (p.8,8); HS25 Q8 (p.9) |
| 5 | R14 Histogram & boxplot interpretation (quartiles, IQR, skewness, mean vs median) | 3/3 | 4 (1/1/2) | 1.40 | HS23 Q15 (p.13); HS24 Q13 (p.13); HS25 Q15,16 (p.14,15) |
| 6 | R03 Web scraping: XPath expression for an HTML element | 3/3 | 3 (1/1/1) | 1.00 | HS23 Q2 (p.5); HS24 Q3 (p.6); HS25 Q2 (p.6) |
| 7 | R05 Python basic data types: output of type() on expressions | 3/3 | 3 (1/1/1) | 1.00 | HS23 Q5 (p.7); HS24 Q4 (p.6); HS25 Q4 (p.7) |
| 8 | R09 Filtering & cleaning: dropna, drop_duplicates, .loc with & / |, .iloc | 3/3 | 3 (1/1/1) | 1.00 | HS23 Q11 (p.10); HS24 Q6 (p.7); HS25 Q9 (p.10) |
| 9 | R12 Sample standard deviation by hand (n-1) | 3/3 | 3 (1/1/1) | 1.00 | HS23 Q14 (p.12); HS24 Q16 (p.14); HS25 Q14 (p.13) |
| 10 | R13 Contingency table: relative (joint/conditional) frequencies | 3/3 | 3 (1/1/1) | 1.00 | HS23 Q13 (p.12); HS24 Q14 (p.13); HS25 Q13 (p.13) |
| 11 | R15 Correlation: Pearson r, correlation matrix / heatmap interpretation | 3/3 | 3 (1/1/1) | 1.00 | HS23 Q16 (p.14); HS24 Q15 (p.14); HS25 Q19 (p.17) |
| 12 | R17 GIS vector data formats: WKT vs GeoJSON (Point/LineString/Polygon) | 3/3 | 3 (1/1/1) | 1.00 | HS23 Q17 (p.15); HS24 Q18 (p.15); HS25 Q17 (p.15) |
| 13 | R18 Geocoding with GeoAdmin API; Swiss LV95 vs WGS84 coordinates | 3/3 | 3 (1/1/1) | 1.00 | HS23 Q18 (p.15); HS24 Q17 (p.15); HS25 Q18 (p.16) |
| 14 | R20 Chi-squared test of independence: expected frequencies | 3/3 | 3 (1/1/1) | 1.00 | HS23 Q20 (p.16); HS24 Q19 (p.16); HS25 Q20 (p.18) |
| 15 | R24 Linear regression: prediction from a (multiple) regression equation | 3/3 | 3 (1/1/1) | 1.00 | HS23 Q21 (p.17); HS24 Q21 (p.18); HS25 Q23 (p.20) |
| 16 | R25 Linear regression: interpretation of coefficients/intercept (ceteris paribus) | 3/3 | 3 (1/1/1) | 1.00 | HS23 Q22 (p.17); HS24 Q22 (p.18); HS25 Q21 (p.19) |
| 17 | R26 R-squared: definition, 1-SSE/SST, R^2 = r^2 in simple regression | 3/3 | 3 (1/1/1) | 1.00 | HS23 Q23 (p.18); HS24 Q23 (p.19); HS25 Q22 (p.19) |
| 18 | R28 Confusion matrix metrics by hand: accuracy, precision, recall, F1 | 3/3 | 3 (1/1/1) | 1.00 | HS23 Q24 (p.18); HS24 Q25 (p.20); HS25 Q24 (p.20) |
| 19 | R29 ROC curve & AUC interpretation | 3/3 | 3 (1/1/1) | 1.00 | HS23 Q26 (p.19); HS24 Q26 (p.20); HS25 Q26 (p.21) |
| 20 | R30 Classification trees (Gini impurity) & random forest mechanics (bootstrap, feature subsets) | 3/3 | 3 (1/1/1) | 1.00 | HS23 Q25 (p.18); HS24 Q24 (p.19); HS25 Q25 (p.21) |
| 21 | R31 k-means: algorithm properties, choosing k, elbow method (WCSS/inertia) | 3/3 | 3 (1/1/1) | 1.00 | HS23 Q27 (p.19); HS24 Q27 (p.21); HS25 Q27 (p.22) |
| 22 | R32 Silhouette plots & average silhouette scores | 3/3 | 3 (1/1/1) | 1.00 | HS23 Q28 (p.20); HS24 Q28 (p.22); HS25 Q28 (p.23) |
| 23 | R33 Text preprocessing pipeline result (lowercase, punctuation, tokens, stopwords, lemma) | 3/3 | 3 (1/1/1) | 1.00 | HS23 Q29 (p.21); HS24 Q29 (p.23); HS25 Q29 (p.24) |
| 24 | R34 Text representation: bag-of-words, lemmatizer output, TF-IDF matrix | 3/3 | 3 (1/1/1) | 1.00 | HS23 Q30 (p.21); HS24 Q30 (p.23); HS25 Q30 (p.24) |
| 25 | R10 Regex & string processing (re.findall, str.contains, type conversion) | 2/3 | 2 (0/1/1) | 0.73 | HS24 Q12 (p.12); HS25 Q11 (p.12) |
| 26 | R21 t-tests (unpaired vs paired; output, H0, alpha, p-value, Type I error) | 2/3 | 2 (1/1/0) | 0.60 | HS23 Q19 (p.16); HS24 Q20 (p.17) |
| 27 | R04 Web API request code (requests.get, JSON response, Overpass API) | 1/3 | 1 (0/0/1) | 0.40 | HS25 Q3 (p.7) |

**Never tested (0/90 questions):** R02 Data analytics process model, business objectives, choosing data sources; R08 SQL databases from Python (sqlite3, SQL queries, to_sql/read_sql); R16 Graphical EDA: plotting code (matplotlib/seaborn syntax, plot choice); R19 GIS tools: folium maps, QGIS choropleth/nearest neighbour, KML/Google Earth; R22 ANOVA (one-way, f_oneway); R23 Simulation, random sampling, bootstrapping (population vs sample); R27 Regression trees & random-forest regression (RT); R35 Sentiment analysis as classification (TF-IDF features + classifier), POS tagging; R36 Neural networks (perceptron, backprop, CNN, Keras); R37 Presenting & sharing results: Flask, Plotly Dash, Colab, saving models; R38 Jupyter/Codespaces tooling, magics, general Python syntax

### C) Categorization of all topics + time allocation (20 h)

**Thresholds (applied mechanically by script, `table_c.py` logic):**
- 🟢 **Important:** appears in **≥ 2 of 3 MEPs (≥ 67 %)** **AND** is taught (core or secondary in ≥ 1 exercise task/notebook, **or** explicitly listed in the HS26 Module description / Semester program when the only teaching source is the missing slides; these are marked ⚠️).
- 🟠 **Neutral:** appears in **exactly 1 of 3** MEPs, **or** 0/3 MEPs but **core in at least one small-class exercise task** ("only in teaching, but clearly").
- 🔴 **Unimportant:** 0/3 MEPs **and** only secondary/mentioned or large-class-only in teaching, **or explicitly excluded** from the exam by a course document.
- **Hours** ∝ weighted questions per exam (~0.5 h per expected question), adjusted up for code-output and calculation types that need practice and down for single-rule types. Orange topics get 0–0.25 h. Sum = 20 h (checked by script).
- *Tested level* counts come from the verified classification of the 90 questions (Repro = reproduction, Underst. = understanding, Appl. = application).

| # | Topic / question type | Cat. | MEP freq. (x/3) | #Q total (HS23/24/25) | Weighted Q per exam | Teaching depth (repo) | Tested level (count) | Study h | Sources (MEP Q / PDF page) |
|---|---|---|---|---|---|---|---|---|---|
| R01 | Scales of measurement (nominal/ordinal/interval/ratio) & Likert scale | 🟢 | 3/3 | 5 (2/2/1) | 1.60 | none in repo ⚠️ (W1 program lists "Categorization of Data"; slides only) | Underst. 5 | 0.75 | HS23 Q1,4 (p.5,6); HS24 Q1,2 (p.5,5); HS25 Q1 (p.5) |
| R02 | Data analytics process model, business objectives, choosing data sources | 🟠 | 0/3 | 0 (0/0/0) | 0.00 | W1 SC T1–T2 (5 sub); process-model figure in all 13 exercise PDFs | — (never tested) | 0.25 | — |
| R03 | Web scraping: XPath expression for an HTML element | 🟢 | 3/3 | 3 (1/1/1) | 1.00 | none in repo ⚠️ (XPath absent; related: W1 SC T3 Chrome Web-Scraper, 13 sub) | Appl. 3 | 0.50 | HS23 Q2 (p.5); HS24 Q3 (p.6); HS25 Q2 (p.6) |
| R04 | Web API request code (requests.get, JSON response, Overpass API) | 🟠 | 1/3 | 1 (0/0/1) | 0.40 | W1 SC T3 (Overpass nb); W4 LC T1 (yfinance); W5 SC T1 (GeoAdmin) | Underst. 1 | 0.25 | HS25 Q3 (p.7) |
| R05 | Python basic data types: output of type() on expressions | 🟢 | 3/3 | 3 (1/1/1) | 1.00 | no dedicated task (W2 intro; LC_01 T2 %who) | Appl. 3 | 0.50 | HS23 Q5 (p.7); HS24 Q4 (p.6); HS25 Q4 (p.7) |
| R06 | Data structures list/tuple/set/dict: literals, indexing, keys()/values()/get() | 🟢 | 3/3 | 6 (2/1/3) | 2.07 | no dedicated task (LC_02 T2 dict; numpy arrays W10/W12) | Appl. 6 | 1.00 | HS23 Q6,7 (p.7,8); HS24 Q5 (p.7); HS25 Q5,6,7 (p.8,8,8) |
| R07 | File formats JSON/XML (structure, semi-structured) & choosing pd.read_* / read_json | 🟢 | 3/3 | 5 (2/2/1) | 1.60 | W2 SC T2 (8 sub), SC T3 (11 sub); LC_02 T1–T3 | Appl. 3, Underst. 2 | 0.75 | HS23 Q3,8 (p.6,8); HS24 Q7,8 (p.8,8); HS25 Q8 (p.9) |
| R08 | SQL databases from Python (sqlite3, SQL queries, to_sql/read_sql) | 🟠 | 0/3 | 0 (0/0/0) | 0.00 | W2 SC T4 (8 sub); apartments_database_Python.ipynb (23 cells) | — (never tested) | 0.25 | — |
| R09 | Filtering & cleaning: dropna, drop_duplicates, .loc with & / |, .iloc | 🟢 | 3/3 | 3 (1/1/1) | 1.00 | W2 SC T3 e); W3 SC T1 (5 sub); LC_03 T3; dropna in 11 nb files | Appl. 3 | 0.50 | HS23 Q11 (p.10); HS24 Q6 (p.7); HS25 Q9 (p.10) |
| R10 | Regex & string processing (re.findall, str.contains, type conversion) | 🟢 | 2/3 | 2 (0/1/1) | 0.73 | W2 SC T1 (9 regex), W3 SC T1; LC_02 T3, LC_03 T1–T2 | Appl. 2 | 0.50 | HS24 Q12 (p.12); HS25 Q11 (p.12) |
| R11 | Combining & organizing: concat, merge, groupby, pivot_table (predict output/shape) | 🟢 | 3/3 | 8 (3/3/2) | 2.60 | W3 SC T2 (7 sub), SC T3 (7 sub); LC_03 T3; pivot_table in 5 weeks | Appl. 8 | 1.25 | HS23 Q9,10,12 (p.9,9,11); HS24 Q9,10,11 (p.9,10,11); HS25 Q10,12 (p.11,12) |
| R12 | Sample standard deviation by hand (n-1) | 🟢 | 3/3 | 3 (1/1/1) | 1.00 | no hand calculation task; .std()/describe() in W4, W6 nbs | Appl. 3 | 0.25 | HS23 Q14 (p.12); HS24 Q16 (p.14); HS25 Q14 (p.13) |
| R13 | Contingency table: relative (joint/conditional) frequencies | 🟢 | 3/3 | 3 (1/1/1) | 1.00 | W4 nb pd.crosstab; W7 SC T1–T2 contingency tables | Appl. 2, Underst. 1 | 0.25 | HS23 Q13 (p.12); HS24 Q14 (p.13); HS25 Q13 (p.13) |
| R14 | Histogram & boxplot interpretation (quartiles, IQR, skewness, mean vs median) | 🟢 | 3/3 | 4 (1/1/2) | 1.40 | W4 SC T2–T4 (10 sub), LC_04 T2–T3; W6/LC_06 grouped boxplots | Underst. 4 | 0.75 | HS23 Q15 (p.13); HS24 Q13 (p.13); HS25 Q15,16 (p.14,15) |
| R15 | Correlation: Pearson r, correlation matrix / heatmap interpretation | 🟢 | 3/3 | 3 (1/1/1) | 1.00 | W7 SC T3 (4 sub), LC_07 T2 (3 sub); W4 nb heatmap | Underst. 3 | 0.50 | HS23 Q16 (p.14); HS24 Q15 (p.14); HS25 Q19 (p.17) |
| R16 | Graphical EDA: plotting code (matplotlib/seaborn syntax, plot choice) | 🟠 | 0/3 | 0 (0/0/0) | 0.00 | W4 SC T1 (graphics_with_matplotlib.ipynb, 26 cells), SC T4 | — (never tested) | 0.00 | — |
| R17 | GIS vector data formats: WKT vs GeoJSON (Point/LineString/Polygon) | 🟢 | 3/3 | 3 (1/1/1) | 1.00 | none in repo ⚠️ (WKT/GeoJSON absent; related: W5 QGIS shapefiles) | Repro 2, Underst. 1 | 0.25 | HS23 Q17 (p.15); HS24 Q18 (p.15); HS25 Q17 (p.15) |
| R18 | Geocoding with GeoAdmin API; Swiss LV95 vs WGS84 coordinates | 🟢 | 3/3 | 3 (1/1/1) | 1.00 | W5 SC T1 (5 sub; geocoding_addresses.ipynb; Swiss vs WGS84 coords) | Underst. 3 | 0.50 | HS23 Q18 (p.15); HS24 Q17 (p.15); HS25 Q18 (p.16) |
| R19 | GIS tools: folium maps, QGIS choropleth/nearest neighbour, KML/Google Earth | 🟠 | 0/3 | 0 (0/0/0) | 0.00 | W5 SC T2–T3 (10 sub, QGIS videos); LC_05 T1–T3 (KML) | — (never tested) | 0.00 | — |
| R20 | Chi-squared test of independence: expected frequencies | 🟢 | 3/3 | 3 (1/1/1) | 1.00 | W7 SC T1 (3 sub), SC T2 (7 sub, expected freq. by own function); LC_07 T1 | Appl. 3 | 0.50 | HS23 Q20 (p.16); HS24 Q19 (p.16); HS25 Q20 (p.18) |
| R21 | t-tests (unpaired vs paired; output, H0, alpha, p-value, Type I error) | 🟢 | 2/3 | 2 (1/1/0) | 0.60 | W6 SC T2 (5 sub; ttest_ind only — paired test not in repo ⚠️) | Repro 1, Underst. 1 | 0.50 | HS23 Q19 (p.16); HS24 Q20 (p.17) |
| R22 | ANOVA (one-way, f_oneway) | 🟠 | 0/3 | 0 (0/0/0) | 0.00 | W6 SC T3 (5 sub), LC_06 T3; analysis_of_variance_ANOVA.ipynb | — (never tested) | 0.25 | — |
| R23 | Simulation, random sampling, bootstrapping (population vs sample) | 🟠 | 0/3 | 0 (0/0/0) | 0.00 | W6 SC T1 (4 sub), LC_06 T1; simulations also LC_07/LC_09 | — (never tested) | 0.25 | — |
| R24 | Linear regression: prediction from a (multiple) regression equation | 🟢 | 3/3 | 3 (1/1/1) | 1.00 | W8 SC T1 (4 sub), LC_08 T2; linear_regression.ipynb (31 cells) | Appl. 3 | 0.25 | HS23 Q21 (p.17); HS24 Q21 (p.18); HS25 Q23 (p.20) |
| R25 | Linear regression: interpretation of coefficients/intercept (ceteris paribus) | 🟢 | 3/3 | 3 (1/1/1) | 1.00 | W8 SC T1 d) (coef, P>|t|); linear_regression.ipynb cell 24 | Underst. 3 | 0.50 | HS23 Q22 (p.17); HS24 Q22 (p.18); HS25 Q21 (p.19) |
| R26 | R-squared: definition, 1-SSE/SST, R^2 = r^2 in simple regression | 🟢 | 3/3 | 3 (1/1/1) | 1.00 | W8 SC T1 (compare R²); linear_regression.ipynb cells 9, 24 (SSE/SST ⚠️ not in repo) | Underst. 3 | 0.50 | HS23 Q23 (p.18); HS24 Q23 (p.19); HS25 Q22 (p.19) |
| R27 | Regression trees & random-forest regression (RT) | 🟠 | 0/3 | 0 (0/0/0) | 0.00 | W8 SC T2 (6 sub), LC_08 T3; regression_trees_random_forest.ipynb | — (never tested) | 0.25 | — |
| R28 | Confusion matrix metrics by hand: accuracy, precision, recall, F1 | 🟢 | 3/3 | 3 (1/1/1) | 1.00 | W9 SC T1–T2 (confusion_matrix, classification_report); formulas ⚠️ not in repo | Appl. 3 | 0.75 | HS23 Q24 (p.18); HS24 Q25 (p.20); HS25 Q24 (p.20) |
| R29 | ROC curve & AUC interpretation | 🟢 | 3/3 | 3 (1/1/1) | 1.00 | W9 SC T1 (RocCurveDisplay, AUC) | Underst. 3 | 0.50 | HS23 Q26 (p.19); HS24 Q26 (p.20); HS25 Q26 (p.21) |
| R30 | Classification trees (Gini impurity) & random forest mechanics (bootstrap, feature subsets) | 🟢 | 3/3 | 3 (1/1/1) | 1.00 | W9 SC T1 (tree + RF), LC_09 T3/T5/T6; Gini ⚠️ not in repo | Underst. 2, Repro 1 | 0.50 | HS23 Q25 (p.18); HS24 Q24 (p.19); HS25 Q25 (p.21) |
| R31 | k-means: algorithm properties, choosing k, elbow method (WCSS/inertia) | 🟢 | 3/3 | 3 (1/1/1) | 1.00 | W10 SC T1 (8 sub), SC T2 (7 sub); LC_10 T3 (elbow) | Repro 2, Underst. 1 | 0.50 | HS23 Q27 (p.19); HS24 Q27 (p.21); HS25 Q27 (p.22) |
| R32 | Silhouette plots & average silhouette scores | 🟢 | 3/3 | 3 (1/1/1) | 1.00 | W10 SC T1 c), SC T2 g); silhouette.py | Underst. 3 | 0.50 | HS23 Q28 (p.20); HS24 Q28 (p.22); HS25 Q28 (p.23) |
| R33 | Text preprocessing pipeline result (lowercase, punctuation, tokens, stopwords, lemma) | 🟢 | 3/3 | 3 (1/1/1) | 1.00 | W11 SC T1 (6 sub); NLP_text_preprocessing.ipynb cell 5 (step list) | Appl. 3 | 0.50 | HS23 Q29 (p.21); HS24 Q29 (p.23); HS25 Q29 (p.24) |
| R34 | Text representation: bag-of-words, lemmatizer output, TF-IDF matrix | 🟢 | 3/3 | 3 (1/1/1) | 1.00 | W11 SC T1 d) (CountVectorizer DTM); TF/IDF cells 23–27 | Appl. 2, Underst. 1 | 0.75 | HS23 Q30 (p.21); HS24 Q30 (p.23); HS25 Q30 (p.24) |
| R35 | Sentiment analysis as classification (TF-IDF features + classifier), POS tagging | 🟠 | 0/3 | 0 (0/0/0) | 0.00 | W11 SC T2 (hotel reviews: TF-IDF + RandomForest); POS in SC T1 | — (never tested) | 0.00 | — |
| R36 | Neural networks (perceptron, backprop, CNN, Keras) | 🔴 | 0/3 | 0 (0/0/0) | 0.00 | W12 SC T1–T4 (17 sub), LC_12 T1–T5; LC_11 (CBOW) — excluded: LC_11 Task 1 | — (never tested) | 0.00 | — |
| R37 | Presenting & sharing results: Flask, Plotly Dash, Colab, saving models | 🟠 | 0/3 | 0 (0/0/0) | 0.00 | W13 SC T1–T3 (16 sub), LC_13 T1–T3 | — (never tested) | 0.00 | — |
| R38 | Jupyter/Codespaces tooling, magics, general Python syntax | 🔴 | 0/3 | 0 (0/0/0) | 0.00 | LC_01 T1–T5 only (13 sub) | — (never tested) | 0.00 | — |
| X1 | Timed simulation of the 3 old MEPs (3 × 60 min) + checking answers against notebooks | — | — | — | — | — | — | 3.00 | — |
| X2 | Writing the 2-page summary (section D) | — | — | — | — | — | — | 1.00 | — |
| | **Total** | | | **90** | **30.00** | | | **20.00** | |

**Hours by category:** 🟢 14.5 h (26 types), 🟠 1.5 h (10), 🔴 0 h (2), practice 3 h, summary 1 h = **20 h**.

**Suggested order (ASSESSMENT):**
1. **1 h:** HS25 under exam conditions (60 min, open book) as a diagnostic, to find your weak spots.
2. **14.5 h:** 🟢 topics in exam order S1→S10. For each, use the listed MEP questions plus the linked notebook.
3. **1 h:** write the 2-page summary.
4. **1.5 h:** 🟠 quick pass (ANOVA, SQL, RT, simulation, Web API: one decision rule each).
5. **2 h:** HS24 and HS23 under exam conditions, using your summary, then fix the remaining gaps.

Total: 1 + 14.5 + 1 + 1.5 + 2 = **20 h**.

### D) The 2-page summary: what must be on it

**Principle (ASSESSMENT):** you have 60 min for 30 questions, so **2 min per question**. The sheet should hold what you *look up or calculate* under time pressure: formulas, decision rules, and "what does this code return" rules. Definitions you can reason out don't need space. The order below follows the exam sections, so you can scan it top to bottom alongside the paper.

**Page 1: Python, data, EDA (S1–S4 ≈ 16 Q, ~53 % of points)**
| # | Put on the sheet | Why (frequency) | Source for the content |
|---|---|---|---|
| 1 | **Scales of measurement decision table** (nominal / ordinal / interval / ratio: order? equal distances? absolute zero?) + **Likert = ordinal** | R01: 5 Q, 3/3 exams, always Q1 | ⚠️ not in repo → slides. The rules are visible in the MEP options (HS23 Q1 a–d, Q4) |
| 2 | **XPath syntax:** `/html/body/div/ul/li[1]/text()`, 1-based index, no `head` in the body path, `//`, `[@id='…']`, `td[2]` | R03: 3/3 | ⚠️ slides. Example paths in HS23 Q2, HS24 Q3, HS25 Q2 |
| 3 | **Python type rules:** `/` → float; comparisons, `isinstance`, `and`/`or` → bool; `len()` → int; `str + str` → str; `int(str(71))` → int | R05: 3/3 (Appl.) | HS23 Q5, HS24 Q4, HS25 Q4 |
| 4 | **Container cheat sheet:** `()` tuple, `[]` list, `{a,b}` set (duplicates removed), `{k:v}` dict; `list(d.keys())[i]`, `list(d.values())[i]`, `d.get(k)` | R06: 6 Q, 3/3 | HS25 Q5–Q7; HS23 Q6–Q7 |
| 5 | **JSON vs XML vs CSV** recognition + `pd.read_json` / `read_csv` / `read_xml` / `read_html` (read_json returns a DataFrame) | R07: 5 Q, 3/3 | `Excercises_Week_02.pdf` T3 b) ("A json-file has key:value pairs"); `supermarkets_data.ipynb` |
| 6 | **pandas "what comes out":** `concat` stacks rows (rows add up, columns = union); `merge` = **inner** by default (only matching keys); `groupby(...).mean()`; `pivot_table` default aggfunc = mean; `dropna()` drops rows with ≥ 1 NaN; `drop_duplicates()` compares **all** columns; `&`/`\|` need parentheses; `.loc` = labels/conditions, `.iloc` = positions | R09 + R11: 11 Q, 3/3 | `dropna`: `apartments_data_preparation_zuerich.ipynb` cell 30; merge key: `combining_and_organizing_data.ipynb` cell 13. Defaults for `merge`/`pivot_table` are pandas behaviour (⚠️ check the notebooks) |
| 7 | **Regex:** `re.findall('[0-9]+', s)` returns a list of strings; `str.contains('(A)\|(B)')` gives a bool (→ `.astype(int)` for a 0/1 dummy); `try/except IndexError` → None | R10: 2/3 | `Excercises_Week_02.pdf` T1; `Week_02/03` apartment notebooks |
| 8 | **Sample SD formula** s = √(Σ(x−x̄)²/(n−1)) + calculator keystrokes | R12: 3/3 | HS24 Q16 (verified: mean 910, SS 127,000, /4, √ = 178.19) |
| 9 | **Contingency table:** joint % = cell/N; row % = cell/row total; column % = cell/column total | R13: 3/3 | HS23 Q13, HS24 Q14, HS25 Q13 |
| 10 | **Boxplot/histogram rules:** IQR = Q3 − Q1; whiskers/outliers; mean > median ⇒ right-skewed | R14: 4 Q, 3/3 | `Week_04/exploratory_data_analysis_apartment_data.ipynb` (quantiles, `.skew()`); ⚠️ the 1.5×IQR rule and skew wording are from the slides |
| 11 | **Correlation reading:** sign = direction, \|r\| = strength; significance via p-value | R15: 3/3 | `Week_07/correlation_analysis.ipynb` (`pearsonr` → r, p); LC_07 cell 13 (r = cov/√(var·var)) |

**Page 2: Geo, statistics, models, text (S5–S10 ≈ 14 Q, ~47 % of points)**
| # | Put on the sheet | Why | Source |
|---|---|---|---|
| 12 | **WKT vs GeoJSON** side by side (`POINT (30 10)`, `LINESTRING`, `POLYGON ((…))` with a hole vs `{"type":"Polygon","coordinates":[[[…]]]}`) | R17: 3/3 | ⚠️ slides. Snippets in HS23 Q17, HS24 Q18, HS25 Q17 |
| 13 | **Coordinates:** Swiss LV95 (e.g. 2 697 110 / 1 262 228, metres) vs WGS84 (lat 47.50, lon 8.73, degrees); GeoAdmin API code parts (base_url, params `searchText`/`origins=address`/`type=locations`, `requests.get`, `r.json()`) | R18: 3/3 | `Excercises_Week_05.pdf` T1 a); `geocoding_addresses.ipynb` cells 5–7; HS24 Q17 |
| 14 | **Expected frequency** E = (row total × column total) / N; chi-squared H0 = independence; `chi2_contingency` → (stat, p, dof, expected) | R20: 3/3 | `Week_07/analysis_of_contingency_tables.ipynb` cells 22–24; `Excercises_Week_07.pdf` T2 c) |
| 15 | **Test decision rule:** p < α (0.05) → reject H0; Type I error = rejecting a true H0; unpaired (independent groups, `ttest_ind`) vs paired (same subjects); ANOVA = more than 2 groups (`f_oneway`), doesn't say which group differs | R21 (+R22) | `unpaired_two_sample_t-test.ipynb` cell 10; `analysis_of_variance_ANOVA.ipynb` cell 12; ⚠️ paired test and Type I wording are from the slides |
| 16 | **Regression:** ŷ = b0 + b1x1 + b2x2 (+…) as a plug-in template; bᵢ = change in ŷ per unit xᵢ, **other variables held constant**; `P>\|t\| < 0.05` → significant; R² = explained share of variance = 1 − SSE/SST; in simple regression R² = r² ⇒ R² = 1 ⇔ r = ±1 | R24–R26: 9 Q, 3/3 | `Week_08/linear_regression.ipynb` cells 9, 24; `Excercises_Week_08.pdf` T1 d); SSE/SST in HS24 Q23 |
| 17 | **Confusion matrix:** accuracy = (TP+TN)/all; precision = TP/(TP+FP); recall = TP/(TP+FN); F1 = 2PR/(P+R) + a small layout sketch | R28: 3/3 (calculation) | `classification_report` in `Week_09/classification_analysis_titanic.ipynb`; ⚠️ formulas are from the slides |
| 18 | **ROC/AUC:** TPR vs FPR; diagonal = random (AUC 0.5); AUC 1 = perfect; higher AUC = better model | R29: 3/3 | `Week_09` notebook (`RocCurveDisplay`); ⚠️ rules are from the slides |
| 19 | **Trees & RF:** Gini = 1 − Σpᵢ² (0 = pure node); RF = each tree gets a **bootstrap sample of rows** + a **random subset of features** (sklearn classifier default `max_features='sqrt'`) | R30: 3/3 | Gini formula in HS24 Q24 options; RF defaults quoted in HS25 Q25; ⚠️ slides |
| 20 | **k-means:** minimises within-cluster sum of squares (inertia/WCSS); elbow = bend in WCSS vs k; k-means (unsupervised, k clusters) ≠ kNN (supervised) | R31: 3/3 | `k-means_clustering.ipynb` cells 8, 13; HS25 Q27 |
| 21 | **Silhouette:** value per point in [−1, 1]; the average is the dashed line; higher average = better separation; compare with the elbow k | R32: 3/3 | `Week_10/silhouette.py`; `Excercises_Week_10.pdf` T2 g); ⚠️ the [−1, 1] range and "bars below the average" rule are from the slides |
| 22 | **Text preprocessing order from class:** lowercase → remove punctuation → tokenize → remove stopwords → lemmatize (+ one worked example sentence) | R33: 3/3 | `Week_11/NLP_text_preprocessing.ipynb` cell 5 |
| 23 | **BoW / TF-IDF / lemmatizer:** BoW = counts per vocabulary word; TF = count/len(doc); IDF = log10(N/df), so with the class formula a word in every doc gets IDF = log10(1) = 0, i.e. a near-zero TF-IDF (HS25 Q30: "the" ≈ 0.01–0.03); TF-IDF = TF × IDF; `WordNetLemmatizer().lemmatize(w, pos='v'/'n'/'a')` | R34: 3/3 | Same notebook, cells 17–27 |

**Left off the sheet on purpose (ASSESSMENT):** NN, Flask/Dash, SQL syntax, matplotlib syntax, QGIS, ANOVA details beyond one line, the process model. All have 0/90 questions.

### E) Data gaps: what to send me to complete the analysis
| # | Missing / unclear | Why it matters | Exactly what is needed |
|---|---|---|---|
| 1 | **Lecture slides, Weeks 1–13** (not in the codespace) | 3/3 question types have **no repo source**: scales/Likert (R01), XPath (R03), WKT/GeoJSON (R17), Gini (R30), precision/recall/F1 formulas (R28), SSE/SST (R26), paired t-test / Type I error (R21), 1.5×IQR and skew rules (R14), silhouette range (R32). Also needed to measure teaching depth by slide count | PDFs of all slide decks (especially W1, W2, W4, W5, W6, W8, W9, W10) |
| 2 | **Answer keys for HS23/HS24/HS25** | You can't verify your practice answers | Official solutions, or your own marked answers for me to check against the notebooks |
| 3 | **Solutions to the small-class exercises** | Promised as "Exercises (with Key)" in the Module description p.2; only LC_01/LC_02 solutions exist | Solution notebooks/PDFs for Weeks 1–13 |
| 4 | **Older MEPs (HS22 or earlier) or a HS26 sample exam** | The pattern rests on 3 exams | Any additional exam PDFs |
| 5 | **HS26 exam date** | Not given in any document (Semester program p.3 "End-of-module exams – –") | Date from the exam schedule |
| 6 | Leaflet **"Utilities" / "Guidelines on Supplementary Materials"** | Which calculator is allowed (5 calculation types per exam) | The leaflet PDF |
| 7 | **"Part of the exam" wording conflict** (Semester program vs General information) | Affects how much to trust the exercises as a question source | A Moodle announcement or lecturer statement, if any |
| 8 | **NN exclusion for HS26** | The only exclusion statement is in LC_11 (a large-class task). W12 is still in the Semester program | Confirmation from the lecturers or Moodle |
| 9 | **Meaning of the file suffixes `-3`, `-2`** in `23_BA.3DA-WIN-3.pdf` / `24_BA.3DA-WIN-2.pdf` | Could mean other exam versions exist (A/B variants) | Where the files came from; other versions if they exist |
| 10 | Better scans of HS24 Q10 (faint digits), HS24 Q24 option b, HS25 Q3 (dark screenshot), HS25 Q19 (heatmap values), HS25 Q28 (axis ticks) | The rest is fully legible | Original PDFs, if available |
| 11 | `Excercises_Week_02.pdf` T1: regex expressions "highlighted in green/blue", but no highlighting survives in the PDF | The intended regex answers are not visible | The original colour version |

---

## Appendix A: All 90 questions, classified and verified
Each exam was transcribed by one agent, then **independently re-read and verified** by a second agent, which also linked the course material. Stems are paraphrased; the question text itself is in the PDFs. "Type (row)" refers to the R-numbers in table C. Levels: Repro = Reproduction, Underst. = Understanding, Appl. = Application.
### HS23 — `MEP/23_BA.3DA-WIN-3.pdf`

| Q | PDF p. | Section | Type (row) | Level | Format | Question (paraphrase) | Closest course material |
|---|---|---|---|---|---|---|---|
| 1 | 5 | S1 | R01 | Underst. | evaluate statements | Given a smartphone table (Brand, Storage, RAM, Display_Size, OS, Price_Category, Price; 5 rows: Apple, Samsung, OnePlus, Xiaomi, Google), which statement about the … | — (not found in repo) |
| 2 | 5 | S1 | R03 | Appl. | choose code or function | The text 'iPhone 13 Pro' must be extracted with XPath from an HTML file (body > div id='content' with h1, p, ul of three li class='product' items: iPhone 13 Pro, … | Excercises_Week_01.pdf Task 3 |
| 3 | 6 | S1 | R07 | Underst. | evaluate statements | Given a JSON snippet {name, age, city, hobbies [array], street, email, phone} whose lines lack separating commas, which statement about this file and JSON in general … | Excercises_Week_02.pdf Task 3 |
| 4 | 6 | S1 | R01 | Underst. | evaluate statements | Given a five-point Likert scale from an online survey (Strongly Disagree=1 ... Strongly Agree=5), which statement about the scale of measure of Likert-scale data is … | — (not found in repo) |
| 5 | 7 | S2 | R05 | Appl. | predict code output | Given a=24, b=100/15*2, c='dog', d=False, e=7==8, f=6>5, g=int(str(71)), which types does print(type(a), ..., type(g)) show? | Excercises_Week_02.pdf |
| 6 | 7 | S2 | R06 | Appl. | predict code output | obj = [{'pets':['cat','dog','bird']}, [1,2,3,4], ('A','B','C'), {'mouse','turtle','fish'}]; what does print(type(obj[1])) return? | Excercises_Week_02.pdf |
| 7 | 8 | S2 | R06 | Appl. | predict code output | A dict obj (id, make, model, year, color for 4 cars: Toyota Camry, BMW X5, Ford Focus, Audi A4) becomes cars = pd.DataFrame(obj). The code runs key_sel = … | Week_02/supermarkets_data.ipynb |
| 8 | 8 | S2 | R07 | Appl. | choose code or function | A file 'myfile' has no extension. Its content is { "name": "Alice", "age": 30, "city": "New York", "interests": [...] }. Which line of code reads it correctly into a … | Week_02/supermarkets_data.ipynb |
| 9 | 9 | S3 | R11 | Appl. | predict code output | df1 (Apple, Banana, Orange, Grape with Color, Taste) and df2 (Kiwi, Pineapple, Strawberry, Mango with Color, Taste) are combined with pd.concat([df1, df2], … | Week_11/NLP_hotel_reviews_sentiment_prediction.ipynb |
| 10 | 9 | S3 | R11 | Appl. | predict code output | df has co2=[95,90,99,104,105,94,99,104], model=[Citigo, Fabia, Fiesta, Rapid, Focus, Mondeo, Octavia, B-Max] and make=[Skoda, Skoda, Ford, Skoda, Ford, Ford, Skoda, … | Week_03/combining_and_organizing_data.ipynb |
| 11 | 10 | S3 | R09 | Appl. | predict code output | A DataFrame 'data' holds 6 pets (name, type, age, breed); Buddy and Charlie have breed NaN. The code is subset = data.dropna().loc[(data['age'] >= 3) \| (data['type'] … | Week_02/supermarkets_data.ipynb |
| 12 | 11 | S3 | R11 | Appl. | predict code output | The cars DataFrame has Brand [Toyota,BMW,Toyota,BMW,Toyota,BMW], Model [Camry,X5,Corolla,X3,Corolla,X5], Price [35000,45000,40000,48000,42000,54000] and Sales … | Week_03/combining_and_organizing_data.ipynb |
| 13 | 12 | S4 | R13 | Appl. | evaluate statements | A contingency table of observed frequencies from an online survey: likes Snickers Boy 86 / Girl 60 (sum 146); doesn't like Snickers Boy 16 / Girl 38 (sum 54); column … | Week_04/exploratory_data_analysis_apartment_data.ipynb |
| 14 | 12 | S4 | R12 | Appl. | calculate value | A sample of Swiss house prices: 1500000, 1600000, 1700000, 1800000, 1900000. What is the sample standard deviation (rounded to one decimal)? | Week_04/exploratory_data_analysis_apartment_data.ipynb |
| 15 | 13 | S4 | R14 | Underst. | interpret output or figure | A histogram and a boxplot of car prices (USD) are shown with printed Q1=10262, median=17291 and Q3=27422. Which statement about these graphics and measures is NOT … | Week_04/exploratory_data_analysis_apartment_data.ipynb |
| 16 | 14 | S4 | R15 | Underst. | interpret output or figure | A correlation heatmap of environmental variables is shown (wind, temperature, radiation, ozone; ozone-temperature 0.7, ozone-wind -0.61, temperature-wind -0.5, … | Week_04/exploratory_data_analysis_apartment_data.ipynb |
| 17 | 15 | S5 | R17 | Repro | evaluate statements | A GIS text format is shown: a polygon POLYGON ((30 10, 40 40, 20 40, 10 20, 30 10)) and a polygon with a hole POLYGON ((35 10, 45 45, 15 40, 10 20, 35 10),(20 30, 35 … | Excercises_Week_05.pdf Task 2 |
| 18 | 15 | S5 | R18 | Underst. | evaluate statements | Python code in 4 parts: (1) base_url of the api3.geo.admin.ch SearchServer; (2) a parameters dict with searchText 'Marktstrasse 14, 8500 Frauenfeld', origins … | Week_05/geocoding_addresses.ipynb |
| 19 | 16 | S6 | R21 | Repro | evaluate statements | Which statement about an unpaired t-test is NOT correct? | Week_06/unpaired_two_sample_t-test.ipynb |
| 20 | 16 | S6 | R20 | Appl. | calculate value | Observed frequencies of beverage preference: men wine 64 / beer 78 (sum 142); women wine 75 / beer 62 (sum 137); column sums 139 / 140; total 279. Which expected … | Week_07/analysis_of_contingency_tables.ipynb |
| 21 | 17 | S7 | R24 | Appl. | calculate value | A scatter plot with a linear regression of alligator weight (kg, y) on length (cm, x): y = 1.0758x + 32.425, R^2 = 0.9568. Which prediction (rounded to whole kg) is … | Week_08/linear_regression.ipynb |
| 22 | 17 | S7 | R25 | Underst. | interpret output or figure | Given the regression equation y = -0.22x + 45000 (y = estimated car price in $, x = mileage in km), what does the equation imply? | Week_08/linear_regression.ipynb |
| 23 | 18 | S7 | R26 | Underst. | evaluate statements | Two numerical variables are analysed with correlation and with regression. If the coefficient of determination R^2 equals 1, then the correlation coefficient r ... | Week_08/linear_regression.ipynb |
| 24 | 18 | S8 | R28 | Appl. | calculate value | Confusion matrix of a spam classifier: Actual Not Spam 850 (TN), 50 (FP); Actual Spam 30 (FN), 950 (TP). What is the accuracy (rounded to two decimals)? | Week_09/classification_analysis_titanic.ipynb |
| 25 | 18 | S8 | R30 | Repro | evaluate statements | About an individual tree Tk in a Random Forest (T1...Tn), which statements are true? (1) built on a randomly selected subset of features; (2) built on all features; … | Week_09/classification_analysis_titanic.ipynb |
| 26 | 19 | S8 | R29 | Underst. | interpret output or figure | Given a ROC curve (TPR vs FPR with a diagonal reference line), which statement about ROC curves and AUC is NOT correct? | Week_09/classification_analysis_titanic.ipynb |
| 27 | 19 | S9 | R31 | Repro | definition or fact | How is the optimal number of clusters typically determined in k-means clustering? | Week_10/k-means_clustering.ipynb |
| 28 | 20 | S9 | R32 | Underst. | interpret output or figure | Figure 1 is a silhouette plot of a k-means solution with clusters 0-5 and a red dotted average line. Figure 2 lists the average silhouette scores: k=3 0.5882, k=4 … | Week_10/k-means_clustering.ipynb |
| 29 | 21 | S10 | R33 | Appl. | other | Which option is the complete preprocessing of the sentence 'Paul wanted a better job.' according to the text-preprocessing steps presented in class? | Week_11/NLP_text_preprocessing.ipynb |
| 30 | 21 | S10 | R34 | Appl. | calculate value | Using bag-of-words, what is the numerical representation of 'the cat chased the cat around the cat'? Apply no preprocessing, use this sentence as the vocabulary, and … | Week_11/NLP_text_preprocessing.ipynb |

### HS24 — `MEP/24_BA.3DA-WIN-2.pdf`

| Q | PDF p. | Section | Type (row) | Level | Format | Question (paraphrase) | Closest course material |
|---|---|---|---|---|---|---|---|
| 1 | 5 | S1 | R01 | Underst. | evaluate statements | A car data table is given (Brand, Model, Year, Engine_Size, Fuel_Type, Price_Category, Price; 5 rows, including a Tesla with Engine_Size 'Electric'). Which statement … | — (not found in repo) |
| 2 | 5 | S1 | R01 | Underst. | evaluate statements | A 5-point Likert scale questionnaire is given (Strongly Agree=1 ... Strongly Disagree=5; items such as 'I like Stock Market', 'I like Stocks', 'I Like Money', 'I Like … | — (not found in repo) |
| 3 | 6 | S1 | R03 | Appl. | choose code or function | An HTML product page is given: a div id='main' containing h1, p, and a ul with three li class='product' items (MacBook Air, Dell XPS 13, HP Spectre x360), plus a … | Excercises_Week_01.pdf Task 3 |
| 4 | 6 | S2 | R05 | Appl. | predict code output | Which data types does print(type(x), type(y), type(z), type(w), type(v), type(u), type(h)) return for x = str(bool(int('0'))), y = 7.5*2, z = 'Python'+'is easy'+'to … | Excercises_Week_02.pdf |
| 5 | 7 | S2 | R06 | Appl. | predict code output | Which types does print() return for model_01 = ('iPhone 12', 'Galaxy S21', ...) in parentheses, model_02 = {'OnePlus', 'Pixel', ...} in braces without keys, model_03 … | Excercises_Week_02.pdf |
| 6 | 7 | S2 | R09 | Appl. | predict code output | Given the data frame 'smartphones' (8 rows: brand, model, release_year, price, battery_life), which columns and values does print(smartphones.loc[(brand != 'Google') … | Week_06/unpaired_two_sample_t-test.ipynb |
| 7 | 8 | S2 | R07 | Appl. | choose code or function | A utf-8 encoded file 'my_file' has no extension. Opened in a text editor, it shows a JSON structure: a list of objects with type 'node', id, lat, lon, and tags such … | Week_02/supermarkets_data.ipynb |
| 8 | 8 | S2 | R07 | Underst. | evaluate statements | Two items are shown: 1.) an XML note document (to/from/heading/body tags) and 2.) a JSON object (type, id, lat, lon, tags for Coop Uznach Linthpark). Which statement … | Excercises_Week_02.pdf Task 3 |
| 9 | 9 | S3 | R11 | Appl. | predict code output | A df has make ['VW','BMW','BMW','VW','BMW','VW'] and price [21000, 27000, 33000, 31000, 45000, 32000]. The code runs output = df.groupby(by='make').price.mean() and … | Week_03/combining_and_organizing_data.ipynb |
| 10 | 10 | S3 | R11 | Appl. | predict code output | A DataFrame smartphones has Brand [Apple, Samsung, Apple, OnePlus, Samsung], Model [iPhone 12, Galaxy S21, iPhone 12, Nord, Galaxy S21], Price (appears to be [999, … | Week_03/combining_and_organizing_data.ipynb |
| 11 | 11 | S3 | R11 | Appl. | predict code output | df_phones (Brand; Model: iPhone 12, Galaxy S21, iPhone 13, Nord) is merged with df_sales (the same 4 Models, Price [999, 850, 1099, 500], Sales [1500, 2000, 1700, … | Week_03/combining_and_organizing_data.ipynb |
| 12 | 12 | S3 | R10 | Appl. | predict code output | price_raw is ['$999', '€850', '1099 USD', '500 pounds', 'Free']. A loop applies re.findall('[0-9]+', i) and takes d1[0].strip(), or None on IndexError. Then … | Week_02/apartments_data_preparation_winterthur.ipynb |
| 13 | 13 | S4 | R14 | Underst. | interpret output or figure | A histogram and a boxplot of smartphone prices (USD) are shown, with Q1=$718, median=$1005, Q3=$1372 and many high outliers up to about $7000. Which statement is NOT … | Week_04/exploratory_data_analysis_apartment_data.ipynb |
| 14 | 13 | S4 | R13 | Underst. | interpret output or figure | A contingency table from an online survey: men like dogs 50 / don't 20 (sum 70); women like 70 / don't 60 (sum 130); total 200 (like 120, don't 80). Which statement … | Week_04/exploratory_data_analysis_apartment_data.ipynb |
| 15 | 14 | S4 | R15 | Underst. | interpret output or figure | A correlation matrix of smartphone data is shown (Price, Camera MP, Battery Life, Weight, Portability rating 1-10, higher = more portable), e.g. Price-Camera 0.9651, … | Week_04/exploratory_data_analysis_apartment_data.ipynb |
| 16 | 14 | S4 | R12 | Appl. | calculate value | A sample of 5 smartphone prices is given: 800, 950, 1200, 850, 750. What is the sample standard deviation (rounded to 2 decimals)? | Week_04/exploratory_data_analysis_apartment_data.ipynb |
| 17 | 15 | S5 | R18 | Underst. | interpret output or figure | A map from 'Koordinator' for 8400 Winterthur, Theaterstrasse 17 shows 1.) coordinates 2 697 110 / 1 262 228 and 2.) 'Grad Dezimal' Lat 47.50363, Lng 8.72759. Which … | Excercises_Week_05.pdf Task 1 |
| 18 | 15 | S5 | R17 | Underst. | evaluate statements | A GIS data snippet is given: { "type": "Polygon", "coordinates": [[[30,10],[40,40],[20,40],[10,20],[30,10]]] }. Which statement about this format is NOT correct? | — (not found in repo) |
| 19 | 16 | S6 | R20 | Appl. | calculate value | The dog-liking contingency table from Q14 is shown again (50/70/120; 20/60/80; 70/130/200). For a Chi-squared test, which are the correct expected frequencies? | Excercises_Week_07.pdf Task 1 c-d |
| 20 | 17 | S6 | R21 | Underst. | interpret output or figure | Watermelon weights (kg) from Field A and Field B (14 each) are given with unpaired two-sample t-test results: means 5.754 vs 7.595, variances 0.224 vs 0.583, df 22, t … | Week_06/unpaired_two_sample_t-test.ipynb |
| 21 | 18 | S7 | R24 | Appl. | calculate value | A scatter plot shows a simple linear regression of smartphone price on camera megapixels, y = 450.91 + 9.53x. What is the estimated price for a 48-megapixel camera (2 … | Week_08/linear_regression.ipynb |
| 22 | 18 | S7 | R25 | Underst. | evaluate statements | A multiple regression is given: y_hat = 200 + 10*x1 + 20*x2 (y_hat = smartphone price in USD, x1 = camera megapixels, x2 = battery life in hours). Which statement is … | Week_08/linear_regression.ipynb |
| 23 | 19 | S7 | R26 | Underst. | evaluate statements | Which statement about the coefficient of determination (R^2) and the elements of its formula is NOT correct? | Week_08/linear_regression.ipynb |
| 24 | 19 | S8 | R30 | Underst. | interpret output or figure | A graphic shows a classification tree with 20 observations of two classes (plus/minus), one split and two terminal nodes (left node 14 obs, right node 6 obs). Which … | Week_09/classification_analysis_titanic.ipynb |
| 25 | 20 | S8 | R28 | Appl. | calculate value | An image classifier for cats vs dogs is tested on 10,000 images (cats 4,998, dogs 5,002). Confusion matrix: Cats TP 4,001, FP 997; Dogs FN 1,250, TN 3,752. What are … | Week_09/classification_analysis_titanic.ipynb |
| 26 | 20 | S8 | R29 | Underst. | interpret output or figure | The ROC curve of a binary classifier (area = 0.85) is shown with a diagonal reference line. Which statement about the ROC curve and AUC is NOT correct? | Week_09/classification_analysis_titanic.ipynb |
| 27 | 21 | S9 | R31 | Underst. | interpret output or figure | An elbow plot for k-means is shown with axis labels removed (k = 1..9; values drop from about 310 to 110 to 40, then flatten near 20 toward about 10). Which statement … | Week_10/k-means_clustering.ipynb |
| 28 | 22 | S9 | R32 | Underst. | interpret output or figure | Silhouette plots are shown for (a) 3, (b) 4, (c) 5 and (d) 6 clusters, each with a dashed red average line. Which statement about the Silhouette method in general and … | Week_10/k-means_clustering.ipynb |
| 29 | 23 | S10 | R33 | Appl. | other | For the sentence 'Paul wanted a better job.', which option is the complete preprocessing according to the text wrangling/preprocessing steps presented in class? | Week_11/NLP_text_preprocessing.ipynb |
| 30 | 23 | S10 | R34 | Appl. | predict code output | Using nltk WordNetLemmatizer, the code lemmatizes 'wrote' (pos='v'), 'children' (pos='n'), 'happier' (pos='a'), 'running' (pos='v') and 'employees' (pos='n'), appends … | Week_11/NLP_text_preprocessing.ipynb |

### HS25 — `MEP/25_BA.3DA-WIN.pdf`

| Q | PDF p. | Section | Type (row) | Level | Format | Question (paraphrase) | Closest course material |
|---|---|---|---|---|---|---|---|
| 1 | 5 | S1 | R01 | Underst. | evaluate statements | Given a table of bicycle data (Brand, Model, Frame Size, Weight kg, Gears, Type, Brake System, Price), which statement about the 'scale of measure' of these variables … | — (not found in repo) |
| 2 | 6 | S1 | R03 | Appl. | choose code or function | The text '1965' (year of manufacture of the Triumph Bonneville T120) must be extracted with an XPath from a given HTML file. The file has a table with a header row … | Excercises_Week_01.pdf Task 3 |
| 3 | 7 | S1 | R04 | Underst. | evaluate statements | Python code queries the Overpass API (area ISO3166-1='CH', admin_level=2; node shop=hairdresser) with requests.get. It saves r.json()['elements'] to … | Week_01/getting_supermarket_locations_WebAPI.ipynb |
| 4 | 7 | S2 | R05 | Appl. | predict code output | Which data types does print() show for: a=5+3.0; b='12'+str(8); c=len(['Yamaha','BSA','Norton']); d=(10>3) and isinstance(4.5,float); e=len('Simson')>5; … | Excercises_Week_02.pdf |
| 5 | 8 | S2 | R06 | Appl. | predict code output | Given a dict obj with keys 'key', 'name', 'gender', 'age', 'city' (each mapping to a list of 4 values), what does print(list(obj.keys())) output? | Week_LC/LC_02/Exercises_Large_Classes_Week_02.md Task |
| 6 | 8 | S2 | R06 | Appl. | predict code output | obj_01 = ['Beagle', 1234, 'Bulldog', 'Beagle', 1234]; obj_02 = set(obj_01). What does print(obj_01, obj_02) output? | Excercises_Week_02.pdf |
| 7 | 8 | S2 | R06 | Appl. | predict code output | Given dict obj = {'pets': ['cat','dog','bird'], 'numbers': (1,2,3,4), 'colors': {'red','green','blue'}, 'info': {'name':'Max','age':5}}, what does … | Excercises_Week_02.pdf |
| 8 | 9 | S2 | R07 | Appl. | predict code output | Code builds a dict {'employees': [3 dicts with name/age/city]}, writes it with json.dump to 'employees.json', reads it back with pd.read_json and prints type(df). … | Week_02/supermarkets_data.ipynb |
| 9 | 10 | S3 | R09 | Appl. | predict code output | DataFrame 'data' has 7 tractors (id, brand, country, horsepower, category, price). Claas and Kubota have country NaN, and the two Fendt rows (id 2 and 6) are … | Week_03/apartments_data_preparation_zuerich.ipynb |
| 10 | 11 | S3 | R11 | Appl. | predict code output | df1 and df2 each have 4 rows and 3 columns (Brand, Country, Horsepower). df3 = pd.concat([df1, df2], ignore_index=True); print(df3.shape). How many rows and columns … | Week_LC/LC_09/classification_models.ipynb |
| 11 | 12 | S3 | R10 | Appl. | predict code output | DataFrame df has 8 restaurant reviews (review_text, city, avg_price). The code uppercases review_text, sets pattern '(FRIENDLY)\|(CLEAN)\|(BEAUTIFUL)\|(EXCELLENT)', … | Week_03/apartments_data_preparation_zuerich.ipynb |
| 12 | 12 | S3 | R11 | Appl. | predict code output | df1 (5 rows: brand, horsepower, country) and df2 (5 rows: brand, category, price (k€)); df3 = df1.merge(df2[['brand','price (k€)']], on='brand'). How many rows and … | Week_03/combining_and_organizing_data.ipynb |
| 13 | 13 | S4 | R13 | Appl. | calculate value | Contingency table from a survey (use / do not use public transport x men / women): Men 72/28 (100), Women 88/42 (130), totals 160/70/230. Which statement (percentages … | Week_04/exploratory_data_analysis_apartment_data.ipynb |
| 14 | 13 | S4 | R12 | Appl. | calculate value | Sample of 5 smartphone prices (CHF): 1099, 999, 899, 799, 699. What is the sample standard deviation (rounded to 1 decimal)? | Week_06/population_and_samples.ipynb |
| 15 | 14 | S4 | R14 | Underst. | interpret output or figure | A histogram and a boxplot of smartphone prices (CHF) are shown with Q1=579, median=810 and Q3=1106. Which statement about the graphics and measures is NOT correct? | Week_04/exploratory_data_analysis_apartment_data.ipynb |
| 16 | 15 | S4 | R14 | Underst. | interpret output or figure | A grouped horizontal boxplot of smartphone prices (USD) for the brands Alpha, Beta and Gamma is shown. Which statements are correct: (1) Gamma has a larger IQR than … | Week_LC/LC_06/tasks_large_classes_week_06.md Task 2 |
| 17 | 15 | S5 | R17 | Repro | definition or fact | Which statement about the shown GIS data format (POINT (30 10), LINESTRING (30 10, 10 30, 40 40)) is NOT correct? | Excercises_Week_05.pdf Task 2 |
| 18 | 16 | S5 | R18 | Underst. | evaluate statements | Code in four parts. (1) base_url of the api3.geo.admin.ch SearchServer. (2) Parameters searchText 'Bahnhofstrasse 10, 8001 Zürich', origins 'address', type … | Week_05/geocoding_addresses.ipynb |
| 19 | 17 | S6 | R15 | Underst. | interpret output or figure | A correlation heatmap of Study_Hours, Sleep_Hours, Screen_Time, Grades and Stress_Level is shown (e.g. Study-Sleep -0.65, Study-Grades 0.41, Sleep-Stress -0.74). All … | Week_07/correlation_analysis.ipynb |
| 20 | 18 | S6 | R20 | Appl. | calculate value | Using the public transport contingency table from Q13 (72/88/160; 28/42/70; 100/130/230), which set of expected frequencies for a chi-squared test is correct (2 … | Week_07/analysis_of_contingency_tables.ipynb |
| 21 | 19 | S7 | R25 | Underst. | interpret output or figure | Given the regression equation y = 3.5x1 + 25x2 + 200 (y = smartphone price in $, x1 = storage GB, x2 = camera MP), what does the equation imply? | Week_08/linear_regression.ipynb |
| 22 | 19 | S7 | R26 | Underst. | definition or fact | Two numerical variables are analysed with correlation and regression. If the coefficient of determination R^2 equals 1, then the correlation coefficient r ... | Week_08/linear_regression.ipynb |
| 23 | 20 | S7 | R24 | Appl. | calculate value | Using the regression y = 120 + 2.75x1 + 8.60x2 + 0.15x3 (x1 storage GB, x2 camera MP, x3 battery mAh), what is the estimated price (USD) for 128 GB, 48 MP and 4000 … | Week_08/linear_regression.ipynb |
| 24 | 20 | S8 | R28 | Appl. | calculate value | Confusion matrix of a classification model: TP=950, FN=120, FP=210, TN=840. What is the recall (4 decimals)? | Week_09/classification_analysis_titanic.ipynb |
| 25 | 21 | S8 | R30 | Underst. | evaluate statements | A RandomForestClassifier with default settings (bootstrap=True, max_samples=None, max_features='sqrt'). Which statements are true: (1) each tree uses 80% of features … | Week_09/classification_analysis_titanic.ipynb |
| 26 | 21 | S8 | R29 | Underst. | interpret output or figure | ROC curves of three classification models on the same dataset are shown: Model A (LogReg, AUC=0.92), Model B (RandomForest, AUC=0.95), Model C (SVM RBF, AUC=0.91), … | Week_09/classification_analysis_titanic.ipynb |
| 27 | 22 | S9 | R31 | Repro | definition or fact | Which statement about the k-means algorithm is correct? | Week_10/k-means_clustering.ipynb |
| 28 | 23 | S9 | R32 | Underst. | interpret output or figure | Figure 1 is a silhouette plot (clusters 0-5, red dotted line at about 0.8). Figure 2 lists average silhouette scores for k=3: 0.5459, k=4: 0.7052, k=5: 0.8140, k=6: … | Week_10/k-means_clustering.ipynb |
| 29 | 24 | S10 | R33 | Appl. | other | For the sentence 'Lisa bought an expensive car.', which option corresponds to complete preprocessing according to the text preprocessing steps presented in class? | Week_11/NLP_text_preprocessing.ipynb |
| 30 | 24 | S10 | R34 | Underst. | interpret output or figure | A TF-IDF matrix for 5 terms (data, science, machine, learning, the) across documents D1-D5 is shown (e.g. D3: data 0.42, machine 0.36, learning 0.29; 'the' 0.01-0.03 … | Week_11/NLP_text_preprocessing.ipynb |

## Appendix B: Method (how the numbers were produced)
1. **Admin documents** (Module description, Semester program, General information) were read in full from their text layer.
2. **MEPs** (scans without text) were rendered page by page. For each exam, an extraction pass transcribed and classified Q1–Q30. An **independent verification pass** re-read every page and corrected the result. Corrections, in total: HS24 Q29 and HS25 Q29 level → Application, HS25 Q21 format, stem clarifications for HS23 Q7/Q11/Q17, and fixed counts of negated stems. All 90 page numbers were confirmed.
3. **Course material:** every exercise PDF, notebook (cells counted exactly), LC task file and app was read per week. Topic, emphasis and interpretation rules were recorded **with file/cell citations**.
4. **Counting:** all frequencies, weights, categories and hours were computed by script from the verified data. Each of the 90 questions is mapped to exactly one question type (asserted), and the hours sum to exactly 20 (asserted).
5. **Independent spot-checks** by grep over the repo: no XPath, Likert, WKT/GeoJSON, Gini or `ttest_rel` anywhere. The only exam-scope statement found is LC_11 Task 1.

