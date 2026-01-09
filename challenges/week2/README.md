# Week 2 Challenge: Zagat Restaurant Analysis

**IE-GY 9113: Data Analytics for Operational Excellence**

**Due: Before Week 3 class**

---

## Overview

The Zagat dataset contains restaurant evaluations based on specific components: **food**, **décor**, and **service**, using a 30-point scale (30 = highest, 1 = lowest). The dataset also includes estimated **price** (cost per person).

**Dataset Source:** https://raw.githubusercontent.com/jcbonilla/Analytics/master/BAData/zagat.CSV

**Your task:** Analyze the dataset using Python to answer 10 questions about restaurant performance patterns.

---

## Question 1: Data Loading (5 points)

**Start by loading the 'zagat.csv' file from Github into Python. Wake up that data!**

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Load the data
url = 'https://raw.githubusercontent.com/jolineuichanco/DataAnalytics/main/week2/zagat.CSV'
df = pd.read_csv(url)

# Display the data
# Your code here:
```

**What to include:**
- Show the first few rows of data
- Report the number of restaurants in the dataset
- Confirm that the data loaded successfully

---

## Question 2: Stats at a Glance (10 points)

**Get a feel for your data. Compute those quick summary statistics for price, décor, service, and food quality.**

```python
# Your code here:
# Use .describe() to get summary statistics
```

**What to write:**
For each dimension (Food, Decor, Service, Price), report:
- Mean
- Median  
- Min and Max
- 25th and 75th percentiles

**Interpretation:** What do these numbers tell you about the restaurants in this dataset?

---

## Question 3: Spotting the Underperformers (10 points)

**How many restaurants are not making the cut? You know, the ones below average in price, décor, service, AND food? Find them!**

```python
# Your code here:
# Calculate mean for each dimension
# Filter for restaurants below average on ALL FOUR dimensions
# Use & operator to combine conditions

# Example structure:
# underperformers = df[(df['Food'] < mean_food) & 
#                      (df['Decor'] < mean_decor) & 
#                      (df['Service'] < mean_service) & 
#                      (df['Price'] < mean_price)]
```

**What to write:**
- How many restaurants are underperformers?
- What percentage of the total is this?
- Show the names and ratings of 2-3 example underperformers
- What do you notice about them?

---

## Question 4: Measures of Central Tendency (15 points)

**Define and explain the measures of central tendency (mean, median, mode) for price, décor, service, and food quality. Should you use the mean, median, or mode? Think about what makes more sense here and why.**

```python
# Your code here:
# Calculate mean, median, and mode for each dimension

# For mode (most common value):
# df['Food'].mode()
```

**What to write:**

**Part A: Define the measures (3 points)**
- What is the mean? 
- What is the median?
- What is the mode?

**Part B: Calculate for each dimension (8 points)**
For Food, Decor, Service, and Price, report:
- Mean
- Median
- Mode (if applicable)

**Part C: Which to use? (4 points)**
- For this restaurant dataset, which measure (mean, median, or mode) should you use to describe "typical" values? 
- Justify your choice for each dimension
- Are mean and median similar or different? What does this tell you about the distribution?

---

## Question 5: Variety is the Spice of Life (10 points)

**Which aspect (price, décor, service, food quality) shows the most variability? Figure this out using standard deviation.**

```python
# Your code here:
# Calculate standard deviation for each dimension
# df['Food'].std()
# df['Decor'].std()
# ...
```

**What to write:**
- Report the standard deviation for Food, Decor, Service, and Price
- Which dimension has the HIGHEST standard deviation?
- Which has the LOWEST?
- What does high vs. low variability mean in practical terms for restaurants?
- Why might one dimension be more variable than others?

---

## Question 6: Connecting the Dots (15 points)

**Time to play detective! Which dimensions are highly correlated? Use correlation analysis and visualization to find out. Once you spot those high correlations, think about what they might mean.**

```python
# Your code here:
# Calculate correlation matrix
# corr_matrix = df[['Food', 'Decor', 'Service', 'Price']].corr()

# Create correlation heatmap
# plt.figure(figsize=(8, 6))
# sns.heatmap(corr_matrix, annot=True, cmap='coolwarm', 
#             center=0, vmin=-1, vmax=1, square=True)
# plt.title('Restaurant Ratings Correlation Heatmap')
# plt.show()
```

**What to write:**
- Show your correlation matrix (the numbers)
- Include your correlation heatmap visualization
- Which two dimensions have the STRONGEST correlation? What is the correlation value?
- Which dimensions have WEAK correlations?
- What do these correlations tell you about restaurants? (For example: if food and decor are highly correlated, what does that mean?)
- Important: Do these correlations prove causation? Why or why not?

---

## Question 7: The Best and the Worst (15 points)

**Based on your analysis, who's the top dog and who's lagging behind? Identify the best and worst restaurants and back it up with reasons.**

```python
# Your code here:
# First, define what "best" means
# Option 1: Average the three rating dimensions
# df['avg_rating'] = (df['Food'] + df['Decor'] + df['Service']) / 3

