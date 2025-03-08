# Stepik-ML-Contest

## Overview
This project is a machine learning model designed to predict student attrition in a Stepik course. The dataset consists of user interaction and submission data collected from Stepik, an online learning platform. Feature engineering was guided by course mentors, while the training, optimization, and modeling were independently developed.

## Dataset
The dataset consists of two main CSV files:

1. **Events Data (`event_data_train.zip`)**
   - `step_id`: ID of the step the student interacted with.
   - `timestamp`: Time of the event (Unix timestamp format).
   - `action`: Type of interaction (viewed, passed, discovered).
   - `user_id`: Unique identifier for the student.

2. **Submissions Data (`submissions_data_train.zip`)**
   - `step_id`: ID of the step where submission was made.
   - `timestamp`: Time of submission (Unix timestamp format).
   - `submission_status`: Whether the submission was `correct` or `wrong`.
   - `user_id`: Unique identifier for the student.

## Feature Engineering
- **days**: Number of unique days a student was active.
- **steps_tried**: Total number of different steps attempted.
- **correct**: Count of correct submissions.
- **wrong**: Count of wrong submissions.
- **correct_ratio**: Ratio of correct submissions to total submissions.
- **viewed**: Total number of steps viewed.

## Model Training
Two models were trained:
1. **Neural Network (TensorFlow/Keras)**
   - Layers with ReLU activation.
   - Binary classification with sigmoid activation.
   - Optimized using Adam optimizer with `binary_crossentropy` loss.
   - 92.7% accuracy.

2. **Random Forest (Alternative Model)**
   - Hyperparameter tuning using GridSearchCV.
   - 5-fold cross-validation.
   - 92.7% accuracy.

## Running the Notebook
To run the notebook locally:
1. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn tensorflow
   ```
2. Open `Stepik ML Contest.ipynb` in Jupyter Notebook or VS Code.
3. Run all cells to train and evaluate the model.

