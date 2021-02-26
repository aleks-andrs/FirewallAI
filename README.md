# AI-based Web Application Firewall
Imagine that malicious web requests frequently hit the web server and traditional security solutions such as firewalls and signature-based intrusion detection systems are not capable of detecting them. A solution to this problem would be the development of an AI-based web application firewall. 

## Model
When it comes to building firewall systems, supervised learning may be more limited than unsupervised; in particular, classification algorithms may not be able to detect zero-day vulnerabilities since they are trained on the existent malicious sample data. On the other hand, unsupervised learning relies on a decision of whether an observation belongs to the benign distribution or should be considered as a different one (e.g. an outlier). However, not all outliers should be counted as malicious. It is possible that some legitimate queries might be misclassified as malicious since those queries deviate from the benign majority. Therefore, a supervised machine learning algorithm was selected for this problem, a Naive Bayes classifier. More information about data processing and model training can be obtained from the enclosed PDF file.

## Results
According to the generated confusion matrix, 95% of test data was classified as True Positive or True Negative. It should also be noted that the number of False Positive cases is larger than False Negatives, meaning that the model leans towards assigning test queries to benign class. While it is a preferable situation, the number of False Negatives is about 2% out of all benign queries. This means that a few benign queries may be classified as malicious, which can lead to disruption of service for the server. Higher accuracy may be achieved using other machine learning algorithms.
A prototype of the developed system can be downloaded using
> saveRDS(NBModel, "./final_NBModel.rds")

command and implemented as part of the server defence.
## Repository Files
1. Two data files are attached to demonstrate the source data used for model training, benign queries are in the “benignqueries.txt” file, while malicious queries are in the “maliciousqueries.txt” file.
2. The RMD file is a Markdown file that contains R code with comments.
3. The PDF file contains compiled code with corresponding results.