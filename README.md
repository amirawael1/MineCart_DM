# MineCart_DM

Data-mining project that builds product bundles and cross-sell recommendations from Amazon product metadata.

## Overview
This project analyzes Amazon product data and delivers two recommendation tools:
- **Bundle Generator**: Suggests 2–3 complementary items within a price limit.
- **Cross-Selling Engine**: “Customers also bought” suggestions using multiple signals.

## Workflow

### 1. Preparation (The “Ingredients”)
- **Loading Data**: Reads Amazon products (prices, names, ratings) and categories.
- **Cleaning**: Fills missing prices, removes unnamed products, and coerces numeric fields.
- **Feature Engineering**: Creates derived metrics like *Popularity Score* and *Value Score*.

### 2. Understanding the Data (The “Taste Test”)
- **Exploratory Analysis**: Charts for category popularity, price distribution, and best-sellers.
- **Word Cloud**: Highlights frequent terms in product titles.

### 3. Grouping Similar Products (Clustering)
- **Text Analysis**: Converts titles into TF-IDF features.
- **Clustering**: K-Means groups products into similarity-based clusters.

### 4. Teaching the Computer “Meanings” (Word2Vec)
- Trains Word2Vec to capture semantic similarity between product terms.
- Represents titles as vectors for similarity comparisons.

### 5. Learning Buying Patterns (Association Rules)
- **Simulation**: Generates transactions based on category and price affinities.
- **Apriori Algorithm**: Extracts rules like “If X, then Y.”

### 6. The Recommendation Engines (The “Result”)
**Bundle Generator**
- Uses Word2Vec similarity.
- Enforces category diversity.
- Respects a price cap.

**Cross-Selling Engine**
- Combines content similarity, category affinity, and popularity.

### 7. Grading the System (Evaluation)
- Scores random bundles by category diversity and semantic coherence.

## Repository Structure
- [data/](data/)
	- amazon_categories.csv
	- amazon_products_cleaned.csv
- [notebooks/](notebooks/)
	- bundle_recommendation_solution.ipynb
	- reference.ipynb

## Notes
- This project is notebook-driven.
- Source data and engineered features are in [data/](data/).