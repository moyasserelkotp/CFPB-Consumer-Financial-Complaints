# CFPB Consumer Financial Complaints Analysis

## Project Overview

This project applies **Latent Semantic Analysis (LSA)** and **Singular Value Decomposition (SVD)** to automatically discover hidden complaint topics in real consumer financial complaints from the U.S. Consumer Financial Protection Bureau (CFPB).

### Problem Statement

Financial institutions receive thousands of complaints weekly that cannot be manually reviewed. This project addresses the need to:

- **Automatically discover** the main complaint topics
- **Group similar issues** together without manual labeling
- **Identify patterns** and recurring problems
- **Prioritize** the most urgent issues for resolution
- **Ensure compliance** with regulatory response requirements

---

## Dataset

### Source Information

| Property | Detail |
|---|---|
| **Dataset Name** | Consumer Financial Protection Bureau (CFPB) Complaints Database |
| **Source** | [Kaggle - CFPB Consumer Complaint Database](https://www.kaggle.com/datasets/selener/consumer-complaint-database) |
| **Text Field** | Consumer complaint narrative |
| **Category Field** | Product type |
| **Document Type** | Real customer financial complaints |

### Industries Represented

- Banks & Credit Unions
- Credit Card Companies
- Mortgage Lenders
- Student Loan Servicers
- Debt Collection Agencies

---

## Methodology

### Technique: Latent Semantic Analysis (LSA)

LSA uses **Singular Value Decomposition (SVD)** to discover hidden semantic relationships in unstructured text data without requiring labeled training data.

#### How It Works

1. **TF-IDF Vectorization** — Converts complaint text into numerical vectors
2. **SVD Decomposition** — Reduces dimensionality and uncovers latent semantic topics
3. **Similarity Analysis** — Identifies complaints discussing similar issues
4. **Topic Extraction** — Discovers which words define each hidden topic

#### Why LSA for This Problem

| Advantage | Benefit |
|---|---|
| **Unsupervised Learning** | No labeled training data required |
| **Semantic Understanding** | Related terms cluster together (e.g., "interest", "rate", "charge") |
| **Scalability** | Efficiently handles thousands of documents |
| **Interpretability** | Topic meanings discoverable from high-loading words |
| **No Domain Expertise Needed** | Automatically finds patterns across complaint text |

---

## Project Structure

```
CFPB Consumer Financial Complaints/
├── README.md                                    # This file
├── CFPB_Consumer_Financial_Complaints.ipynb    # Main analysis notebook
├── data/                                        # (if applicable)
│   └── consumer_complaints.csv                 # CFPB dataset
└── output/                                      # (if generated)
    ├── topic_analysis.csv
    ├── complaint_similarities.csv
    └── visualizations/
```

---

## Analysis Sections

### 1. Data Loading & Exploration
- Load CFPB complaint dataset
- Examine complaint distribution by product type
- Explore text statistics and vocabulary

### 2. Text Preprocessing
- Remove HTML tags and special characters
- Normalize text case
- Remove stopwords using spaCy
- Lemmatization for feature extraction

### 3. Feature Extraction (TF-IDF)
- Convert complaint text to TF-IDF vectors
- Configure vectorizer for optimal feature representation
- Analyze term frequency distributions

### 4. Dimensionality Reduction (SVD)
- Apply Truncated SVD to discover latent topics
- Determine optimal number of components
- Extract latent semantic space

### 5. Topic Discovery
- Identify key words defining each latent topic
- Interpret semantic meaning of discovered topics
- Visualize topic relationships

### 6. Similarity Analysis
- Calculate cosine similarity between complaint vectors
- Identify groups of similar complaints
- Find most representative complaints for each topic

### 7. Insights & Recommendations
- Pattern identification across complaint types
- Severity and frequency analysis
- Actionable insights for complaint handling

---

## Technologies & Libraries

### Core Libraries

| Library | Purpose |
|---|---|
| **pandas** | Data manipulation and exploration |
| **numpy** | Numerical computations |
| **scikit-learn** | SVD, TF-IDF vectorization, similarity metrics |
| **spaCy** | Natural language processing and lemmatization |

### Visualization Libraries

| Library | Purpose |
|---|---|
| **matplotlib** | Static visualizations |
| **seaborn** | Statistical data visualization |
| **plotly** | Interactive visualizations |

### Requirements

- Python 3.7+
- See dependencies in notebook imports section

---

## Getting Started

### Prerequisites

Ensure you have the following installed:

```bash
pip install pandas numpy scikit-learn spacy matplotlib seaborn plotly
python -m spacy download en_core_web_sm
```

### Running the Analysis

1. Download the CFPB dataset from [Kaggle](https://www.kaggle.com/datasets/selener/consumer-complaint-database)
2. Place the dataset in the project directory
3. Open `CFPB_Consumer_Financial_Complaints.ipynb` in Jupyter Notebook or JupyterLab
4. Run cells sequentially to execute the analysis

### Expected Outputs

- **Topic distributions** across complaint categories
- **Similarity matrices** between complaints
- **Visualizations** of latent topics and complaint clusters
- **Statistical summaries** of complaint patterns

---

## Key Findings & Insights

The analysis reveals:

- **Hidden complaint topics** not explicitly labeled in the dataset
- **Semantic relationships** between seemingly different complaint types
- **Clustering patterns** showing groups of similar issues
- **Topic-specific vocabulary** characteristic of each complaint category
- **Actionable recommendations** for complaint prioritization and handling

---

## Business Applications

### For Financial Institutions

1. **Automated Triage** — Route complaints to appropriate departments
2. **Duplicate Detection** — Identify related complaints for batch resolution
3. **Trend Analysis** — Detect emerging complaint patterns
4. **Quality Assurance** — Ensure response consistency for similar issues
5. **Product Development** — Identify features causing recurring complaints

### For Regulators

1. **Compliance Monitoring** — Track complaint trends by institution
2. **Risk Assessment** — Identify systemic issues across the industry
3. **Consumer Protection** — Prioritize areas needing regulatory action

---

## Limitations & Future Work

### Current Limitations

- Analysis based on text only (metadata not incorporated)
- SVD requires parameter tuning for optimal results
- Computational constraints for very large datasets
- Language-specific implementation (English complaints only)

### Future Enhancements

- Incorporate temporal analysis (complaint trend evolution)
- Add metadata features (complaint resolution outcome, institution type)
- Implement hierarchical clustering for nested topics
- Develop real-time complaint processing pipeline
- Extend to multilingual complaint analysis
- Compare with modern NLP approaches (word embeddings, transformers)

---

## References

- **Dataset Source**: [Kaggle - CFPB Consumer Complaint Database](https://www.kaggle.com/datasets/selener/consumer-complaint-database)
- **Data Provider**: [Consumer Financial Protection Bureau](https://www.consumerfinance.gov/)
- **SVD/LSA Reference**: Deerwester et al. (1990) - "Indexing by Latent Semantic Analysis"
- **TF-IDF Reference**: [scikit-learn Documentation](https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.TfidfVectorizer.html)

---

## Author Notes

This project was completed as an assignment in multivariate analysis, demonstrating practical applications of dimensionality reduction techniques to real-world text analysis problems.

---

## License

This project uses publicly available data from the CFPB. Refer to the [CFPB Data License](https://www.consumerfinance.gov/) for usage terms.

---

**Last Updated**: May 2026  
**Project Status**: Complete

