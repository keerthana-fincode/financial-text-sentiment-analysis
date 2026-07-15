# Financial Sentiment & Linguistic Analysis

## Project Overview
This project builds an NLP pipeline designed to quantify the tone of corporate financial disclosures. By deploying two distinct lexical scoring methods, the analysis demonstrates how general-purpose sentiment dictionaries fail to account for the unique semantic requirements of financial documents, leading to frequent misclassifications of regulatory "boilerplate" language as negative sentiment.

## Technical Methodology
1. **Text Processing:** Utilizes `NLTK` and `re` to clean and normalize transcript text, including tokenization, stopword removal, and lemmatization.
2. **Lexical Scoring Engine:**
   - **VADER:** A rule-based, valence-aware model optimized for general social media sentiment.
   - **Loughran–McDonald (LM):** A domain-specific lexicon curated specifically for corporate financial filings, stripping away common words that are contextually neutral in finance.
3. **Comparative Analysis:** A side-by-side performance evaluation showing how the same document produces divergent "positive/negative" scores depending on the underlying lexicon choice.

## Performance & Lexicon Comparison

| Metric | General-Purpose (VADER) | Domain-Specific (LM) |
| :--- | :--- | :--- |
| **Sentiment Logic** | Social Valence | Financial Context |
| **Boilerplate Handling** | High misclassification rate | Low (Context-Aware) |
| **Precision** | Low in corporate contexts | High in financial contexts |

## Strategic Analysis
### 1. The "Boilerplate" Bias
General-purpose models like VADER frequently flag phrases such as *"statements involve risks and uncertainties"* as negative due to the presence of the word "risks." The LM lexicon identifies these as neutral disclosures required by the SEC. This project quantifies this discrepancy, revealing why domain-specific lexicons are essential for accurate financial signal extraction.

### 2. Analytical Insights
By mapping word frequency distributions and sentiment trajectories across an earnings transcript, this model provides a clearer understanding of managerial tone, separating genuine operational concerns from mandatory legal disclosures.

## Technical Environment
* **Language:** Python
* **NLP Processing:** `NLTK`, `RegEx`
* **Lexical Scoring:** `VADER`, `Loughran-McDonald`
* **Visualization:** `matplotlib` & `wordcloud`
