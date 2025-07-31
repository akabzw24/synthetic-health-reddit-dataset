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
| **library** | Load datasets via Python |
| **pandas, numpy** | Data manipulation and merging |
| **Faker** | Generating realistic synthetic Reddit post content |

---

## Methodology

Step 1: Data Sourcing
- Loaded `solomonk/reddit_mental_health_posts` for Reddit-style mental health text  
- Loaded `Nicolybgs/healthcare_data` (500,000 rows) for hospital admission records  

Step 2: API-Based Loading
- Used `datasets.load_dataset()` to pull in both datasets  
- Preprocessed columns for consistency  

Step 3: Data Synthesis
- Randomly sampled features (age, gender, diagnosis, etc.)  
- Paired them with synthetic Reddit posts generated via `Faker`  
- Created 100,000 synthetic records  

Step 4: Cleaning Missing Values
- Filled 30304 missing `diagnosis` values with `"Other"` to best match the real-world scenario.   

---

## Features in Final Dataset

- `title`, `body`, `subreddit`, `score`, `num_comments`  
- `age`, `gender`, `diagnosis`, `severity`, `insurance`, `stay_days`, `admission_type`

---

**Example Record:**

```json
{
  "title": "Hear kid actually again.",
  "body": "Maybe what address tonight song and happy. Deep fact western book evening threat choose...",
  "subreddit": "r/ocd",
  "score": 2,
  "num_comments": 38,
  "age": "31-40",
  "gender": "Female",
  "diagnosis": "Diabetes",
  "severity": "Moderate",
  "insurance": "No",
  "stay_days": 7,
  "admission_type": "Trauma"
}

