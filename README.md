# Reddit Fake Post Detection

## Problem Formulation:

### Input:
The dataset comprises titles of Reddit posts, and the goal is to predict whether a post is fake news or not based on its title.

### Output:
The model aims to provide the probability of a title being classified as fake news.

### Data Preprocessing:
A cleaning function, `clean_text`, is defined to perform several steps:
1. Remove HTML tags.
2. Retain only ASCII + European characters and whitespace, excluding digits.
3. Remove single-letter characters.
4. Convert all whitespaces to single whitespace.
5. For non-embedding purposes:
    - Convert to lowercase.
    - Remove stopwords, punctuation, and stem words.

## Model Tuning and Documentation:

### Trial 0: Logistic Regression with TfidfVectorizer (Word)
- **Observations:** Initial attempt using Logistic Regression with TfidfVectorizer at the word level.
- **Code:** The pipeline includes TfidfVectorizer and Logistic Regression.
- **Results:** Achieved a best score of 82.30% with optimal hyperparameters.

### Trial 1: XGBoost with TfidfVectorizer (Char)
- **Observations:** Experimenting with XGBoost and character-level TfidfVectorizer.
- **Code:** Utilized TfidfVectorizer at the character level and XGBoostClassifier.
- **Results:** Achieved a best score of 81.72% with specific hyperparameter configurations.

### Trial 2: RandomForest with TfidfVectorizer (Word)
- **Observations:** Trying RandomForest with TfidfVectorizer at the word level.
- **Code:** Employed TfidfVectorizer at the word level and RandomForestClassifier.
- **Results:** Achieved a less satisfactory score of 52.59%. Potential overfitting indicated.

### Trial 3: Logistic Regression with TfidfVectorizer (Word) - GridSearchCV
- **Observations:** Introduced GridSearchCV for logistic regression with TfidfVectorizer.
- **Code:** Utilized TfidfVectorizer at the word level, implemented GridSearchCV.
- **Results:** Achieved a significant improvement with a train score of 91.44%.


### Conclusion:

- Explored various models and preprocessing techniques.
- Logistic Regression with TfidfVectorizer (Word) demonstrated consistent and robust performance.
- The final model achieved a train score of 91.44% and can effectively classify fake news based on Reddit post titles.
