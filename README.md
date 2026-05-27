# Twitter Trending Topic Detection (Big Data & PySpark)

A scalable, distributed computing project that leverages Apache Spark and Natural Language Processing (NLP) to detect emerging trending topics in real-time from Twitter data streams.

## 🎯 Objective
The goal of this project was to build a Big Data pipeline capable of processing large volumes of unstructured social media text. Instead of simply counting frequent words, the system is designed to identify *emerging* trends—topics that are suddenly gaining popularity—while penalizing historically common words, offering a true "Trending Topics" algorithm.

## 🚀 What is Achieved
- **Distributed NLP Pipeline:** Implemented a robust preprocessing pipeline using `Spark NLP` to handle language detection, tokenization, normalization, stop-word removal, and Named Entity Recognition (NER).
- **Time-Window Aggregation:** Grouped tweets into sliding time windows to track the chronological evolution of word usage.
- **Custom B-Ngram Algorithm:** Generated bi-grams and applied a custom `DF-IDF` (Document Frequency - Inverse Document Frequency over Time) formula. This mathematically penalizes words that are consistently popular and boosts emerging terms.
- **Entity Boosting & Clustering:** Boosted scores for bigrams containing Named Entities (like people or places). Finally, applied Hierarchical Clustering using `scipy` to group related n-grams into cohesive, understandable topics.
- **Scalability:** The entire architecture is built on PySpark DataFrames, ensuring it can scale horizontally across a cluster to handle massive data throughput.

## 🛠️ Tools & Technologies
- **Framework:** Apache Spark (`PySpark`)
- **NLP Library:** Spark NLP (`com.johnsnowlabs.nlp`)
- **Clustering:** `scipy` (Hierarchical Clustering, Linkage, Distance Matrices)
- **Environment:** Databricks / Jupyter Notebooks
- **Techniques:** TF-IDF Variations, Named Entity Recognition (GloVe 100d Embeddings), Sliding Window Aggregation.

## 📖 Usage Guide

### Prerequisites
To run this notebook locally, you need a Spark environment configured with the Spark NLP packages.

```bash
# Install PySpark and Spark NLP
pip install pyspark spark-nlp numpy pandas scipy
```
*Note: When launching your Spark session, ensure you include the Spark NLP jar package (e.g., `spark.jars.packages = com.johnsnowlabs.nlp:spark-nlp_2.12:5.5.2`).*

### Exploring the Project
1. Clone this repository.
2. Read the `Project_Report.pdf` for a deep theoretical explanation of the mathematical formulas (DF-IDFt) and the clustering architecture used.
3. Open the `Trending_Topics_Twitter_PySpark.ipynb` notebook to view the code, the pipeline execution, and the final clustered trending topics output.

---
*Note: This project demonstrates the ability to handle Big Data architectures and deploy machine learning NLP pipelines in distributed environments.*
