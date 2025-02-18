# Playground Series - Sticker Sales Prediction (S5E1)

This project aims to predict the number of stickers sold (`num_sold`) based on various features using a **Ridge Regression** model. The dataset contains information about sticker sales in various countries, stores, and dates. The goal is to build a model that can predict the number of stickers sold on a given day for each store and country.

## **Project Structure**

- `train.csv`: The training dataset containing information on sticker sales, which includes columns like country, store, date, and number of stickers sold (`num_sold`).
- `test.csv`: The test dataset that needs predictions for `num_sold` based on the same features from the training dataset.
- `submission.csv`: The final submission file with predicted values for the `num_sold` column.

## **Technologies Used**
- **Python 3**: The project is implemented using Python 3.
- **Pandas**: For data processing and manipulation.
- **NumPy**: For numerical operations.
- **Scikit-learn**: For machine learning model development and preprocessing.


## **Steps Involved**

### 1. **Data Preprocessing**
   - Load the datasets (`train.csv` and `test.csv`).
   - Check for missing values and handle them. The missing `num_sold` values are filled with the **median**.
   - Convert categorical columns (e.g., `country`, `store`) into numerical values using **Label Encoding**.
   - Extract the **year** from the `date` column, which was originally in `YYYY-MM-DD` format.

### 2. **Data Exploration and Visualization**
   - Check the distribution of countries involved in the sticker sales and visualize the data with a pie chart.
   - Extract the years from the `date` columns for both the training and test datasets.
   - Explore missing values and handle them appropriately.
   - Drop the `id` column as it has high variance and doesn't provide useful information for the model.

### 3. **Model Development**
   - Split the dataset into **independent** (features) and **dependent** (target variable `num_sold`) variables.
   - Scale the features using **StandardScaler** for better model performance (especially important for models with regularization, such as Ridge).
   - Train a **Ridge Regression** model with the training dataset to predict the number of stickers sold.

### 4. **Model Evaluation and Prediction**
   - After training the model, use it to make predictions on the test dataset (`X_test`).
   - Create a submission file that includes the `id` and the predicted `num_sold` values.

### 5. **Submission**
   - The predictions are saved to a `submission.csv` file, ready for submission.

## **Installation**

To get started with this project, you need to install the following Python libraries:

```bash
pip install pandas numpy scikit-learn matplotlib
```
## **Files and Output**
- **train.csv:** Training data(with the num_sold column).
- **test.csv:** Test data (with no num_sold column, only features)
- **submission.csv:** The submission file containing the predicted number of stickers sold (num_sold) for the test data
  
## **Challenges faced**
- **Handling Missing Values:** The num_sold column contained missing values which were handled by filling them with median.
- **Feature Engineering:** The date column was converted to year to simplify the model and potentially improve performance.
- **Label Encoding:** The categorical columns (country, store) were transformed using Label Encoding to convert them to numerical format.
  
## **Future Improvement**
- **Hypterparameter Tuning:** Further optimization of the Ridge Regression model using cross-validation and grid search.
- **Additional Feature Engineering:** Explore creating more feature based on the year, such as sales trends over time or country-specific patterns.
- **Model Selection:** Experiment with other regression model like Lasso, Linear Regression, or Gradient Boosting.
