# Data Analysis and Machine Learning with PySpark

## Overview
This project involves using PySpark for data analysis and machine learning tasks. The notebook is structured into several sections, each focusing on a specific aspect of the workflow, including data preprocessing, handling missing values, evaluating similarity, and implementing supervised learning models. This project utilizes data integration, SQL querying, visualization, and research question exploration.

## Project Structure
The notebook is organized as follows:

1. **Read Data into PySpark DataFrame**: 
   - The dataset is loaded into PySpark DataFrames to enable distributed data processing.
   - Initial exploration includes schema inspection and basic statistics to understand data distributions and potential quality issues.

2. **Question 1: Data Processing**:
   - **Table A (`people_current_companies`)**:
     - Identifies the top 10 users with the highest total experience by counting positions listed in their experience columns.
     - Computes the distinct count of companies users have worked at and includes fields like `user_id`, `current_company_name`, and `current_position`.
     - Implements sorting logic using PySpark transformations and actions.
   - **Table B (`people_history_companies`)**:
     - Identifies the top 10 most educated users by accumulating years spent in education, calculated from start and end dates.
     - Includes additional metrics such as months spent in positions (`company_months`) and relative indices of positions (`company_index`).
     - Handles edge cases for missing data by filtering out incomplete rows.

3. **Question 2: Missingness Mechanisms**:
   - Explores patterns of missing data across key columns like `experience` and `education`.
   - Implements strategies to handle missing data, including imputation and filtering.
   - Discusses potential causes of missingness (e.g., MCAR, MAR, MNAR) and their impact on analysis.

4. **Question 3: Evaluating Similarity**:
   - Uses cosine similarity and other distance metrics to evaluate relationships between user profiles based on their attributes (e.g., skills, positions, and descriptions).
   - Constructs feature vectors using Word2Vec and TF-IDF techniques in PySpark.
   - Analyzes clusters of users or companies with similar attributes using visualization tools.

5. **Question 4: Supervised Learning**:
   - Trains a Logistic Regression model to classify users into predefined categories based on their features.
   - Implements a preprocessing pipeline to assemble features, handle categorical variables, and scale numerical data.
   - Evaluates the model using metrics like weighted precision, recall, and F1 score, achieving a best validation F1 score of 0.503.

6. **Analysis Report**:
   - Summarizes the key implementation steps, including:
     - **Feature Engineering**: Derived features such as `description_vector`, `popularity`, and `followers_log`.
     - **Pipeline Construction**: Automated steps for tokenization, embedding generation, and feature assembly.
     - **Error Analysis**: Examined misclassifications using confusion matrices and feature importance plots.
     - **Class-wise Performance Metrics**: Compared model performance across different user categories.

## Requirements
To run the notebook, ensure the following dependencies are installed:

- Python (>=3.7)
- PySpark
- pandas
- NumPy
- scikit-learn

## How to Run
1. Clone the repository:
   ```bash
   git clone <repository_url>
   ```

2. Navigate to the project directory:
   ```bash
   cd <project_directory>
   ```

3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Open the Jupyter Notebook:
   ```bash
   jupyter notebook HW2_322620873_207176462_314779166.ipynb
   ```

5. Run each cell sequentially to reproduce the results.

## Deliverables
The following deliverables align with the assignment requirements:

1. **Table Outputs**:
   - `people_current_companies.csv`: Details about the top 10 most experienced users.
   - `people_history_companies.csv`: Details about the top 10 most educated users.

2. **SQL Queries**:
   - Query A: Top 10 users by recommendations, including experience details.
   - Query B: Analysis of distinct URLs in the `people_also_viewed` column.

3. **Visualizations**:
   - Topics in posts and about sections, using NLP techniques like spaCy and NLTK.
   - Exploratory questions answered using data visualizations, such as trends in user attributes and company profiles.

4. **Research Questions**:
   - Three research questions defined and justified, with a focus on career success and professional network dynamics.

## Results
- Detailed insights and metrics for data preprocessing, missingness mechanisms, similarity evaluation, and supervised learning are included in the notebook.
- Visualizations and analytical summaries are saved in the deliverables.
