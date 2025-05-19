# Binary Classification of Bug Reports in Issue Tracking Systems using Machine Learning

Duplicate bug report detection is a crucial task for any large-scale software project since it helps detect and triage redundant issues that occur during its lifecycle. For example, when Microsoft Word crashes several times, one can file multiple bug reports on the same issue using different words or forms of expression. This creates unnecessary load on the developer's end and reduces their efficiency by wasting their valuable time in deciphering similar queries and going through multiple reports filed on the same problem.<br>

From the large number of bug reports and issues generated in code repositories of software projects, almost a third of them are found to be duplicates. The widespread problem of duplicate bug reports leads to unproductive software development life cycles and wasteful resource usage. It creates bigger problems for the developers to fix the issues. Identification of these duplicates can be done manually, but it is a very time consuming process. For this reason, there have been many approaches that use automation for classifying different bug reports into duplicates or non-duplicates.
This work proposes a machine-learning approach using binary classification.<br>

We have evaluated our approach using a master dataset consisting over 1,22,000 bug reports which is the amalgamation of both duplicate and non-duplicate reports from three real-world datasets collected from open source projects (Eclipse, Mozilla, and ThunderBird). Our results show that the proposed approach outperforms several machine-learning baselines in terms of precision, recall and AUC (Area Under the Curve) score.<br>


# Datasets
1. Eclipse - 46,908 (duplicates and non-duplicates)
2. Mozilla Firefox - 60,904 (duplicates and non-duplicates)
3. Mozilla ThunderBird - 14,263 (duplicates and non-duplicates)

# Flow of the Proposed Approach
![](/Process_new.jpeg)

## Stage 1 : Data preparation
  - Datasets consisting of duplicate & non-duplicate bug report data is merged for the three datasets, individually.
  - Merged datasets from the three open-source projects are combined to form a larger dataset containing 1,22,075 data samples (bug report pairs).

## Stage 2 : Data Preprocessing
  - Bug title and description are concatenated for each of the bug report pairs.
  - Stop words are removed from the concatenated string to minimize presence of words that don't add to the meaning of the bug reports.
  - Punctuation marks are removed from the strings.

## Stage 3: Feature Extraction and Dataset Preparation

* The preprocessed text (combined title and description) is vectorized using techniques such as TF-IDF or Bag of Words.
* The vectorized dataset is then split into a **Training Set** and a **Testing Set**, maintaining appropriate class balance between duplicate and non-duplicate samples.

## Stage 4: Model Training

* Multiple machine learning classifiers are trained using the training set. In our approach, we experimented with:

  * **Logistic Regression (LR)**
  * **Decision Trees (DT)**
  * **Random Forests (RF)**
* Each model is trained independently to learn the underlying patterns of duplication in bug reports.

## Stage 5: Prediction and Evaluation

* The trained models are evaluated on the testing set.
* A **prediction matrix** is generated, which contains predictions for each pair of bug reports in the testing set.
* Based on these predictions, a final binary classification is made:

  * If the pair is predicted as a **duplicate**, it is classified as **Positive**.
  * Otherwise, it is classified as **Negative**.
* Evaluation metrics such as **Precision**, **Recall**, **Accuracy**, and **AUC Score** are computed to assess model performance.

## Key Highlights

* Utilizes only **title** and **description** fields from bug reports—no need for metadata or stack traces.
* Trained and evaluated on a **real-world large-scale dataset** of over 122,000 bug report pairs.
* Achieves **\~62% Recall** and **\~80% Accuracy**, significantly improving over baseline methods.
* Designed for **scalability** across diverse issue tracking systems and open-source repositories.
      
<!-- ## Research Articles

- The research paper for this research is available [here](https://www.researchgate.net/publication/341605950_Fast_Detection_of_Duplicate_Bug_Reports_using_LDA-based_Topic_Modeling_and_Classification).
-->
