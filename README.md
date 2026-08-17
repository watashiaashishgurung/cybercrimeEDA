# Predicting Cybersecurity Incidents: Exploratory Data Analysis 🍊🍊🍃

## Introduction

This project explores patterns in reported cybercrime incidents in **Leuven, Belgium, from 2016 to 2025**.

The analysis examines how cybercrime reports change over time, with particular attention to:

* Yearly trends in reported cybercrime
* Monthly and seasonal patterns
* Differences between individual years
* Accumulated monthly incidents across 2016–2025
* Possible relationships between periods of increased technological activity and cybercrime reports

A secondary research question considers whether periods associated with major technology releases and increased consumer activity coincide with changes in reported cybercrime.

> **Important:** This is an exploratory data analysis (EDA). Similar timing between technology releases and cybercrime activity may indicate an association worth investigating, but does not by itself establish causation.

---

## Dataset

The dataset contains monthly cybercrime reports for the **Leuven arrondissement** covering:

**2016–2025**

The data is transformed into a tidy structure containing:

| Column  | Description                             |
| ------- | --------------------------------------- |
| `year`  | Year of the observation                 |
| `month` | Month of the observation                |
| `total` | Number of reported cybercrime incidents |

With 12 months across 10 years, the cleaned dataset contains **120 monthly observations**.

---

## Data Preparation

The original CSV is stored in a wide, semicolon-separated format.

During preprocessing, the data is transformed into a structure suitable for analysis:

```text
year | month    | total
2016 | january  | ...
2016 | february | ...
2016 | march    | ...
...  | ...      | ...
2025 | december | ...
```

The notebook then converts the relevant fields to appropriate data types and creates a date variable for chronological analysis.

---

## Exploratory Data Analysis

The analysis investigates the dataset from several perspectives.

### Cybercrime Reports by Year

Monthly observations are grouped by year to calculate the total number of reported cybercrime incidents for each year.

This makes it possible to examine whether reported cybercrime increased, decreased, or remained relatively stable between **2016 and 2025**.

### Cybercrime Reports by Month

The data is also grouped by calendar month.

For example:

```text
January total =
January 2016 +
January 2017 +
January 2018 +
...
January 2025
```

The resulting stacked bar chart shows both:

* The **accumulated total for each month across 2016–2025**
* The contribution of each individual year to that monthly total

Each bar therefore represents ten years of observations for the corresponding month.

### Monthly Patterns by Year

Individual years are visualized separately to make it easier to identify unusual months, peaks, declines, and recurring patterns.

The project also uses radial charts to visualize how reported incidents are distributed throughout each calendar year.

A consistent **Plasma color scale** is used across several visualizations to make comparisons between years easier.

---

## Background Research 🍊🍊🍃

Before analyzing whether technology-release periods might coincide with changes in cybercrime activity, it is useful to identify periods of the year associated with major technology announcements and consumer activity.

### Timeline of Major Technology Events

| Period                | Examples                                                            |
| --------------------- | ------------------------------------------------------------------- |
| **January**           | Consumer Electronics Show (CES) and major technology announcements  |
| **March–April**       | Spring product announcements and updates                            |
| **June**              | Apple WWDC and other major software/platform announcements          |
| **September–October** | Major smartphone, operating-system and consumer-device launches     |
| **November–December** | Holiday shopping period, promotions and increased consumer activity |

These periods provide useful reference points when visually comparing monthly cybercrime patterns.

---

## Why Technology Releases Could Be Relevant

### New Device Bugs and Software Vulnerabilities

New devices and software releases can introduce:

* New or previously undiscovered vulnerabilities
* Compatibility problems
* Firmware and driver issues
* Software bugs
* Configuration problems

The period immediately following a release may therefore create new opportunities for vulnerability discovery and exploitation.

### Increased Cybercriminal Attention

Major technology events can also generate increased public attention.

Cybercriminals may attempt to exploit this attention through techniques such as:

* Phishing
* Fake promotions
* Fraudulent websites
* Malicious downloads
* Social engineering
* Impersonation of technology companies or services

Holiday shopping periods may similarly provide opportunities for fraud and phishing campaigns.

---

## Interpretation

The monthly cybercrime data can be compared with the approximate timing of major technology releases and periods of increased consumer activity.

However, a similar seasonal pattern should **not automatically be interpreted as evidence that technology releases cause cybercrime**.

Other factors could influence the observed numbers, including:

* Changes in reporting behavior
* Increased use of digital services
* Holiday shopping
* Large phishing or fraud campaigns
* Changes in law-enforcement classification
* Economic conditions
* Growth in the number of internet-connected devices
* Broader long-term growth in cybercrime

The current analysis should therefore be considered **exploratory and hypothesis-generating**.

A stronger causal analysis would require additional variables and statistical testing.

---

## Visualizations

The Jupyter notebook contains several visualizations, including:

