# Submission Guidelines for Challenges


## What to Submit

Submit a **single Google Colab notebook** via Brightspace containing:
- Your code for each question
- Output/results clearly displayed
- Written interpretations in **markdown cells** (not code comments!)
- Your name at the top

---

## 📝 Required Structure

Each question should follow this format:

```
┌─────────────────────────────────────────┐
│ ## Question 1.1: Load and Inspect       │  ← Markdown cell: Question title
└─────────────────────────────────────────┘

┌─────────────────────────────────────────┐
│ import pandas as pd                     │  ← Code cell: Your code
│ df = pd.read_csv('data.csv')            │     (with comments)
│ print(f"Students: {df.shape[0]}")       │
└─────────────────────────────────────────┘
   Students: 4424                          ← Output (visible)

┌─────────────────────────────────────────┐
│ **Analysis:**                           │  ← Markdown cell: Interpretation
│ The dataset contains 4,424 students...  │     (prose, not code!)
└─────────────────────────────────────────┘
```

**Structure for Each Question:**
1. **Question** – Clearly state which question you're analyzing
2. **Code** – Provide structured and well-commented code
3. **Output** – Include results from your code
4. **Insights** (for non-factual questions) – Write interpretation (length specified per question)

---

## 💡 How to Answer Each Question

### For Factual Questions with Parts (a, b, c, d, e):

** Your code output IS your answer** - no additional markdown text needed

**Use clear labels in your code:**

```python
# a) Dataset size
print(f"Students: {df.shape[0]}, Columns: {df.shape[1]}")

# b) Column names and types
print(df.info())

# c) First 10 rows
df.head(10)

# d) Missing values
print(f"Missing values: {df.isnull().sum().sum()}")

# e) Status distribution
print(df['status'].value_counts())
```

**Key point:** Make your output self-explanatory with good print statements. We can see the answer directly from running your code.

---

### For "Write a paragraph/sentences" Questions:

** Code output is NOT sufficient**

** Must write prose in a markdown cell**

**NOT Acceptable:**
```python
# The dropout rate is 32% which is high
# We should provide more support
print(dropout_rate)
```

**Required - In Markdown Cell:**
```markdown
**Analysis:**

The university faces a significant retention challenge with a 32.1% dropout rate 
(1,421 students). This is particularly concerning in programs like Equinculture 
(55.3% dropout) and Informatics Engineering (54.1% dropout). Students with 
semester 1 success rates below 50% face a 77.4% dropout risk, suggesting early 
intervention after first semester could prevent substantial attrition.
```

**Interpretation means:**
- Full sentences
- Specific numbers from your analysis
- Your reasoning and insights
- This shows you understand what the numbers MEAN, not just how to calculate them

---

## Creating Markdown Cells in Google Colab

**Method 1: Hover Between Cells**
1. Hover your mouse over the border between existing cells
2. Click the **"+ Text"** button that appears
3. A new markdown cell is created
4. Type your interpretation
5. Click outside or press Shift+Enter to render

**Method 2: Use Menu**
1. Click on an existing cell
2. Click "Insert" in top menu
3. Choose "Text cell"

**Method 3: Keyboard Shortcut**
1. Click on a code cell
2. Press **Ctrl+M** then **B** (insert cell below)
3. Press **Ctrl+M** then **M** (convert to markdown)

---

### Required Steps

- [ ] **Run All:** Click "Runtime" → "Restart and run all" 
  - This ensures your code works from top to bottom
  - Catches any hidden dependencies or errors
  
- [ ] **Check Outputs:** Scroll through entire notebook
  - All code cells show output (no error messages)
  - Tables and results are visible (not collapsed)
  - Graphs display correctly (if applicable)

- [ ] **Verify Interpretations:** 
  - Written analysis in **markdown cells** (not code comments)
  - Each "Write X sentences" question has interpretation
  - Used specific numbers from your analysis

- [ ] **Name at Top:** First cell has your full name

- [ ] **Download File:** Ready to upload .ipynb file

---

## 📤 How to Submit on Brightspace

### Step 1: Download Your Notebook

1. Click **"File"** in the top menu
2. Select **"Download"** → **"Download .ipynb"**
3. Save to your computer
4. **Recommended filename:** `LastName_FirstName_Week1_Challenge.ipynb`
   - Example: `Smith_John_Week1_Challenge.ipynb`

**Important:** 
- Make sure you clicked "Runtime" → "Run all" BEFORE downloading
- All outputs must be visible before you download
- The downloaded file will include all your code AND outputs

---

### Step 2: Submit on Brightspace

1. Go to **Brightspace** → **Course** → **Assignments**
2. Find the correct assignment (e.g., "Week 1 Challenge")
3. Click **"Submit Assignment"**
4. Click **"Add a File"** or drag and drop
5. Select your `.ipynb` file from your computer
6. Click **"Submit"** to confirm
7. **Verify:** You should see confirmation message with your filename

---

## 📚 Resources

**In Course Repository:**
- Dataset README files for variable descriptions
- Code examples from lectures
- Python and pandas cheat sheets

**Getting Help:**
- Office hours: [Days/Times]
- Course assistant: Grishma Balgi
- Discussion forum on Brightspace

---

## Late Policy & Resubmissions

**Late Submissions:**
- Assignments due before next class
- Late accepted within 48 hours with 10% penalty per day
- After 48 hours: no credit without documented emergency

**Resubmissions:**
- If you submitted something wrong, you can resubmit before deadline
- Simply update your notebook and submit new link
- Email instructor: "I resubmitted Week X Challenge"

---

*Last updated: January 2025*
