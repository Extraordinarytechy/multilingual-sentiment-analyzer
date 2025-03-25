# Twitter Multilingual Sentiment Analysis

## Project Overview
Two interconnected NLP projects analyzing tweet sentiment, comparing models (BERT vs. XLM-Roberta), and extracting business insights.

# Key Features
| Feature | Implementation Details |
|---------|------------------------|
| Multilingual Analysis | `bert-base-multilingual-uncased` model |
| Data Visualization | Matplotlib histograms |
| Export Results | CSV generation with confidence scores |

# Sample Output
{'label': '5 stars', 'score': 0.89}

# Technical Stack
```python
from transformers import pipeline
classifier = pipeline("text-classification", 
                     model="nlptown/bert-base-multilingual-uncased-sentiment")
classifier("I loved the service!")  # Output: {'label': '5 stars', 'score': 0.89}
```

# How to Run
```bash
# Clone repository
git clone https://github.com/your-username/multilingual-sentiment-analyzer.git

# Open in Colab:
[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/extraordinarytechy/multilingual-sentiment-analyzer/blob/main/notebooks/twitter_sentiment_analysis.ipynb)

```markdown
# Multilingual Sentiment Analysis Projects

# Project 1: Twitter Sentiment Analysis with BERT
Goal: Built a baseline sentiment classifier for multilingual tweets.

# Key Achievements
- Processed 500+ tweets from the `sentiment140` dataset
- Achieved 82% accuracy in detecting negative/positive sentiment
- Discovered model limitation with sarcasm (e.g., "Great job... not!")


 Files:  
- `notebooks/twitter_sentiment.ipynb`  
- `data/twitter_results.csv`  
- `assets/sentiment_dist.png`  

---

# Project 2: Model Benchmarking & Business Insights
Goal: Compared BERT vs. XLM-Roberta and extracted actionable trends.

### Key Findings
| Model | Accuracy | Best At | Weakness |
|-------|----------|---------|----------|
| BERT | 82% | Emoji interpretation | Neutral tweets |
| XLM-Roberta | 85% | Code-switched text | Speed |

SQL Insights:  
```sql
-- Peak negativity hours
SELECT strftime('%H', created_at) AS hour, 
       AVG(sentiment) AS avg_mood
FROM tweets 
GROUP BY hour
```
 **Output**: Negative tweets spike at **2-4AM** (suggests staffing needs).

 **Files**:  
- `notebooks/Model_Comparison_BERT_vs_XLM.ipynb`  
- `notebooks/sql_sentiment_analysis.ipynb`  
- `assets/hourly_sentiment.png`  

---

## How to Run
1. **For Project 1**:
   [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/extraordinarytechy/multilingual-sentiment-analyzer/blob/main/notebooks/twitter_sentiment_analysis.ipynb)

2. **For Project 2**:  
   ```bash
   git clone https://github.com/extraordinarytechy/multilingual-sentiment-analyzer.git
   cd multilingual-sentiment-analyzer/notebooks
   jupyter notebook Model_Comparison_BERT_vs_XLM.ipynb
   ```

## Lessons Learned
1. **Model Choice Matters**: XLM-Roberta outperformed BERT but required more RAM
2. **Actual Data is Noisy and inconsistent**: 12% of tweets needed manual relabeling
3. **Business Value**: SQL analysis revealed actionable customer service patterns

---

> "These projects helped me bridge my physics background with NLP – proving quantitative analysis applies equally to particle data and tweet sentiment!"  
> - AJAY KUMAR
```

---
