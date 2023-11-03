# Black-Friday-Sales-Prediction-Using-Spark
 Build a Regression model trained on historic black friday sales data to predict future black friday sales.
 ### Step to Black-Friday-Sales-Prediction-Using-spark
 1. Load the dataset
 
2. `DATA EXPLORATION`

Now, that we have read the data, the first step is to explore the data. We will try to find out the following things from the data.

---
**`1. Variable Identification`**

- Data Type of the columns

**`2. Univariate Analysis`**
- 1. Average Purchase amount?
- 2. Counting and Removing null values
- 3. How many distinct values per column?
- 4. Count category values within each of the following column:
     - Gender
     - Age
     - City_Category
     - Stay_In_Current_City_Years
     - Marital_Status

**`3. Bivariate Analysis`**

- Calculate average Purchase for each of the following columns:
     - Gender
     - Age
     - City_Category
     - Stay_In_Current_City_Years
     - Marital_Status

3. Label Encoding
4. Split the dataset using the train-test split
5. Vector Assembler
6. Cross Validation
7. Grid Search


8. `Machine Learning Pipelines in Spark`

----


 *   `Transformer` 
 > - It transforms the input data (X) in some ways.
 > - Implements a method `transform()`, which converts one DataFrame into another, generally by appending one or more columns.
 > - It includes `feature transformers` and `learned models`.
 > > - `Feature transformer` should take a DataFrame, read a column (e.g., text), map it into a new column (e.g., feature vectors), and output a new DataFrame with the mapped column appended.
 > > -  `Learning model` should take a DataFrame, read the column containing feature vectors, predict the label for each feature vector, and output a new DataFrame with predicted labels appended as a column.
 *   `Estimator` 
 > - It predicts a new value (or values) (y) by using the input data (X).
 > - It implements a method `fit()`, which accepts a DataFrame and produces a `Model`, which is a `Transformer`.
 > > - For example, a learning algorithm such as `LogisticRegression` is an `Estimator`, and calling `fit()` trains a `LogisticRegressionModel`, which is a `Model` and hence a `Transformer`.
 * `Pipeline`
 > - It represents a sequence of steps to apply in an ML workflow. Example:
 > > - Stage 1 : Split text into words.
 > > - Stage 2 : Convert words into numeric data.
 > > - Stage 3 : Apply machine learning model on the numeric data.
 > - These steps are represented as `Transformers` or as `Estimators`.
 > - A `Pipeline` is comprised of `Stages`.
 > > - These stages are run in order.
 > > - The input DataFrame is transformed as it passes through each stage.
 > > - Each stage is either a `Transformer` or an `Estimator`.