# IE-GY 9113: Data Analytics for Process Analysis

**NYU Tandon School of Engineering**  
**Department of Technology Management and Innovation**  
**Masters of Industrial Engineering Program**

---

## 📚 Course Repository

This repository contains all datasets, challenge assignments, code examples, and resources for IE-GY 9113: Data Analytics for Operational Excellence.

**Instructor:** Prof. Joline Uichanco  
**Semester:** Spring 2025

---

## 🗂️ Repository Structure

```
IE-GY-9113-Data-Analytics/
├── README.md                          # This file
├── datasets/                          # All course datasets
│   ├── week1_student_performance/
│   │   ├── student_performance.csv
│   │   └── README.md                  # Dataset documentation
│   ├── week2_[dataset_name]/
│   └── projects/
├── challenges/                        # Weekly challenge assignments
│   ├── submission_guidelines.md       # Instructions on submissions
│   ├── week1_student_success/
│   │   ├── Week1_Challenge.pdf
│   │   └── README.md
│   ├── week4_statistical_tests/
│   └── ...
├── code_examples/                     # Instructor code demonstrations
│   ├── week1_pandas_basics/
│   ├── week2_data_cleaning/
│   └── ...
└── projects/                          # Course project guidelines
    ├── project1_guidelines.pdf
    ├── project2_guidelines.pdf
    └── project3_guidelines.pdf
```

---

## 📊 Datasets

All datasets used in this course are stored in the `datasets/` directory. Each dataset has its own folder containing:
- The data file(s) (`.csv`, `.xlsx`, etc.)
- A README with variable descriptions, sources, and usage notes

### Available Datasets

| Week | Dataset | Description | Size |
|------|---------|-------------|------|
| 1 | Student Performance | Real student dropout and success data from UCI ML Repository | 4,424 rows |
| 2 | [Coming Soon] | | |
| 3 | [Coming Soon] | | |

### Using the Datasets

**Option 1: Download from GitHub**
- Navigate to the specific dataset folder
- Click on the `.csv` file
- Click "Download" button

**Option 2: Direct URL in Google Colab**
```python
import pandas as pd

# Replace with actual raw GitHub URL
url = 'https://raw.githubusercontent.com/jolineuichanco/DataAnalytics/main/datasets/week1_student_performance/student_performance.csv'
df = pd.read_csv(url)
```

---

## 📝 Challenge Assignments

Weekly challenges are posted in the `challenges/` directory. Each challenge includes:
- Assignment PDF with questions and requirements
- Dataset references
- Submission guidelines

### Challenge Schedule

| Week | Topic | Dataset | Due Date |
|------|-------|---------|----------|
| 1 | Student Success Analysis | Student Performance | Before Week 2 |
| 2 | [Coming Soon] | | |
| 3 | [Coming Soon] | | |

### Submission Guidelines

All challenges should be submitted as **Google Colab notebooks** via Brightspace containing:
1. Your name at the top
2. Code for each question
3. Outputs clearly displayed
4. Written interpretations in markdown cells
5. Run All before submitting

---

## 💻 Code Examples

The `code_examples/` directory contains instructor demonstrations from class lectures:
- Jupyter notebooks with code walkthroughs
- Step-by-step tutorials
- Common patterns and techniques

These are reference materials - you're welcome to use them to understand concepts, but challenge submissions must be your own work.

---

## 📚 Resources

