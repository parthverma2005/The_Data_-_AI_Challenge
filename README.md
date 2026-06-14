# The_Data_-_AI_Challenge

# Intelligent Candidate Discovery & Ranking System

> AI-powered candidate ranking engine built for the Redrob AI Hackathon.

## Overview

Traditional Applicant Tracking Systems (ATS) rely heavily on keyword matching, often missing highly qualified candidates while rewarding keyword stuffing. This project introduces an intelligent candidate discovery and ranking system that evaluates candidates holistically using semantic understanding, career progression analysis, technical expertise assessment, and behavioral signals.

The system is designed to mimic how an experienced recruiter evaluates talent rather than simply matching keywords.

---

## Problem Statement

Recruiters review hundreds or thousands of profiles for a single role.

### Challenges

- Keyword-based matching misses qualified candidates
- Candidates can manipulate rankings through keyword stuffing
- Career progression is ignored
- Behavioral and engagement signals are overlooked
- Recruiters receive low-quality shortlists

### Goal

Build an AI-driven ranking system that understands the intent behind a Job Description and identifies candidates who genuinely fit the role.

---

## Solution Architecture

```text
Job Description
       │
       ▼
Semantic Understanding
       │
       ▼
Feature Extraction
       │
       ▼
Candidate Embeddings
       │
       ▼
Hybrid Scoring Engine
       │
       ▼
Behavioral Signal Analysis
       │
       ▼
Candidate Ranking
       │
       ▼
Explainable Recommendations
```

---

## Key Features

### Semantic Candidate Understanding

- Uses Sentence Transformers for semantic embeddings
- Understands contextual meaning instead of exact keyword matching
- Identifies related skills and transferable experience

### Career Progression Analysis

Evaluates:

- Years of experience
- Seniority growth
- Product-company experience
- Relevant project exposure

### Technical Expertise Assessment

Identifies expertise in:

- Machine Learning
- Information Retrieval
- Search Systems
- Recommendation Systems
- Ranking Infrastructure
- Vector Databases
- LLM Applications

### Behavioral Signal Analysis

Leverages platform signals such as:

- Recruiter responsiveness
- Activity levels
- Engagement patterns
- Availability indicators

### Explainable AI

Provides recruiter-friendly reasoning for every recommendation.

**Example:**

> Candidate has 7 years of production ML experience, previously built recommendation systems, demonstrates strong retrieval expertise, and shows high recruiter engagement.

---

## Tech Stack

### Programming Language

- Python 3.10+

### Machine Learning

- Sentence Transformers
- Scikit-Learn
- NumPy
- Pandas

### Retrieval & Similarity

- FAISS
- Cosine Similarity

### Development Environment

- Google Colab
- Jupyter Notebook

---

## Project Structure

```text
redrob-ai-ranking/
│
├── data/
│   ├── candidates.jsonl.gz
│   ├── sample_candidates.json
│
├── notebooks/
│   ├── training.ipynb
│
├── src/
│   ├── embeddings.py
│   ├── ranking.py
│   ├── reasoning.py
│   ├── feature_engineering.py
│
├── outputs/
│   ├── submission.csv
│
├── requirements.txt
├── README.md
└── submission_metadata.yaml
```

---

## Dataset

Each candidate profile contains:

- Candidate ID
- Profile Summary
- Career History
- Education
- Skills
- Certifications
- Languages
- Behavioral Signals

### Dataset Size

- 100,000 Candidates

---

## Methodology

### Step 1: Candidate Profile Construction

Multiple fields are merged into a unified candidate representation:

- Profile
- Career History
- Skills
- Education
- Certifications
- Languages

### Step 2: Embedding Generation

Candidate profiles and Job Descriptions are converted into dense vector embeddings using:

```python
all-MiniLM-L6-v2
```

### Step 3: Semantic Retrieval

Cosine similarity identifies candidates whose profiles are semantically aligned with the Job Description.

### Step 4: Feature Engineering

Additional ranking signals include:

- Skill Match Score
- Career Relevance Score
- Seniority Score
- Behavioral Score
- Availability Score

### Step 5: Hybrid Ranking

```text
Final Score =
0.40 × Semantic Similarity
+ 0.25 × Career Relevance
+ 0.15 × Skill Match
+ 0.10 × Behavioral Signals
+ 0.05 × Availability
- 0.05 × Risk Penalty
```

### Step 6: Explainable Output

Top candidates are returned with ranking explanations and confidence scores.

---

## Installation

### Clone Repository

```bash
git clone https://github.com/yourusername/redrob-ai-ranking.git

cd redrob-ai-ranking
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Running the Project

### Generate Candidate Rankings

```bash
python rank.py \
--candidates ./data/candidates.jsonl.gz \
--output ./outputs/submission.csv
```

---

## Output Format

The generated submission follows the official competition format:

```csv
candidate_id,rank,score,reasoning
CAND_000001,1,0.985,...
CAND_000002,2,0.978,...
```

### Requirements

- Top 100 candidates only
- Unique candidate IDs
- Unique ranks
- Non-increasing scores

---

## Performance Goals

- CPU-only execution
- Runtime under 5 minutes
- Memory usage below 16 GB
- No external API calls
- Scalable to 100,000 candidates

---

## Future Improvements

- Learning-to-Rank Models
- Cross-Encoder Re-ranking
- Fine-Tuned Domain Embeddings
- Graph-Based Talent Discovery
- Recruiter Feedback Loop
- Online Ranking Optimization

---

## Results

1 Semantic candidate understanding

2 Behavioral intelligence integration

3 Explainable recommendations

4 Scalable ranking pipeline

5 Production-friendly architecture

---

## Hackathon Submission Components

This repository contains:

- Complete source code
- Ranking pipeline
- Reproducible workflow
- Submission generation script
- Documentation

### Deliverables

1. GitHub Repository
2. Presentation PDF
3. Ranked Candidate CSV

---

## Author

Developed for the **Redrob AI Hackathon**

**Building hiring systems that understand people, not just keywords.**
