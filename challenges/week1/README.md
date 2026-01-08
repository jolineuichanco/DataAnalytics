# Week 1 Dataset: Student Performance

**For:** Week 1 Challenge - Student Success Analysis  
**File:** `student_performance.csv`

---

## 📊 Quick Facts

- **4,424 students** from Portuguese higher education institution
- **20 variables** (demographics, academics, financials, outcomes)
- **0 missing values** - clean dataset ready to use
- **32.1% dropout rate** | 49.9% graduate | 18.0% enrolled

---

## 🚀 How to Load

### In Google Colab (Recommended)

```python
import pandas as pd

# Method 1: Load directly from GitHub
url = 'https://raw.githubusercontent.com/jolineuichanco/DataAnalytics/main/challenges/week1/student_performance.csv'
df = pd.read_csv(url)

# Method 2: Upload file to Colab
# Click folder icon → Upload button → Select student_performance.csv
df = pd.read_csv('student_performance.csv')

# Explore the data
print(df.shape)
df.head()
df.info()
```

---

## 📝 Variable Descriptions

### Demographics (4 variables)

| Variable | Type | Description | Example Values |
|----------|------|-------------|----------------|
| `student_id` | int | Unique student identifier | 1, 2, 3, ... 4424 |
| `age` | int | Age at enrollment | 17, 18, 19, ... 70 |
| `gender` | str | Student gender | Male, Female |
| `marital_status` | str | Marital status at enrollment | Single, Married, Divorced, Widowed, Union, Separated |

---

### Program Information (2 variables)

| Variable | Type | Description | Example Values |
|----------|------|-------------|----------------|
| `course` | str | Academic program enrolled | Nursing, Management, Social Service, Veterinary Nursing, Journalism, Marketing Management, Tourism, Communication Design, Animation & Design, Agronomy, Basic Education, Informatics Engineering, Equinculture, Oral Hygiene, Biofuel Production |
| `attendance` | str | Class schedule type | Daytime, Evening |

**Note:** 15 different programs, ranging from 12 students (Biofuel Production) to 766 students (Nursing)

---

### Academic Background (2 variables)

| Variable | Type | Description | Scale/Range |
|----------|------|-------------|-------------|
| `admission_grade` | float | Grade at admission | 0-200 (Portuguese system: 95+ is good, 140+ is excellent) |
| `previous_grade` | float | Prior qualification grade | 0-200 (same scale) |

**Portuguese Grading Context:**
- 0-94: Below standard
- 95-139: Adequate to good
- 140-169: Very good
- 170-200: Excellent

---

### Financial Status (3 variables)

| Variable | Type | Description | Values |
|----------|------|-------------|--------|
| `scholarship` | str | Receives financial aid | Yes, No |
| `tuition_up_to_date` | str | Tuition payments current | Yes, No |
| `debtor` | str | Owes money to university | Yes, No |

**Key Analysis Notes:**
- `scholarship = "Yes"` → Student receives financial aid
- `tuition_up_to_date = "No"` OR `debtor = "Yes"` → Financial issues
- Use OR logic: `(df['debtor'] == 'Yes') | (df['tuition_up_to_date'] == 'No')`

---

### Semester 1 Performance (4 variables)

| Variable | Type | Description | Range |
|----------|------|-------------|-------|
| `semester1_enrolled` | int | Courses enrolled in semester 1 | 0-26 courses |
| `semester1_approved` | int | Courses passed in semester 1 | 0-26 courses |
| `semester1_grade` | float | Average grade semester 1 | 0-20 (Portuguese: 10+ is passing, 14+ is good) |
| `semester1_success_rate` | float | Percent of courses passed | 0-100% (already calculated) |

**Semester 1 Grading Context:**
- 0-9: Failing
- 10-13: Passing (C to B range)
- 14-16: Good (B+ to A- range)
- 17-20: Excellent (A range)

**Success Rate:**
- 100% = Passed all courses
- 50% = Passed half the courses
- 0% = Failed all courses

---

### Semester 2 Performance (4 variables)

| Variable | Type | Description | Range |
|----------|------|-------------|-------|
| `semester2_enrolled` | int | Courses enrolled in semester 2 | 0-23 courses |
| `semester2_approved` | int | Courses passed in semester 2 | 0-23 courses |
| `semester2_grade` | float | Average grade semester 2 | 0-20 (same scale as semester 1) |
| `semester2_success_rate` | float | Percent of courses passed | 0-100% (already calculated) |

**Note:** Some students who dropped out or are struggling may have 0 for semester 2 values

---

### Outcome (1 variable)

| Variable | Type | Description | Values |
|----------|------|-------------|--------|
| `status` | str | Student final outcome | Dropout, Graduate, Enrolled |

**Status Meanings:**
- **Dropout** (32.1%): Student left university before completing degree
- **Graduate** (49.9%): Student successfully completed degree
- **Enrolled** (18.0%): Student still actively enrolled (data collected during studies)

---

## 📚 Dataset Source & Citation

**Source:** UCI Machine Learning Repository  
**Original Research:** Realinho, V., Vieira Martins, M., Machado, J., & Baptista, L. (2021)  
**Institution:** Instituto Politécnico de Portalegre, Portugal  
**License:** Creative Commons Attribution 4.0 International (CC BY 4.0)

**Full Citation:**
```
Realinho, V., Vieira Martins, M., Machado, J., & Baptista, L. (2021). 
Predict Students' Dropout and Academic Success [Dataset]. 
UCI Machine Learning Repository. 
https://doi.org/10.24432/C5MC89
```

**Original Paper:**  
"Early prediction of student's performance in higher education: a case study"  
Published in Trends and Applications in Information Systems and Technologies (2021)

**Data Collection:**
- Multiple academic years from Portuguese polytechnic institute
- Real institutional records (not simulated)
- Students across 15 different academic programs
- Includes traditional and non-traditional students

---

*Last updated: January 2025*
