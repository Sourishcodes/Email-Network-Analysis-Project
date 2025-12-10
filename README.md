Email Network Graph Analysis: Malicious Node Detection

Project Overview:
This project develops a Hybrid Anomaly Detection Model to identify suspicious actors (potential phishers or spammers) within large-scale email communication networks.
It surpasses traditional, static filters by analyzing both the structural behavior and the linguistic patterns of users across the entire network. 
The system is deployed using Unsupervised Learning (Isolation Forest), making it effective in environments where labeled data on new threats is scarce.


Methodology: Hybrid Feature Fusion
The core of this project lies in fusing two distinct data sources into a unified feature set.

1. Graph Theory (Network Structure)
We model all email communication as a Directed Graph. Each unique email address is a Node, and every sent email is a directed Edge.
The objective is to quantify the user's role and behavior. We calculate Network Centrality metrics (e.g., Out-Degree and Betweenness)
to identify users who exhibit anomalous communication patterns, such as mass-sending emails without receiving replies.

2. Natural Language Processing (Linguistic Content):
We analyze the aggregated text sent by each user using the TF-IDF (Term Frequency-Inverse Document Frequency) algorithm.
 This generates a numerical profile that highlights words used uniquely or disproportionately by a specific sender, which flags vocabulary commonly associated with phishing or threat activity.

Modeling and Results:
The fused feature dataset is processed by the Isolation Forest algorithm. 
This model specializes in finding outliers—nodes whose combined structural and linguistic profiles deviate statistically from the majority of legitimate users.
The model flags these outliers as Malicious Nodes. The system's effectiveness is validated by testing the trained model against an unseen dataset,
achieving an F1-Score of  0.0763. A network graph visualization is generated, clearly showing the detected malicious nodes.


Key Technologies and Setup

Language: Python
Libraries: pandas, networkx, scikit-learn, matplotlib
Data Source: Enron Email Dataset

How to Run the Project

1. Prerequisites: All required Python libraries (pip install pandas networkx scikit-learn).
2. Data Setup: two files: emails.csv (training data) and emails_test.csv (validation data) in the running directory.
3. Execution: The entire pipeline is contained within the uploaded code file.
   All cells to be run sequentially to execute data parsing, feature fusion, model training, visualization, and validation.
