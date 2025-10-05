# pandas_complete

This repository offers a complete journey through the `pandas` library, featuring both foundational and advanced techniques. It is organized around two main projects for real-world practice:

1. **Anime Feature Extraction Project**  
   Learn to extract, engineer, and preprocess features from an anime dataset using only pandas.

2. **Countries Data Insights Project**  
   Gain insights and perform data analysis on country statistics, using pandas for all data manipulation and summaries.

---

## Table of Contents

- [About](#about)
- [Projects](#projects)
  - [Anime Feature Extraction](#anime-feature-extraction)
  - [Countries Data Insights](#countries-data-insights)
- [Installation](#installation)
- [Usage](#usage)
- [Requirements](#requirements)
- [Contributing](#contributing)
- [License](#license)

---

## About

This repository provides a comprehensive path through the pandas library, focusing on:

- Data loading, cleaning, and preparation
- Feature engineering and extraction
- Exploratory data analysis (EDA)
- Aggregation, grouping, and pivoting
- Handling missing values and outliers
- Merging, joining, and reshaping data

All code and projects use **only pandas** for operations and visualizations (e.g., pandas’ built-in plotting functions).

---

## Projects

### Anime Feature Extraction

- **Goal:** Extract and engineer features from an anime dataset.
- **Techniques Used:**
  - Data cleaning and preprocessing
  - Parsing and handling categorical/numeric data
  - Creating new feature columns
  - Data exploration

#### Example Code

```python
import pandas as pd

# Load anime dataset
df = pd.read_csv('anime.csv')

# Clean: Drop rows with missing genres
df = df.dropna(subset=['genre'])

# Feature: Split genres into lists
df['genre_list'] = df['genre'].str.split(',')

# Feature: Count genres
df['genre_count'] = df['genre_list'].apply(len)

# Simple EDA with pandas plotting
df['genre_count'].value_counts().sort_index().plot.bar()
```

---

### Countries Data Insights

- **Goal:** Analyze and summarize country data (e.g., population, GDP, region).
- **Techniques Used:**
  - Grouping and aggregation (e.g., by continent)
  - Statistical summaries (mean, median, etc.)
  - Insights with pandas' plotting

#### Example Code

```python
import pandas as pd

# Load countries data
df = pd.read_csv('countries.csv')

# Group by continent and calculate average population
continent_pop = df.groupby('continent')['population'].mean()

print(continent_pop)

# Visualize directly with pandas
continent_pop.plot.bar(title='Average Population by Continent')
```

---

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/Bhawneet1/pandas_complete.git
   cd pandas_complete
   ```
2. (Optional) Set up a virtual environment.

3. Install requirements:
   ```bash
   pip install -r requirements.txt
   ```

---

## Usage

- Browse the code and notebooks in this repository.
- Run and modify the code to learn and experiment with pandas features.
- Use your own datasets for practice.

---

## Requirements

- Python 3.7+
- pandas

Install requirements with:
```bash
pip install pandas
```

---

## Contributing

Contributions, issues, and feature requests are welcome!

---

## License

This project is licensed under the MIT License.
