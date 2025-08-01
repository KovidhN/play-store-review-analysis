# play-store-review-analysis

### Objective
To automatically categorize and analyze negative user reviews from Google Play Store apps using Natural Language Processing (NLP) and unsupervised clustering techniques. This enables identification of major complaint themes, aiding developers in prioritizing app improvements.

### Dataset
- Source: Kaggle dataset "Google Play Store Apps" by lava18, specifically the user reviews file (`googleplaystore_user_reviews.csv`).
- Size: Filtered for reviews labeled with negative sentiment.
- Key columns used: `Translated_Review`, `Sentiment`, `App`.

### Methodology

1. **Data Filtering and Preprocessing**
   - Extracted only negative reviews.
   - Performed text cleaning: lowercasing, removal of non-alphabetic characters, and stopword removal.

2. **Feature Extraction**
   - Applied TF-IDF vectorization to convert cleaned reviews into numerical form, limiting features to the top 2,500 informative terms.

3. **Clustering**
   - Used K-Means clustering algorithm with 5 clusters to group similar reviews based on complaint themes.
   - Analyzed cluster centers to extract the top keywords per cluster for interpretability.

4. **Cluster Interpretation**
   - Each cluster represents a distinct category of user complaints.
   - Representative sample reviews were manually inspected per cluster for validation.

5. **Visualization**
   - PCA was used to project high-dimensional review vectors into 2D for cluster visualization.
   - Bar charts displayed the distribution of review counts per cluster.
   - Word clouds illustrated the dominant keywords within each cluster.
   - Heatmap showed the distribution of clusters across different apps.

### Key Findings
- Reviews grouped into clear themes, such as login failures, app crashes, excessive ads, performance issues, and data loss.
- Distribution of negative reviews is uneven among clusters, with some complaint categories more prevalent.
- Certain apps showed concentrated issues in specific clusters, visible in the heatmap, aiding focused improvement efforts.

### Limitations
- No timestamp data to analyze trends over time.
- K-Means requires predefined number of clusters; interpretation relies on manual inspection of keywords and samples.
- Data sparsity in heatmap suggests many apps have few negative reviews spread thinly across categories.

### Recommendations
- Use cluster labels and top keywords to generate automated alerts or reporting dashboards for product teams.
- Consider advanced embeddings (e.g., BERT) and clustering (e.g., DBSCAN) for deeper semantic grouping.
- Incorporate temporal analysis if timestamps become available to monitor issue trends.
- Focus quality assurance on apps and clusters with highest negative feedback volumes.

[1] https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/82207542/5a779f02-8d96-49e6-8365-75562c3fc1c9/google_play_store_apps_analysis.py
