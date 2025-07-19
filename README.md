# MAGIC Gamma Telescope Classification Project

-----

## 🚀 Project Overview

This project focuses on classifying types of particles (gamma rays vs. hadrons) detected by the MAGIC (Major Atmospheric Gamma-ray Imaging Cherenkov) Telescope. Utilizing a dataset containing various image parameters, the goal is to build a robust classification model to distinguish between gamma (signal) and hadron (background) events. This is crucial for astronomical observations, enabling better identification of cosmic gamma-ray sources.

-----

## 📊 Dataset

The dataset used in this project is sourced from the [UCI Machine Learning Repository: MAGIC Gamma Telescope Dataset](https://archive.ics.uci.edu/dataset/159/magic+gamma+telescope). It comprises 10 continuous features describing the atmospheric Cherenkov images recorded by the telescope, along with a class label indicating whether the event corresponds to a gamma ray (`g`) or a hadron (`h`).

**Features:**

  * **fLength**: continuous (major axis of ellipse [mm])
  * **fWidth**: continuous (minor axis of ellipse [mm])
  * **fSize**: continuous (10-log of sum of content of all pixels [in \#phot])
  * **fConc**: continuous (ratio of sum of two highest pixels over fSize [ratio])
  * **fConc1**: continuous (ratio of highest pixel over fSize [ratio])
  * **fAsym**: continuous (distance from highest pixel to center, projected onto major axis [mm])
  * **fM3Long**: continuous (3rd root of third moment along major axis [mm])
  * **fM3Trans**: continuous (3rd root of third moment along minor axis [mm])
  * **fAlpha**: continuous (angle of major axis with vector to origin [deg])
  * **fDist**: continuous (distance from origin to center of ellipse [mm])

**Class Labels:**

  * `g`: gamma (signal) - 12332 instances
  * `h`: hadron (background) - 6688 instances

-----

## 🛠️ Data Preprocessing & Exploratory Data Analysis (EDA)

The initial preprocessing involved converting the categorical 'class' label into a numerical format, where 'g' (gamma) was mapped to **1** and 'h' (hadron) was mapped to **0**.

Exploratory Data Analysis was performed by visualizing the distribution of each feature for both gamma and hadron classes using **histograms**. This allowed for an understanding of the feature distributions and their separability between the two classes.

-----

## 🤖 Model & Results

A machine learning model was developed to classify the particles. Upon evaluating the model's performance on the test set, the following classification report was generated:

```
              precision    recall  f1-score   support

           0       0.86      0.79      0.82      3804  (Hadron)
           1       0.91      0.94      0.93      7836  (Gamma)

    accuracy                           0.89     11640
   macro avg       0.89      0.87      0.87     11640
weighted avg       0.89      0.89      0.89     11640
```

**Key Performance Metrics:**

  * The model achieved an overall **accuracy of 89%**.
  * For the **gamma (signal) class (1)**, the model demonstrated high performance with a precision of **0.91**, recall of **0.94**, and an f1-score of **0.93**. This indicates that the model is very effective at identifying gamma-ray events and minimizing false negatives.
  * For the **hadron (background) class (0)**, the model showed a precision of **0.86**, recall of **0.79**, and an f1-score of **0.82**. While slightly lower than the gamma class, these metrics still indicate strong performance in filtering out background noise.

-----

## ✨ Conclusion

This project successfully demonstrates the application of machine learning techniques for classifying MAGIC Gamma Telescope events. The high accuracy and strong f1-scores for both classes, particularly for gamma events, highlight the model's effectiveness in distinguishing between signal and background. This work is a foundational step towards enabling more precise and efficient analysis of high-energy astronomical data.

-----

## 🚀 How to Run

This project is contained within a Jupyter Notebook (`fcc_magic.ipynb`). To run it:

1.  **Clone the Repository (if applicable):** If this notebook is part of a GitHub repository, clone it to your local machine. The original notebook mentions an "Open In Colab" badge, suggesting it's hosted on GitHub: [https://colab.research.google.com/github/Olamaryse/magic-telescope/blob/main/fcc\_magic.ipynb](https://colab.research.google.com/github/Olamaryse/magic-telescope/blob/main/fcc_magic.ipynb).
2.  **Install Dependencies:** Ensure you have Python installed, along with the necessary libraries:
    ```bash
    pip install numpy pandas matplotlib scikit-learn
    ```
3.  **Run the Notebook:** Open the `fcc_magic.ipynb` file using Jupyter Notebook or JupyterLab, or simply click on the "Open In Colab" badge provided in the original notebook to run it directly in Google Colab.
4.  **Data File:** Make sure the `magic04.data` file is accessible in a `sample_data` directory relative to the notebook, or update the `pd.read_csv` path accordingly.

-----
