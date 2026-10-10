<div align="center">

# 📚 Analysis of Book Publication Data

**Exploratory data analysis of book publishing data: genres, ratings, sales and publisher revenue**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

<p>
  <a href="#-overview">Overview</a> •
  <a href="#-objective">Objective</a> •
  <a href="#-technologies-used">Technologies</a> •
  <a href="#-project-structure">Structure</a> •
  <a href="#-analysis-pipeline">Pipeline</a> •
  <a href="#-key-findings">Findings</a> •
  <a href="#-how-to-use">How to Use</a> •
  <a href="#-contributing">Contributing</a> •
  <a href="#-license">License</a>
</p>

</div>

---

## 🔍 Overview

This project explores a dataset of **1,070 books** with information on publishing year, author, language, ratings, genre, sale price, units sold and publisher revenue. The notebook cleans the data, standardizes categories and answers business questions about **what sells, who earns the most and whether author reputation changes sales**, closing with a hypothesis test.

## 🎯 Objective

- Clean and validate the raw data (missing values, invalid years, duplicates)
- Understand how books are distributed by **year, genre and language**
- Compare **ratings and sales** across genres and author ratings
- Rank **publishers by revenue** and **authors by gross sales**
- Test statistically whether **famous authors sell more** than intermediate ones

## 🛠️ Technologies Used

| Tool | Purpose |
|---|---|
| **Python** | Core language |
| **Pandas** | Data loading, cleaning, grouping and aggregation |
| **Matplotlib** and **Seaborn** | Histograms, bar, pie, scatter and box plots |
| **SciPy** (`scipy.stats`) | Welch's t-test for independent samples |
| **Jupyter Notebook** | Interactive analysis |

## 📁 Project Structure

```
📁 Analysis_of_Book_Publication_Data/
├── 📁 Data/
│   └── 📄 Books_Data_Clean.csv      # Dataset (1,070 rows, 15 columns)
├── 📓 main.ipynb                    # Full analysis notebook
├── 📄 LICENSE.md                    # CC BY-NC-ND 4.0
└── 📄 README.md                     # This file
```

## 🔄 Analysis Pipeline

### 1️⃣ Data quality
- Inspected types, missing values and summary statistics (`info`, `isna`, `describe`)
- Kept books published **from 1900 onwards** and removed rows **without a book name**
- Checked for duplicates (**none found**) and unique values per column
- Result: **988 books** ready for analysis

### 2️⃣ Category standardization
- Merged `genre fiction` into `fiction`, leaving three genres: **fiction (813)**, **nonfiction (160)** and **children (15)**

### 3️⃣ Exploratory analysis
- Distribution of books by **publishing year** (histogram) and by **genre** (bar chart)
- **Average rating** by author and **ratings count / average rating by genre** (box plots)
- **Sale price vs. units sold**, **rating vs. ratings count** and **rating vs. units sold** (scatter plots, also filtered to books under 10,000 units)
- **Language** share (pie chart) and **units sold per publishing year** (line chart)
- **Publisher revenue** and **author gross sales** rankings
- **Correlation matrix** of average rating, ratings count, gross sales and sale price

### 4️⃣ Hypothesis test
- **Question:** do books by *Famous* authors sell more units than books by *Intermediate* authors?
- **Method:** Welch's t-test (`scipy.stats.ttest_ind` with `equal_var=False`)

## 💡 Key Findings

| Topic | Finding |
|---|---|
| 📚 Genres | Fiction dominates the catalog: 813 of 988 books (≈ 82%) |
| 🌐 Languages | 8 language codes, mostly English variants (`eng`, `en-US`, `en-GB`, `en-CA`) |
| ⭐ Author ratings | Intermediate (576), Excellent (336), Famous (48), Novice (28) |
| 🏢 Top publishers by revenue | Penguin Group (USA) LLC, Random House LLC, Amazon Digital Services and HarperCollins Publishers |
| 🧪 Famous vs. Intermediate authors | **t = −0.66, p = 0.51**: no statistically significant difference in units sold at the 5% level |

> The test suggests that, in this dataset, author fame alone does not explain sales volume. Genre, price and publisher are worth investigating next.

## 🚀 How to Use

1. **Clone the repository**

   ```bash
   git clone https://github.com/Laurentius96/Analysis_of_Book_Publication_Data.git
   cd Analysis_of_Book_Publication_Data
   ```

2. **Install the dependencies**

   ```bash
   pip install pandas matplotlib seaborn scipy jupyter
   ```

3. **Point the notebook to the dataset.** In the first cell of `main.ipynb`, set the path to the file in this repository:

   ```python
   df = pd.read_csv("Data/Books_Data_Clean.csv")
   ```

4. **Run the analysis**

   ```bash
   jupyter notebook main.ipynb
   ```

> 💡 No installation? Open [Google Colab](https://colab.research.google.com/), upload `main.ipynb` and `Data/Books_Data_Clean.csv`, and run all cells.

## 🔭 Next Steps

- [ ] Use a relative path to the dataset in the notebook
- [ ] Translate the remaining chart labels and comments to English
- [ ] Add a regression model for units sold (price, rating, genre, publisher)

## 🤝 Contributing

Contributions, ideas and feedback are welcome!

- 🐛 **Found a bug or something unclear?** [Open an issue](https://github.com/Laurentius96/Analysis_of_Book_Publication_Data/issues/new) describing what happened and how to reproduce it.
- 💡 **Have an idea or a question?** [Open an issue](https://github.com/Laurentius96/Analysis_of_Book_Publication_Data/issues/new) and tell me about it.
- 🔧 **Want to propose a fix?** Fork the repository, create a branch (`git checkout -b fix/short-description`), commit your changes and open a pull request explaining what changed and why.

By contributing, you agree that your contribution is shared under the same license as this project.

## 📜 License

This project is licensed under the [Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License (CC BY-NC-ND 4.0)](LICENSE.md).

**What this means:**
- ✅ You may **share** this work with **attribution**
- ❌ You may **not** use it for **commercial purposes**
- ❌ You may **not** distribute **modified versions**

---

<div align="center">

**Lorenzo C. Bianchi** · [GitHub](https://github.com/Laurentius96) · [LinkedIn](https://www.linkedin.com/in/cb-lorenzo/)

</div>
