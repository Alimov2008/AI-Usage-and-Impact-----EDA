# AI Usage and Impact — Exploratory Data Analysis

An exploratory data analysis project investigating how students and professionals use artificial intelligence tools and how AI usage relates to reported productivity, satisfaction, accuracy, time savings, and cost.

**Repository:** [Alimov2008/AI-Usage-and-Impact-----EDA](https://github.com/Alimov2008/AI-Usage-and-Impact-----EDA)

---

**Link To Original Dataset:** [Kaggle Dataset](https://www.kaggle.com/datasets/eishatuzzuhra/ai-usage-and-impact-on-students-and-professionals)

---

## Table of Contents

- [Overview](#overview)
- [Research Questions](#research-questions)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Analytical Workflow](#analytical-workflow)
- [Areas of Analysis](#areas-of-analysis)
- [Technology Stack](#technology-stack)
- [Getting Started](#getting-started)
- [Running the Notebook](#running-the-notebook)
- [Methodological Considerations](#methodological-considerations)
- [Limitations](#limitations)
- [Future Improvements](#future-improvements)
- [Author](#author)

## Overview

Artificial intelligence tools are increasingly used for coding, writing, research, studying, and professional tasks. However, frequent usage does not necessarily translate into better outcomes, greater satisfaction, or more efficient work.

This project explores these relationships through **Exploratory Data Analysis (EDA)** of a dataset describing AI usage among students and professionals.

The analysis follows a data-first approach: inspect the raw dataset, identify data-quality problems, clean and standardize the data, examine distributions, investigate relationships between variables, and compare reported outcomes across user groups and AI tools.

Rather than treating AI usage as a single measure, the project considers several dimensions:

- **Adoption:** Who uses AI, which tools they use, and what they use them for.
- **Usage intensity:** How much time users spend interacting with AI.
- **Effectiveness:** Reported productivity, accuracy, and time savings.
- **User experience:** Satisfaction and willingness to recommend AI.
- **Economics:** Monthly AI expenditure and reported benefits.
- **User segmentation:** Differences between students, professionals, and occupational groups.

The primary deliverable is a Jupyter Notebook containing the data preparation, exploratory analysis, visualizations, and supporting observations.

## Research Questions

The notebook is organized around the following research questions.

### 1. AI Adoption and Usage Patterns

- Who uses AI tools: students or professionals?
- Which AI tools are most frequently used?
- What are the most common purposes of AI usage?
- How does AI usage vary across professions, countries, and educational backgrounds?

### 2. Productivity and Usage Intensity

- Is daily AI usage associated with higher reported productivity?
- Do users who spend more time using AI report greater benefits?
- Are there indications of diminishing returns at higher usage levels?
- Do relationships between usage intensity and productivity differ across professions?

### 3. Accuracy and Satisfaction

- How do reported accuracy ratings vary across AI tools?
- Is perceived accuracy associated with user satisfaction?
- Which tools receive stronger reported satisfaction scores?
- Do users who report better outcomes also express greater willingness to recommend AI?

### 4. Time Savings and Task Efficiency

- Which AI purposes are associated with greater reported time savings?
- How do time savings vary across tools and user groups?
- Is AI usage associated with differences in daily work or study hours?
- Are there users with high AI usage but relatively weak reported outcomes?

### 5. Cost and Reported Value

- Does higher monthly AI expenditure correspond to better reported outcomes?
- Which users report greater benefits relative to their AI expenditure?
- Are paid AI tools associated with different productivity or satisfaction levels?
- Do the reported benefits appear proportional to the amount of money spent?

These questions guide the analysis; they should not be interpreted as established conclusions before examining the corresponding results.

## Dataset

The primary dataset is stored at:

`data/AI_Usage_and_Impact_on_Students_and_Professionals.csv`

The initial inspection in the notebook reports **300 rows and 19 columns**.

Each record describes a user, their AI usage patterns, and their reported outcomes.

### Dataset Features

| Feature | Description |
|---|---|
| `User_ID` | Identifier assigned to a user |
| `Age` | User's age |
| `Gender` | Reported gender |
| `Country` | User's country |
| `User_Type` | Student or professional classification |
| `Education_Level` | Educational background |
| `Profession` | Occupation or field of study |
| `Monthly_Income` | Reported monthly income |
| `AI_Tool` | AI tool used |
| `AI_Purpose` | Primary purpose of AI usage |
| `AI_Usage_Hours_Per_Day` | Daily AI usage duration |
| `Tasks_Performed` | Description of tasks performed with AI |
| `Monthly_AI_Cost` | Reported monthly AI expenditure |
| `Productivity_Score` | Reported productivity score |
| `Accuracy_Rating` | Reported accuracy rating |
| `Satisfaction_Score` | Reported satisfaction score |
| `Time_Saved_Hours_Per_Week` | Reported weekly time savings |
| `Work_or_Study_Hours_Per_Day` | Daily work or study duration |
| `Would_Recommend` | Whether the user would recommend AI |

The dataset contains both categorical and numerical information, making it suitable for univariate, bivariate, and multivariate analysis.

**Data provenance:** Consult the dataset's original source before reusing it in other projects. The repository documentation should identify the original publisher and include the dataset license when those details are available.

## Project Structure

```text
AI-Usage-and-Impact-----EDA/
│
├── data/
│   └── AI_Usage_and_Impact_on_Students_and_Professionals.csv
│
├── main.ipynb
├── sample.csv
├── requirements.txt
├── pyproject.toml
├── uv.lock
├── .python-version
├── .gitignore
└── README.md
```

### Key Files

| File | Purpose |
|---|---|
| `main.ipynb` | Main notebook containing the data-cleaning workflow and EDA |
| `data/` | Directory containing the primary dataset |
| `sample.csv` | Additional CSV file included in the repository |
| `requirements.txt` | Pinned Python dependency list |
| `pyproject.toml` | Project metadata, Python requirement, and direct dependencies |
| `uv.lock` | Locked dependency resolution for the `uv` package manager |
| `.python-version` | Project Python version configuration |
| `.gitignore` | Files and directories excluded from version control |

## Analytical Workflow

The project follows a sequence of data preparation and exploratory analysis stages.

### 1. Environment Setup

The notebook imports the libraries required for data manipulation and visualization:

- Pandas for tabular data processing.
- NumPy for numerical operations.
- Matplotlib for plotting.
- Seaborn for statistical visualization.

### 2. Data Loading and Initial Inspection

The dataset is loaded into a Pandas DataFrame.

Initial inspection examines:

- Dataset dimensions.
- Column names and data types.
- Sample records.
- Summary statistics.
- Missing values.
- Unique values and category distributions.

The purpose of this stage is to understand the dataset before making assumptions about its quality or suitability for analysis.

### 3. Data Quality Assessment

The raw dataset contains data-quality issues that need to be addressed before meaningful comparisons can be made.

The cleaning workflow examines issues such as:

- Missing values.
- Inconsistent capitalization and category labels.
- Numeric values represented as strings.
- Inconsistent representations of categorical variables.
- Duplicate or repeated user identifiers.
- Invalid or unexpected values.
- Inconsistent column data types.

The notebook evaluates these issues before proceeding to the main analysis.

### 4. Data Cleaning and Standardization

Data preparation focuses on making the dataset consistent and analytically usable.

Depending on the variable, this includes:

- Standardizing categorical values.
- Converting numerical fields to appropriate numeric types.
- Identifying missing and invalid observations.
- Checking repeated identifiers and duplicate records.
- Converting suitable columns to categorical or nullable data types.
- Validating the resulting DataFrame.

Cleaning decisions should preserve the meaning of the original observations. Missing values should not automatically be replaced with zero, and repeated identifiers should not automatically be treated as duplicate records.

### 5. Univariate Analysis

Univariate analysis examines the distribution of individual variables.

The analysis can reveal:

- The composition of student and professional groups.
- The frequency of different AI tools and purposes.
- The distribution of daily AI usage hours.
- Variation in productivity, accuracy, and satisfaction scores.
- The distribution of monthly AI costs.
- The range of reported time savings.

Typical visualizations include bar charts, histograms, and box plots, supported by descriptive statistics.

### 6. Bivariate and Multivariate Analysis

The next stage investigates relationships between variables.

Examples include:

- AI usage hours versus productivity.
- Accuracy ratings versus satisfaction scores.
- AI tool versus reported productivity and time savings.
- Monthly expenditure versus reported outcomes.
- AI purpose versus time saved.
- User type or profession versus productivity.
- Usage intensity versus willingness to recommend AI.

Grouped summaries and statistical visualizations help compare these relationships across different user segments.

### 7. Comparative Analysis of AI Tools

The notebook compares reported outcomes across AI tools using grouped statistics.

The main outcome measures include:

- Productivity score.
- Satisfaction score.
- Accuracy rating.
- Weekly time saved.

These comparisons provide a descriptive view of differences between tools in the observed dataset.

A higher average score should not automatically be interpreted as proof that a particular tool is objectively better. Differences may reflect user characteristics, task selection, sample sizes, or other confounding factors.

### 8. Interpretation

The final stage connects the observed patterns to the original research questions.

A useful interpretation distinguishes between:

1. **Observation:** What the data or visualization shows.
2. **Interpretation:** What the pattern might mean.
3. **Limitation:** Which alternative explanations remain possible.

This distinction is important when analyzing survey-style data about technology adoption and perceived productivity.

## Areas of Analysis

The following areas summarize the main analytical dimensions of the project.

| Area | Main variables | Analytical objective |
|---|---|---|
| User demographics | Age, gender, country | Describe the composition of the dataset |
| User segmentation | User type, education, profession | Compare different user groups |
| AI adoption | AI tool, AI purpose | Examine tool popularity and usage patterns |
| Usage intensity | Daily AI usage hours | Investigate relationships with reported outcomes |
| Productivity | Productivity score | Compare perceived productivity across groups |
| Accuracy | Accuracy rating | Examine reported accuracy differences |
| Satisfaction | Satisfaction score | Explore differences in user experience |
| Efficiency | Weekly time saved | Compare reported time savings |
| Cost | Monthly AI cost, monthly income | Explore expenditure and reported outcomes |
| Recommendations | Would recommend | Examine recommendation behavior alongside other variables |

## Technology Stack

The project uses the Python data-analysis ecosystem.

| Technology | Role |
|---|---|
| Python 3.14+ | Programming language specified by the project configuration |
| Pandas | Data manipulation, cleaning, and aggregation |
| NumPy | Numerical operations |
| Matplotlib | Plot construction and customization |
| Seaborn | Statistical visualization |
| Jupyter Notebook / IPython kernel | Interactive analysis environment |
| Statsmodels | Statistical analysis capabilities available in the environment |

The exact dependency versions are recorded in `requirements.txt` and `uv.lock`.

## Getting Started

### Prerequisites

- Python 3.14 or a compatible version satisfying the project configuration.
- Git.
- Jupyter Notebook or JupyterLab.
- The dependencies listed in the repository.

### 1. Clone the Repository

```bash
git clone https://github.com/Alimov2008/AI-Usage-and-Impact-----EDA.git

cd AI-Usage-and-Impact-----EDA
```

### 2. Create a Virtual Environment

```bash
python -m venv .venv
```

Activate it on Windows:

```powershell
.venv\Scripts\activate
```

On macOS or Linux:

```bash
source .venv/bin/activate
```

### 3. Install Dependencies

Using the provided requirements file:

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

Alternatively, if you use `uv`, the repository includes both `pyproject.toml` and `uv.lock`:

```bash
uv sync
```

Use one environment-management approach consistently. If installation fails, check the Python version specified in `.python-version`, the `requires-python` constraint in `pyproject.toml`, and the availability of compatible dependency builds.

## Running the Notebook

Launch Jupyter from the repository root:

```bash
jupyter notebook
```

Open `main.ipynb` and execute the notebook sequentially.

The notebook loads the primary dataset using a relative path:

```python
df = pd.read_csv(
    "./data/AI_Usage_and_Impact_on_Students_and_Professionals.csv"
)
```

Therefore, preserve the repository's directory structure when running the notebook.

For a clean execution, restart the kernel and run all cells from top to bottom. This helps identify missing dependencies, execution-order issues, and assumptions that depend on previously executed cells.

## Methodological Considerations

### Correlation Does Not Establish Causation

An association between AI usage and productivity does not demonstrate that AI usage caused the observed productivity difference.

For example, users with higher productivity may be more likely to adopt AI, and users with different occupations may have different opportunities to benefit from it.

### Self-Reported Outcomes

Productivity, satisfaction, accuracy, and time savings are reported measures. They may not correspond directly to objectively measured performance.

### Group Size and Representativeness

The dataset contains 300 records. Comparisons between individual AI tools or professional groups may be based on substantially smaller subsets.

Always inspect group sizes and missing-data patterns before interpreting differences in averages.

### Cost and Benefit Comparisons

Reported expenditure and reported time savings represent different quantities. A cost-benefit analysis requires explicit assumptions about currency, income period, the monetary value of saved time, and whether reported time savings are attributable to AI.

A simple comparison of monthly AI cost and weekly time saved is not, by itself, a complete return-on-investment calculation.

### Data Cleaning and Reproducibility

Cleaning decisions can affect distributions and comparisons. Important transformations should be documented, and any derived dataset should be reproducible from the original data.

## Limitations

- **Dataset size:** 300 records limit the strength and generalizability of some subgroup comparisons.
- **Data quality:** Missing values, inconsistent categories, and type-conversion issues can affect the analysis.
- **Self-reported metrics:** Reported outcomes may differ from objectively measured productivity or accuracy.
- **Potential confounding:** Profession, experience, task complexity, and other characteristics may influence observed relationships.
- **Cross-sectional analysis:** The analysis does not establish how outcomes change over time.
- **Tool comparisons:** Differences in group composition may explain apparent differences between AI tools.
- **Data provenance:** The original dataset publisher, collection methodology, and license should be documented before the dataset is used as evidence beyond this project.

These limitations do not make EDA unhelpful. They define which conclusions the available data can reasonably support.

## Future Improvements

Potential extensions include:

- [ ] Add a concise executive summary with quantitative findings.
- [ ] Export selected visualizations into a dedicated `figures/` directory.
- [ ] Document the original dataset source and license.
- [ ] Separate data cleaning into reusable Python functions or a preprocessing module.
- [ ] Add explicit data-quality validation checks.
- [ ] Quantify associations using appropriate statistical tests and effect sizes.
- [ ] Include confidence intervals when comparing group-level outcomes.
- [ ] Investigate whether observed relationships remain after controlling for relevant user characteristics.
- [ ] Develop a cost-benefit analysis with clearly stated assumptions.
- [ ] Add a reproducible analysis script alongside the notebook.
- [ ] Add a final report summarizing key findings, caveats, and actionable recommendations.

GitHub: [@Alimov2008](https://github.com/Alimov2008)

---

*This project is intended for educational and analytical purposes. Findings should be interpreted in the context of the dataset's quality, collection methodology, and limitations.*