# Find best and worst
# best = df.nlargest(1, 'avg_rating')
# worst = df.nsmallest(1, 'avg_rating')

# Or: df.loc[df['avg_rating'].idxmax()]
```

**What to write:**
- How did you define "best" restaurant? (Average? Weighted score? Something else?)
- Which restaurant is the BEST? Show all its ratings (Food, Decor, Service, Price)
- Which restaurant is the WORST? Show all its ratings
- Compare them: What specific numbers make the best restaurant excellent?
- Back it up: Use your earlier analysis (mean, median, correlations) to explain why these restaurants stand out

---

## Question 8: Creating Your Own Score (10 points)

**Let's get creative! Come up with a scoring system using a weighted average. Mix and match columns with some arithmetic magic.**

Example formula structure: `0.5*price/max(price) + 0.5*food/max(food)`

```python
# Your code here:
# Create your custom score using weighted averages
# Make sure to normalize each dimension (divide by max)

# Example:
# df['custom_score'] = (
#     0.4 * df['Food'] / df['Food'].max() +
#     0.3 * df['Service'] / df['Service'].max() +
#     0.2 * df['Decor'] / df['Decor'].max() +
#     0.1 * (1 - df['Price'] / df['Price'].max())
# ) * 100
```

**What to write:**
- What weights did you choose for each dimension? (e.g., 40% food, 30% service...)
- Why did you choose these specific weights? Justify your reasoning
- How did you handle price? (Is higher price better or worse?)
- Show your formula clearly
- Display the top 5 restaurants according to your custom score

---

## Question 9: Divide and Conquer (5 points)

**With your custom score, categorize restaurants into "above average" and "below average".**

```python
# Your code here:
# Calculate the mean of your custom score
# mean_score = df['custom_score'].mean()

# Categorize
# df['category'] = np.where(df['custom_score'] > mean_score, 
#                           'Above Average', 
#                           'Below Average')

# Count how many in each category
# df['category'].value_counts()
```

**What to write:**
- How many restaurants are "above average"?
- How many are "below average"?
- Show a few example restaurants from each category with their scores

---

## Question 10: Comparing the Groups (15 points)

**Lastly, compute and compare summary statistics for your two segments of restaurants.**

```python
# Your code here:
# Compare the two groups
# df.groupby('category')[['Food', 'Decor', 'Service', 'Price', 'custom_score']].agg(['mean', 'median', 'std'])

# Or calculate separately:
# above_avg = df[df['category'] == 'Above Average']
# below_avg = df[df['category'] == 'Below Average']
```

**What to write:**
- For "Above Average" restaurants, report: mean Food, Decor, Service, Price
- For "Below Average" restaurants, report: mean Food, Decor, Service, Price
- How do the two groups differ?
- Which dimension shows the BIGGEST difference between above and below average?
- Is there a price difference between the two groups? What does this tell you?
- Based on this comparison, what makes a restaurant "above average"?

---

## Deliverable

**Submit:** One Google Colab notebook file (.ipynb)

**Filename:** `LastName_FirstName_Week2_Challenge.ipynb`

**Your notebook must include:**
- All 10 questions answered in order
- Python code for each question (clearly commented)
- Outputs visible (run all cells before submitting!)
- Written interpretations for each question (in Markdown cells)
- Your name at the top

**Format:**
```
# Week 2 Challenge: Zagat Restaurant Analysis
**Name:** Your Name
**Date:** [Date]

## Question 1: Data Loading
[Code cell]
[Output]
[Markdown cell with interpretation]

## Question 2: Stats at a Glance
[Code cell]
[Output]
[Markdown cell with interpretation]

[... continue for all 10 questions]
```

**Where to submit:** Upload .ipynb file to Brightspace

**Due:** Before Week 3 class

---

## Grading Rubric (100 points total)

| Question | Points | What we're grading |
|----------|--------|-------------------|
| Q1: Data Loading | 5 | Data loaded correctly, basic exploration shown |
| Q2: Summary Stats | 10 | Complete statistics reported, basic interpretation |
| Q3: Underperformers | 10 | Correct filtering logic, counts accurate |
| Q4: Central Tendency | 15 | Definitions clear, calculations correct, justification strong |
| Q5: Variability | 10 | SD calculated correctly, interpretation meaningful |
| Q6: Correlation | 15 | Matrix + heatmap correct, interpretation insightful |
| Q7: Best & Worst | 15 | Clear criteria, backed up with data |
| Q8: Custom Score | 10 | Creative scoring system, justified weights |
| Q9: Categorization | 5 | Correct categorization |
| Q10: Group Comparison | 15 | Thorough comparison, actionable insights |
| **Total** | **110** | (10 points extra credit built in!) |

**Grading emphasis:**
- **Code (40%):** Does it run? Is it correct?
- **Calculations (30%):** Are the numbers right?
- **Interpretations (30%):** Do you explain what the numbers MEAN?



**Good luck! Remember: Show your work, explain your thinking, and use specific numbers to back up your points!** 🎯📊
