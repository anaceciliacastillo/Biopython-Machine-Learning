
ana6.ipynb - Feature Setup & Initial Random Forest Training
  This notebook handles the first part of the project. Here’s a breakdown of what it does:
  
  1. Data Sampling
    - The full dataset is shuffled and a sample is taken to ensure randomness and reduce potential ordering bias in training/testing.
  
  2. Feature Filtering
     -Originally, the dataset contains a wide range of sequence-derived features. This notebook manually filters features that were found to be less helpful or too noisy for classification. Some of this is based on correlation heatmaps, domain knowledge, or feature redundancy.
  
  4. Redefining Inputs
    - The notebook redefines X1 to include only the cleaned set of important features. The target labels y remain unchanged.
  
  5. Train-Test Split
    - An 80-20 split is applied to divide the dataset into training and testing subsets for the Random Forest classifier.
  
  6. Random Forest Classifier (Initial Run)
    - The model is trained on the cleaned features. The initial performance is checked and metrics like accuracy are computed. Early signs of strong classification are seen here.

ana7.ipynb - Final Model, Evaluation, Visualization
This notebook builds off of the setup in ana6.ipynb and carries out the full end-to-end classification and analysis process.
  
  1. Library Imports & Data Prep
    - The required libraries (Pandas, NumPy, Scikit-learn, Seaborn, Matplotlib) are imported. Data is standardized and made ready for use.
  
  2. Final Random Forest Training
  - The Random Forest model is trained using the filtered features from ana6.ipynb. Important hyperparameters (like tree depth and sample size) are tuned for performance and generalization.
  
  3. Performance Evaluation
    - Accuracy: 100% train and test accuracy is achieved.
    - Precision & Recall: All values are 1.0, indicating perfect prediction across classes.
    - Confusion Matrix: Shows zero misclassifications, confirming the model’s effectiveness.
  
  4. Feature Importance
    - A feature importance chart is generated to highlight which descriptors played the biggest roles in classification. Solvent accessibility, hydrophobicity, and secondary structure transitions stand out.
  
  5. Visualization
    - The model’s classification ability is visualized using:
      - PCA (Principal Component Analysis): Reduces feature dimensions to visualize separation between classes.
      - t-SNE (t-distributed Stochastic Neighbor Embedding): Another dimensionality reduction technique that shows tight clustering for each proteome class.

How to Run
  1. Open both notebooks using Jupyter Notebook, JupyterLab, or any Python environment that supports .ipynb files.

  2. Make sure all necessary packages are installed:
    pip install pandas numpy scikit-learn matplotlib seaborn

  3. Run ana6.ipynb first to clean and prepare the feature space.

  4. Then run ana7.ipynb to perform final training, testing, visualization, and export of results.

Output:
  - Confusion Matrix and Classification Reports are printed to console.
  - FeatureImportance.csv is exported with the Gini Importance scores.
  - Plots show PCA, t-SNE, and feature rankings visually.