### Python & Pandas
- [Python Cheat Sheet](resources/python_cheat_sheet.pdf) - Quick reference for Python basics
- [Pandas Reference](resources/pandas_reference.pdf) - Common pandas operations
- [Official Pandas Documentation](https://pandas.pydata.org/docs/)

### Data Visualization
- [Matplotlib Guide](resources/matplotlib_guide.pdf)
- [Seaborn Tutorial](resources/seaborn_tutorial.pdf)

### Statistics
- [Statistical Tests Decision Tree](resources/stats_decision_tree.pdf)
- [Hypothesis Testing Guide](resources/hypothesis_testing.pdf)

### Getting Help
- **Office Hours:** [Days/Times]
- **Course Assistant:** Grishma Balgi - [email]
- **Discussion Forum:** Brightspace
- **Python Help:** Stack Overflow, Python documentation

---

## 🎓 Projects

Major course projects are documented in the `projects/` directory. Projects require:
- Real data analysis on company problems
- Team collaboration (3-4 students)
- Written report and presentation

### Project Timeline

| Project | Topic | Timeline |
|---------|-------|----------|
| 1 | Operational Diagnosis | Weeks 3-5 |
| 2 | Predictive Analytics | Weeks 8-11 |
| 3 | End-to-End Improvement | Weeks 12-15 |

---

## 🚀 Getting Started

### For Students New to Python

1. **Install Python & Anaconda**
   - Download from [anaconda.com](https://www.anaconda.com/)
   - Installs Python, Jupyter, and essential libraries

2. **Set Up Google Colab** (Recommended)
   - Go to [colab.research.google.com](https://colab.research.google.com/)
   - Sign in with your NYU Google account
   - No installation needed!

3. **Learn the Basics**
   - Complete [Python for Beginners](https://www.python.org/about/gettingstarted/) tutorial
   - Review Week 1 lecture slides
   - Try the code examples in `code_examples/week1_pandas_basics/`

### Quick Start: Week 1 Challenge

```python
# 1. Open Google Colab
# 2. Create new notebook
# 3. Load the dataset

import pandas as pd

# Option A: Upload file directly to Colab
df = pd.read_csv('student_performance.csv')

# Option B: Load from GitHub (replace URL)
url = 'https://raw.githubusercontent.com/[username]/IE-GY-9113/main/datasets/week1_student_performance/student_performance.csv'
df = pd.read_csv(url)

# 4. Start exploring!
df.head()
df.info()
df.describe()
```


---

## ⚖️ Academic Integrity

### Collaboration Policy

**✅ Allowed:**
- Discussing concepts and approaches with classmates
- Using code examples from lectures and `code_examples/` as reference
- Getting help from instructor, course assistant, or office hours
- Using AI tools (ChatGPT, Gemini) to learn and debug

**⚠️ Requires Citation:**
- Code adapted from Stack Overflow or other online sources
- AI-assisted code (note which parts used AI help)

**❌ Not Allowed:**
- Sharing your code with other students
- Copying code from classmates or previous years
- Using AI to write entire assignments without understanding
- Submitting work you cannot explain

### Remember

**Exams are closed-everything.** If you use AI to complete challenges without learning, you will struggle on:
- Midterm (no AI, write pandas code from scratch)
- Final (comprehensive analysis, no AI)
- Projects (require synthesis AI cannot do)


## 📧 Contact

**Questions about course content?**  
- Post in Brightspace discussion forum
- Attend office hours: [Days/Times]

**Technical issues with repository?**  
- Email instructor: joline.uichanco@nyu.edu
- File an issue on GitHub (if you know how)

**Course administration questions?**  
- Email course assistant: Grishma Balgi - [email]

---

## 📄 License & Attribution

### Course Materials
Course materials (lectures, assignments, projects) © 2025 Joline Uichanco, NYU Tandon School of Engineering. All rights reserved.

These materials are provided for educational use by enrolled students only. Redistribution or commercial use is not permitted without permission.

### Datasets

**Student Performance Dataset**
- Source: UCI Machine Learning Repository
- Original Research: Realinho et al. (2021), Instituto Politécnico de Portalegre, Portugal
- License: Creative Commons Attribution 4.0 International (CC BY 4.0)
- Citation: Realinho, V., Vieira Martins, M., Machado, J., & Baptista, L. (2021). Predict Students' Dropout and Academic Success [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5MC89

Additional datasets will be attributed as they are added to the repository.


---

**Welcome to IE-GY 9113! Let's learn to turn data into operational excellence. 📊🚀**

---

*Last updated: January 2025*