* Total cybercrime reports by year
* Accumulated cybercrime reports by month
* Monthly totals stacked by year
* Comparison of the earliest and latest years
* Monthly time-series visualization
* Year-by-year bar charts
* Radar charts
* Radial bar charts

Together, these visualizations provide different perspectives on the temporal structure of the dataset.

---

## Technologies Used

* **Python**
* **Jupyter Notebook**
* **Pandas**
* **Matplotlib**
* **Seaborn**
* **NumPy**

---

## How to View and Run the Jupyter Notebook

The main data analysis is provided as a **Jupyter Notebook (`.ipynb`)**. You can either view the notebook directly on GitHub or download it and run the analysis yourself.

### Option 1 — View on GitHub

GitHub can display Jupyter Notebooks directly in your browser.

1. Open this repository on GitHub.
2. Click the `.ipynb` notebook file.
3. GitHub will render the notebook, including its Markdown explanations, Python code, tables, and saved visualizations.

You do not need Python or Jupyter installed if you only want to **view the notebook**.

### Option 2 — Run the Notebook Locally

To execute the analysis yourself, first make sure **Python 3** is installed.

Install Jupyter and the required Python packages:

```bash
python -m pip install jupyter pandas seaborn matplotlib numpy
```

On Windows, if the `python` command is unavailable, you can use:

```bash
py -m pip install jupyter pandas seaborn matplotlib numpy
```

Clone or download this repository and open a terminal inside the project directory.

Start Jupyter Notebook:

```bash
jupyter notebook
```

Your browser should open the Jupyter interface automatically.

Open the project's `.ipynb` file and run the cells sequentially using:

**Cell → Run All**

or execute individual cells with:

**Shift + Enter**

### Dataset Location

The CSV dataset should remain in the **same directory as the Jupyter Notebook** so that the notebook can locate it using a relative path.

Example project structure:

```text
cybercrimeEDA/
│
├── README.md
├── cybercrime_dataanalysis.ipynb
├── transposed20152016.csv
└── Executive_Summary_CS_2016-2025_Styled.pdf
```

Using a relative path makes the project portable and prevents the notebook from depending on a specific Windows user directory.

For example:

```python
transposed = pd.read_csv("transposed20152016.csv", sep=";")
```

rather than:

```text
C:/Users/username/Documents/.../transposed20152016.csv
```

### Required Python Libraries

The analysis uses:

* `pandas` — data loading, cleaning and manipulation
* `seaborn` — statistical data visualization
* `matplotlib` — charts and plotting
* `numpy` — numerical operations and radial-chart calculations

Once the dependencies are installed and the dataset is in the correct location, the notebook can be executed from top to bottom to reproduce the analysis and visualizations.


## Conclusion

The analysis provides an exploratory overview of reported cybercrime in Leuven between **2016 and 2025**.

By examining yearly totals, accumulated monthly totals, individual-year patterns, and radial visualizations, the project makes it possible to identify periods in which reported cybercrime activity appears higher or lower.

The comparison with major technology-release periods provides an interesting hypothesis for further investigation, but the available data alone cannot demonstrate that product releases directly cause increases in cybercrime.

Future work could expand the analysis by incorporating vulnerability disclosures, phishing statistics, technology adoption data, product-release dates, economic indicators, and other cybersecurity datasets.

---

## Further Reading

For additional context on cybersecurity trends and threat activity, useful industry sources include:

1. **Symantec Internet Security Threat Report** — Historical analysis of cybersecurity threats, vulnerabilities and attack trends.
2. **McAfee Labs Threats Report** — Research into malware, vulnerabilities and emerging cyber threats.
3. **Verizon Data Breach Investigations Report (DBIR)** — Annual analysis of security incidents and confirmed data breaches.
4. **Cisco Cybersecurity Reports** — Research into changing attack patterns and cybersecurity risks.

### Project Executive Summary

Additional research and updated findings are available in the project repository:

1. [**Executive Summary CS 2016–2025**](https://github.com/watashiaashishgurung/cybercrimeEDA/blob/main/Executive_Summary_CS_2016-2025_Styled.pdf) — Updated executive summary covering the exploratory analysis of reported cybercrime incidents in Leuven from 2016 to 2025.

---

## Research Question

> **Do reported cybercrime incidents display recurring monthly or seasonal patterns between 2016 and 2025, and do any of these patterns coincide with periods of major technology releases or increased technology-related consumer activity?**

This project approaches that question through exploratory data analysis rather than assuming a causal relationship.

## Data Source

The cybercrime data used in this project was obtained from the
**Belgian Federal Police – Police Crime Statistics (Statistiques Policières de Criminalité)**.

Source: Belgian Federal Police – Directorate of Police Information and ICT Resources (DGR/DRI/BIPOL).

Data period used in this analysis: **2016–2025**  
Geographic area: **Leuven, Belgium**

[Belgian Federal Police Crime Statistics](https://www.police.be/statistiques/en/crime)
