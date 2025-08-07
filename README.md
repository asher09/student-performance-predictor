# Student Performance Predictor 🎓

## Project Overview

This project is an end-to-end machine learning solution designed to predict student performance based on academic and socio-demographic factors. It features a modular, pipeline-driven architecture for robust data processing, model training, and prediction. The primary goal is to help educators and parents identify at-risk students early and implement timely interventions.

---

## Key Features

- **Modular Code Structure:** Organized into distinct modules for maintainability and reusability.
- **End-to-End ML Pipeline:** Includes data ingestion, transformation, model training, and prediction.
- **Custom Exception Handling & Logging:** Robust error handling and logging for debugging and traceability.
- **Flexible Model Training:** Supports multiple regression algorithms (Linear, Ridge, Lasso, CatBoost, XGBoost, etc.).
- **Automated Evaluation:** Provides metrics like RMSE, MAE, and R² for model performance.
- **Web Interface:** Flask-based web app for user-friendly predictions.
- **Jupyter Notebooks:** For EDA, feature engineering, and model experimentation.
- **Environment Management:** Uses `requirements.txt` for dependency management and supports dev containers.

---

## Project Structure

```
├── data/
│   └── raw_data.csv
├── notebook/
│   ├── EDA.ipynb
│   └── 2. MODEL TRAINING.ipynb
├── src/
│   ├── components/
│   │   ├── data_ingestion.py
│   │   ├── data_transformation.py
│   │   └── model_trainer.py
│   ├── pipeline/
│   │   ├── training_pipeline.py
│   │   └── predict_pipeline.py
│   ├── exception.py
│   ├── logger.py
│   └── utils.py
├── templates/
│   ├── home.html
│   └── index.html
├── app.py
├── requirements.txt
├── setup.py
└── README.md
```

- **data/**: Contains the raw dataset.
- **notebook/**: Jupyter notebooks for EDA and model training.
- **src/**: Core source code.
  - **components/**: Data ingestion, transformation, and model training logic.
  - **pipeline/**: Orchestrates the ML workflow for training and prediction.
  - **exception.py**: Custom exception class for error handling.
  - **logger.py**: Logging setup for the project.
  - **utils.py**: Utility functions (e.g., object serialization).
- **templates/**: HTML templates for the Flask web app.
- **app.py**: Flask application entry point.
- **requirements.txt**: Python dependencies.
- **setup.py**: Project setup for packaging.

---

## Installation

1. **Clone the repository:**
   ```sh
   git clone https://github.com/asher09/student-performance-predictor.git
   cd student-performance-predictor
   ```

2. **Install dependencies:**
   ```sh
   pip install -r requirements.txt
   ```

   > **Note:** The project is designed for use in a dev container (Ubuntu 24.04.2 LTS). All dependencies are listed in `requirements.txt`.  
   > Ensure your `scikit-learn` version matches the one used for model training and inference.

---

## Usage

### 1. **Training the Model**

To train the model from scratch and save the best-performing model:

```sh
python src/pipeline/training_pipeline.py
```

- This runs the full pipeline: data ingestion, transformation, model training, and saves the model/preprocessor objects.

### 2. **Running the Web App**

To start the Flask web application for predictions:

```sh
python app.py
```

- Open your browser and navigate to the provided local address to use the web interface.

### 3. **Making Predictions**

- Use the web form to input student features and receive predicted performance.

---

## Features & Implementation Details

### Data Ingestion & Transformation

- **`src/components/data_ingestion.py`**: Reads raw data and splits into train/test sets.
- **`src/components/data_transformation.py`**: Handles feature engineering, encoding, and scaling using `ColumnTransformer` (OneHotEncoder, StandardScaler).
- **`src/components/model_trainer.py`**: Trains multiple regression models and evaluates them.

### Pipelines

- **`src/pipeline/training_pipeline.py`**: Orchestrates the full training workflow.
- **`src/pipeline/predict_pipeline.py`**: Loads the trained model and preprocessor for inference.

### Utilities

- **`src/utils.py`**: Functions for saving/loading Python objects (using `pickle`/`dill`).
- **`src/exception.py`**: Custom exception class for detailed error reporting.
- **`src/logger.py`**: Configures logging to file for debugging and audit.

### Web Application

- **`app.py`**: Flask app for serving predictions.
- **`templates/home.html`**: Main form for user input.
- **`templates/index.html`**: Welcome page.

### Notebooks

- **`notebook/EDA.ipynb`**: Exploratory Data Analysis.
- **`notebook/2. MODEL TRAINING.ipynb`**: Interactive model training, evaluation, and visualization.

---

## Technologies Used

- **Python 3.12+**
- **Pandas, NumPy**: Data manipulation.
- **Scikit-learn**: ML pipelines, preprocessing, and modeling.
- **CatBoost, XGBoost**: Advanced regression models.
- **Matplotlib, Seaborn**: Data visualization.
- **Flask**: Web application.
- **dill, pickle**: Model serialization.
- **Jupyter Notebook**: EDA and experimentation.

---

## Best Practices

- **Version Pinning:** Ensure `scikit-learn` and other dependencies are pinned in `requirements.txt` to avoid serialization issues.
- **Custom Logging & Exceptions:** All errors are logged and raised with context for easier debugging.
- **Dev Container Ready:** Designed for reproducibility in containerized environments.

---

## Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change.

---

## License

This project is licensed under the MIT License.

---

## Author

- Aman Sharma ([sharmaaman0202@gmail.com](mailto:sharmaaman0202@gmail.com))
