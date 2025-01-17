
# easyml

`easyml` is a Python package designed to simplify the process of creating machine learning pipelines. It allows you to easily handle data preprocessing, model selection, and model evaluation with a few simple function calls.

## Features

- Customizable missing value handling for numerical and categorical features.
- Support for multiple machine learning models including:
  - Random Forest
  - Logistic Regression
  - Decision Tree
  - Support Vector Machine (SVM)
  - K-Nearest Neighbors (KNN)
  - Gradient Boosting Classifier (XGBoost)
  - Naive Bayes
- Easy to integrate into your machine learning workflows.
- Built-in model evaluation with accuracy score and classification report.

## Installation

You can install `easyml` directly from PyPI (if published) or locally from the source.

### From PyPI (Coming Soon)

```bash
pip install easyml
```

### From Source

To install `easyml` from the source, follow these steps:

1. Clone the repository:

    ```bash
    git clone https://github.com/gaharivatsa/easyml.git
    ```

2. Navigate to the project directory:

    ```bash
    cd easyml
    ```

3. Install the package:

    ```bash
    pip install .
    ```

## Usage

Here's a step-by-step guide on how to use `easyml` in your projects.

### 1. Import the Package

Start by importing the `create_ml_pipeline` function from the `easyml` package.

```python
from easyml import create_ml_pipeline
```

### 2. Prepare Your Data

Ensure your dataset is in a CSV format and includes a target column that you want to predict.

```python
# Example: Load your dataset
dataset = 'path_to_your_dataset.csv'
target = 'target_column_name'
```

### 3. Create and Run the Pipeline

Use the `create_ml_pipeline` function to build and run the pipeline. You can specify the missing value handling strategies, the model, and any model-specific parameters.

```python
pipeline = create_ml_pipeline(
    numerical_na_method='mean',            # Strategy for imputing missing values in numerical columns
    categorical_na_method='most_frequent', # Strategy for imputing missing values in categorical columns
    model_name='knn',                      # Choose the model (e.g., 'knn', 'random_forest', etc.)
    model_params={'n_neighbors': 5},       # Model-specific parameters
    dataset=dataset,                       # Path to your dataset
    target=target,                         # Target column name
    splitting_ratio=0.25                   # Ratio for splitting the dataset into training and testing sets
)
```

### 4. View Results

The function will output the accuracy and classification report after training the model.

### 5. Save the Pipeline

The trained pipeline is automatically saved as a `.pkl` file for future use.

```python
# Example: Load and use the saved pipeline
import joblib

loaded_pipeline = joblib.load('knn_pipeline.pkl')
```

### 6. Customize Further

Feel free to customize the pipeline further by adjusting the model parameters, trying different models, or even extending the functionality by modifying the source code.

## Example Projects

You can find example projects and more detailed tutorials in the `examples/` directory of the repository.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request or open an Issue on GitHub.

## Author

Harivatsa G A - [GitHub](https://github.com/gaharivatsa)
