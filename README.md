# Driving Behavior Analysis & TTC Prediction using Deep Learning

This project analyzes naturalistic highway traffic data to classify driving behavior and predict Time-to-Collision (TTC) using supervised deep learning techniques.

The workflow follows a structured pipeline including data preprocessing, feature engineering, exploratory analysis, modeling, evaluation, and visualization.

## Project Structure
├── Prjt1.py # Data preprocessing, feature engineering & evaluation metrics
├── Prjt2.py # Deep learning modeling (classification & regression)
├── README.md # Project documentation
├── feature_matrix.csv
└── data/ # Raw highD CSV files



## Dataset

**Dataset:** highD Dataset  
**Source:** Drone-based highway traffic recordings  
**Data type:** Vehicle trajectories and driving dynamics  

**Key parameters used:**

- DHW (Distance Headway)  
- TTC (Time-to-Collision)  
- yVelocity (Lateral velocity)  

## Project Workflow

### 1. Data Preparation (Prjt1.py)

- Cleaning raw CSV files  
- Handling missing values  
- Interpolation of time-series data  
- Normalization of units  
- Vehicle-level aggregation  
- Validation of data consistency  

### 2. Feature Engineering & Exploratory Analysis (Prjt1.py)

- Statistical features: mean, standard deviation  
- Dynamic features: gradients, temporal variations  

**Behavioral labeling:**

- Defensive  
- Normal  
- Aggressive  

**Visualizations:**

- Heatmaps  
- Correlation matrices  
- Distribution plots  

### 3. Feature Matrix Creation (Prjt1.py)

- Aggregated vehicle-level features  
- Final dataset for model training  
- Exported as feature_matrix.csv  

### 4. Deep Learning Modeling (Prjt2.py)

**Classification**

- Task: Driving behavior classification  
- Classes: Defensive, Normal, Aggressive  
- Loss function: Categorical Cross-Entropy  

**Regression**

- Task: TTC prediction  
- Loss function: Mean Squared Error (MSE)  

### 5. Model Training (Prjt2.py)

- Train-test split: 80/20  
- Multi-epoch training  
- Monitoring: training accuracy, validation accuracy, training loss, validation loss  

### 6. Model Evaluation (Prjt1.py)

**Classification metrics:**

- Accuracy  
- Precision  
- Recall  
- F1-score (manual multi-class implementation)  

**Regression metrics:**

- Mean Squared Error (MSE)  
- Root Mean Squared Error (RMSE)  
- Mean Relative Error (MRE)  
- Standard deviation of errors  
- Correlation between predicted and true TTC  

### 7. Visualization

- Regression scatter plots (predicted vs actual TTC)  
- Learning curves  
- Heatmaps for risk analysis  
- Confusion matrix interpretation  

**Example Visualization:**
python
plt.scatter(distance, lateral_velocity, c=minTTC, cmap=cm.RdYlGn) ```

Crash-critical scenarios are highlighted for safety analysis.

Key Findings

Low TTC combined with small headway indicates aggressive driving

Deep learning models outperform rule-based baselines

TTC prediction correlates strongly with real collision risk

Balanced Precision–Recall performance is crucial for safety-critical detection

Requirements

Python >= 3.8

numpy

pandas

matplotlib

seaborn

tensorflow

keras

Note: scikit-learn is optional and not required for core functionality.

How to Run
# Step 1: Feature engineering & evaluation
python Prjt1.py

# Step 2: Model training
python Prjt2.py

Future Work

Integration of additional traffic parameters

Cross-dataset validation

Scenario-based risk modeling

Real-time driving behavior detection

References

highD Dataset (Krajewski et al.)

Deep Learning (Goodfellow et al.)

Traffic Flow Dynamics (Treiber & Kesting)

Author

Khan,Mohammad Ahmad
Dhola, Chintankumar Jayantibhai 
Chauhan, Kartik 
Informatik Project – Driving Behavior Analysis & AI Modeling







```python
plt.scatter(distance, lateral_velocity, c=minTTC, cmap=cm.RdYlGn)
