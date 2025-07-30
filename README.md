# Synthetic-Health-Reddit-Dataset
Synthetic dataset combining datasets from the Hugging Face Datasets Hub for AI training and analysis.

---

## Project Overview ##
This project creates a synthetic dataset by combining:

- Reddit-style mental health posts

- Structured hospital admission records

The goal is to analyze the structure and distribution of the datasets and design a large merged schema that includes important features for training and testing ML models. 

---

## Tools & Libraries Used

| Tool | Purpose |
|------|---------|
| **Hugging Face Datasets** | Source for open-access Reddit and healthcare datasets |
| **datasets** library | Load datasets via Python |
| **pandas, numpy** | Data manipulation and merging |
| **Faker** | Generating realistic synthetic Reddit post content |

---

## 🛠️ Methodology

Step 1: Data Sourcing
- Loaded `solomonk/reddit_mental_health_posts` for Reddit-style mental health text  
- Loaded `Nicolybgs/healthcare_data` (500,000 rows) for hospital admission records  

Step 2: API-Based Loading
- Used `datasets.load_dataset()` to pull in both datasets  
- Preprocessed columns for consistency  

Step 3: Data Synthesis
- Randomly sampled hospital features (age, gender, diagnosis, etc.)  
- Paired them with synthetic Reddit posts generated via `Faker`  
- Created 100,000 synthetic records  

Step 4: Cleaning & Missing Value Strategy
- Filled ~30k missing `diagnosis` values with `"Other"` for realism and data integrity  

---

## Features in Final Dataset

- `title`, `body`, `subreddit`, `score`, `num_comments`  
- `age`, `gender`, `diagnosis`, `severity`, `insurance`, `stay_days`, `admission_type`

---

**Example Record:**

```json
{
  "title": "Tired of always pretending.",
  "body": "Sometimes I just want to stop being okay for others. I’m tired...",
  "subreddit": "r/depression",
  "score": 251,
  "num_comments": 72,
  "age": "31-40",
  "gender": "Female",
  "diagnosis": "Diabetes",
  "severity": "Moderate",
  "insurance": "Yes",
  "stay_days": 9,
  "admission_type": "Urgent"
}

