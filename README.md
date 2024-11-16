### Dataset
The dataset used in this project is sourced from the [FakeNewsNet repository](https://github.com/KaiDMML/FakeNewsNet).


### Step 1: Data Collection and Loading
1. **Load the Data**:
   - Load each CSV file (`gossipcop_fake.csv`, `gossipcop_real.csv`, `politifact_fake.csv`, `politifact_real.csv`) and inspect them for relevant columns (e.g., `title`, `content`, `engagement metrics` if present).
2. **Combine Datasets**:
   - Merge the four datasets into one DataFrame and create a `label` column for `real` or `fake` news and a `source` column for the source (GossipCop or Politifact).

### Step 2: Text Preprocessing
1. **Text Cleaning**:
   - Clean the `title` or `content` columns by removing HTML tags, special characters, and extra whitespace.
   - Convert text to lowercase to normalize it.
2. **Tokenization and Stop Word Removal**:
   - Tokenize text and remove stop words using libraries like NLTK or spaCy.

### Step 3: Named Entity Recognition (NER)
1. **NER Extraction**:
   - Use spaCy or a Hugging Face model to extract named entities from the `content` or `title` of each article, focusing on `ORG`, `GPE`, and `PERSON`.
2. **Entity Count Features**:
   - Calculate the frequency of each entity type (e.g., `count_ORG`, `count_GPE`, `count_PERSON`) and add these as new columns.

### Step 4: Feature Engineering
1. **Textual Features**:
   - Calculate the **article length** (total word count) as a feature.
2. **Sentiment Analysis**:
   - Use TextBlob or VADER to get sentiment scores for each article.
3. **Engagement Metrics**:
   - If engagement data (e.g., likes, shares) is available in the dataset, use these as features to help model popularity.
4. **Additional Features**:
   - Derive features like entity density (entity count per article length) or sentiment-entity interaction metrics.

### Step 5: Predictive Modeling
1. **Data Splitting**:
   - Split the data into training and test sets.
2. **Model Selection**:
   - Try models like Linear Regression or Random Forest for popularity prediction and evaluate using metrics like MAE, accuracy, or F1-score.
3. **Evaluation**:
   - Fine-tune using cross-validation and hyperparameter tuning to optimize results.

### Step 6: Visualization
1. **Entity Frequency**:
   - Bar charts to show the frequency of each entity type (ORG, GPE, PERSON) across articles.
2. **Popularity Correlation**:
   - Scatter plots showing relationships between entity counts and engagement metrics.
3. **Heatmap**:
   - Heatmap to illustrate relationships between entity counts and engagement metrics or popularity scores.

### Step 7: Documentation
1. **Notebook**:
   - Include code, analysis, and comments for each step.
2. **Report**:
   - Summarize the methodology, findings, visualizations, and insights, particularly on the impact of named entities and their effect on article popularity. 

