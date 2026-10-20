# Blood Donation Prediction Using TPOT

## Project Overview

This project uses machine learning to predict whether a blood donor is
likely to donate blood during a future blood drive. The notebook
explores the Blood Transfusion Service Center dataset and compares
automated model selection with classification models.

The dataset comes from a mobile blood donation vehicle operating at
universities in Taiwan.

## Problem Statement

Blood banks and donation teams need to anticipate future donor
participation to help plan blood collection. This project treats the
task as a **binary classification problem**:

-   `1` --- the donor donated blood in March 2007
-   `0` --- the donor did not donate blood in March 2007

## Dataset

The notebook expects a file named `transfusion.data` in the working
directory.

The dataset uses these features:

  -----------------------------------------------------------------------
  Feature                             Description
  ----------------------------------- -----------------------------------
  `Recency (months)`                  Months since the donor's most
                                      recent donation

  `Frequency (times)`                 Total number of donations

  `Monetary (c.c. blood)`             Total volume of blood donated, in
                                      cubic centimeters

  `Time (months)`                     Months since the donor's first
                                      donation

  `target`                            Whether the donor donated blood in
                                      March 2007 (1 = yes, 0 = no)
  -----------------------------------------------------------------------

The notebook renames the original target column to `target`.

## Tools and Libraries

-   Python
-   pandas and NumPy
-   Matplotlib and Seaborn
-   scikit-learn
-   TPOT (Automated Machine Learning)
-   Jupyter Notebook

## Workflow

1.  Load and inspect the dataset.
2.  Review descriptive statistics and target-class proportions.
3.  Visualize feature relationships, target distribution, and
    correlations.
4.  Split the data into training and test sets, using stratification to
    preserve target proportions.
5.  Use TPOT to search for a suitable classification pipeline with
    ROC-AUC as the scoring metric.
6.  Explore feature variance and log normalization for the monetary
    feature.
7.  Train and evaluate AdaBoost and Logistic Regression classifiers.
8.  Review the reported ROC-AUC results.

## Results Reported in the Notebook

The notebook's conclusion reports the following ROC-AUC scores:

  Model / approach                                  ROC-AUC
  ----------------------------------------------- ---------
  TPOT-selected pipeline (reported as AdaBoost)      0.7669
  AdaBoost classifier                                0.7728
  Logistic Regression                                0.7826

According to the notebook, Logistic Regression achieved the highest
ROC-AUC among the reported results. Results can vary if the dataset,
library versions, or notebook code changes.

**Note:** ROC-AUC measures how well a classifier ranks positive cases
above negative cases; it is not the same as accuracy. This project is an
educational prediction exercise, not a validated clinical or blood-bank
decision system.

## How to Run

1.  Download or clone this project.

2.  Place `transfusion.data` in the same folder as the notebook.

3.  Install the required libraries:

    ``` bash
    pip install pandas numpy matplotlib seaborn scikit-learn tpot jupyter
    ```

4.  Start Jupyter Notebook:

    ``` bash
    jupyter notebook
    ```

5.  Open `predict blood donation using tpot.ipynb` and run the cells in
    order.

## Project File

-   `predict blood donation using tpot.ipynb` --- data exploration,
    visualization, model training, and evaluation.

## Limitations

-   Predictions depend on the historical dataset and may not generalize
    to other populations or donation programs.
-   The notebook should be checked end-to-end before reuse; some cells
    may require corrections or consistent preprocessing to run
    successfully.
-   Model predictions should support further investigation and must not
    replace professional planning or eligibility screening.

## Future Improvements

-   Add precision, recall, F1-score, confusion matrix, and
    cross-validation.
-   Tune model hyperparameters and compare additional classifiers.
-   Package preprocessing and model steps into a single reproducible
    pipeline.
-   Validate performance on newer or geographically different donor
    data.
-   Save the trained model and build a simple prediction interface.

## Author

Add your name, GitHub profile, and project links here.
