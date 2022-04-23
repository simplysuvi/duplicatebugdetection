# Binary Classification of Bug Reports in Issue Tracking Systems

Duplicate bug report detection is a crucial task for any large-scale software project since it helps detect and triage redundant issues that occur during its lifecycle. For example, when Microsoft Word crashes several times, one can file multiple bug reports on the same issue using different words or forms of expression. This creates unnecessary load on the developer's end and reduces their efficiency by wasting their valuable time in deciphering similar queries and going through multiple reports filed on the same problem.<br>

From the large number of bug reports and issues generated in code repositories of software projects, almost a third of them are found to be duplicates. The widespread problem of duplicate bug reports leads to unproductive software development life cycles and wasteful resource usage. It creates bigger problems for the developers to fix the issues. Identification of these duplicates can be done manually, but it is a very time consuming process. For this reason, there have been many approaches that use automation for classifying different bug reports into duplicates or non-duplicates.
This work proposes a machine-learning approach using binary classification.<br>

We have evaluated our approach using a master dataset consisting over 1,22,000 bug reports which is the amalgamation of both duplicate and non-duplicate reports from three real-world datasets collected from open source projects (Eclipse, Mozilla, and ThunderBird). Our results show that the proposed approach outperforms several machine-learning baselines in terms of precision, recall and AUC (Area Under the Curve) score.<br>

**This work only considers the title and description of the reports for detecting duplicates. The experimental results show that the proposed machine-learning model achieves a recall rate of ~62% and accuracy of about 80% in detecting the duplicate bug reports correctly.**

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
      
<!-- ## Research Articles

- The research paper for this research is available [here](https://www.researchgate.net/publication/341605950_Fast_Detection_of_Duplicate_Bug_Reports_using_LDA-based_Topic_Modeling_and_Classification).
-->
