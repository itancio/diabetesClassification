# Diabetes Binary Classification




## Objective:
The goal is to classify diabetes diagnosis based on various patient data. The dataset includes demographics, lifestyle, medical history, clinical measurements, medications, symptoms, and more. The aim is to identify factors strongly correlated with diabetes and use these features to train a classification model.

## Process Overview:

### Import Libraries and Datasets:

Libraries such as Pandas, NumPy, TensorFlow, Scikit-learn, and Seaborn were used for data handling, visualization, and model building.
The dataset was read from a CSV file containing data for 1,879 patients.

This dataset contains comprehensive health data for 1,879 patients, uniquely identified with IDs ranging from 6000 to 7878. The data includes demographic details, lifestyle factors, medical history, clinical measurements, medication usage, symptoms, quality of life scores, environmental exposures, and health behaviors. Each patient is associated with a confidential doctor in charge, ensuring privacy and confidentiality.

[Data source: Diabetes Health Dataset Analysis](https://www.kaggle.com/datasets/rabieelkharoua/diabetes-health-dataset-analysis/data)

### Data Preprocessing:

* Inspected and cleaned the dataset, dropping unnecessary columns like PatientID and DoctorInCharge.
* Visualized the data to understand distributions and correlations.

  * Using pairwise plotting, we are able to visualize the a pairwise correlations of each feature from our dataset.
<img src="assets/diabetes2.png" width="80%"/>

  * A different way of seeing this relationship is this 3d plot that shows the relationships of three features. The most notable features include _Fasting Blood Sugar_, _Hb1Ac_ and their diagnoses.
<img src="assets/diabetes3.png" width="80%"/>

* Selected relevant features such as Age, BMI, SystolicBP, DiastolicBP, FastingBloodSugar, HbA1c, and SerumCreatinine.
* Scaled the data using MinMaxScaler to normalize feature values.

Before: The data show the info from the original dataset.
<img src="assets/diabetes4.png" width="80%"/>

After: Here shows the scaled versions of each features.
<img src="assets/diabetes5.png" width="80%"/>

### Model Training:
* Split the data into training (60%), cross-validation (20%), and test sets (20%).
* Trained multiple models, including Logistic Regression, Decision Trees, Random Forest, Gradient Boosting, AdaBoost, Extra Trees, XGBoost, and LightGBM.
* Evaluated models using accuracy metrics on the cross-validation set.
* Used polynomial features to improve model performance but found the optimal degree for minimal cross-validation mean square error.

### Model Selection and Evaluation:
The RandomForestClassifier was chosen as the optimal model based on cross-validation accuracy.
Adjusted the decision boundary to optimize performance, achieving an accuracy of 87.77%.


## Choices Made and Their Justification:

### Feature Selection:
Focused on clinically relevant features with strong correlation to diabetes, ensuring a meaningful input for models.

Here, we are showing the performance of different degrees of polynomials added in our linear model. (Blue line) We can see the the cross-validation 2nd degree polynomial can help data fit our model better.
<img src="assets/diabetes6.png" width="80%"/>

### Data Scaling:
Used MinMaxScaler to ensure all features were on a similar scale, which is crucial for the performance of many machine learning models.

### Model Selection:
Evaluated multiple models to find the best performer, ensuring robustness in the classification task. RandomForest was chosen for its high accuracy and general performance in classification problems.

### Cross-Validation:
Used to tune hyperparameters and select the best model, providing a reliable estimate of model performance.

## Improvements and Next Steps:

* **Feature Engineering**: Explore more sophisticated feature engineering techniques or interactions between features.
Consider domain-specific knowledge to create new features.
* Hyperparameter Tuning**: Perform a more extensive hyperparameter tuning for the selected models using grid search or Bayesian optimization.
* **Model Ensemble**: Combine multiple models to create an ensemble that could potentially improve performance over individual models.
* **Regularization**: Implement regularization techniques to prevent overfitting, especially for complex models like neural networks.
* **Further Validation**: Use additional validation techniques such as bootstrapping or k-fold cross-validation to ensure the model's robustness.

By following these steps, the model can be further refined and its performance potentially improved, ensuring better accuracy and reliability in diagnosing diabetes based on patient data.
