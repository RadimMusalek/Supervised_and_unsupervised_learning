# Supervised_and_unsupervised_learning
A group project on the supervised, unsupervised and semi-supervised learning algorithms
Group's members: Radim Musalek, Nhu Nguyen, Thuong Nguyen

## About the dataset

The source of the data is the paper called Dataset for estimation of obesity levels based on eating habits and physical condition in individuals from Colombia, Peru and Mexico by Fabio Mendoza Palechor and Alexis de la Hoz Manotas from the Universidad de la Costa, CUC in Colombia, published in Elsevier journal and sourced from the UCI website. 

The paper presents data for the estimation of obesity levels of individuals from the countries of Mexico, Peru and Colombia, based on their eating habits and physical condition. The data contains 17 attributes and 2111 records, the records are labeled with the class variable NObesity (Obesity Level), that allows classification of the data using the values of Insufficient Weight, Normal Weight, Overweight Level I, Overweight Level II, Obesity Type I, Obesity Type II and Obesity Type III. To balance the dataset 77% of the data was generated synthetically using the Weka tool and the SMOTE filter, 23% of the data was collected directly from users through a web platform.

## Summary & Findings

Basing on preprocessed (SMOTE) balanced dataset from research team, we continue to conduct preprocessing by calculating BMI variable basing on Weight and Height, convert using proper label encoding methods for categorical variables, and round abnormal values of some category variables caused by a middle process in SMOTE. 

Dataset is analysed to shed interesting insights of both categorical and continuous variables via EDA, which details can be found in the report file "ML_group_assignment_final".

After obtaining insights from the dataset, we continue with supervised learning (regression and classification), Semi-supervised learning and Unsupervised learning.

**Supervised learning - regression**

To understand the overall algorithms' suitability for our data we used the default settings of the Linear regression, RANSAC, Gradient descent, Supporting vector machine ("SVM"), Decision tree and Random forest models and selected SVM, Decision tree and Random forest for further parameter tuning as these achieved the best scores. The best performance could be achieved with the Random forest model which significantly outperformed other models and reached the 86% accuracy without overfitting on the training set.

**Supervised learning - classification**

We used Kneighbor Classifier, SVC, Logistic Regession, Decision Tree, Random Forest, AdaBoost Classifier, and GradientBoosting to compare the accuracy score without tunning for the model selection. And with the accuracy score higher than 70%, I chose Kneighbor Classifier, Decision Tree, Random Forest, and Gradient Boosting to continue. After feature scaling and parameters tuning, Random Forsest give the best result with accuracy score reached 84% and also a balanced f1_score between labels. Therefore, Random Forest will be selected among others to be the model prediction for the Obesity Level classification task.

**Semi-supervised learning**

We choose Logistic Regression as the model to work on. With the limited 100 labeled data, the accuracy score is 52%. After finding the representative sample using Kmeans and giving the labels to other instances, the score decreases to 35%. To improve the score, propagating the label to the 50 percentile closest to the centroid is used and make the improvement with the accuracy score is 57%. However, it is still need further improvement on both Kmeans and model selection as the score is still lower than expected.

**Unsupervised learning**

We aim to cluster around 7 balanced groups. We visualize our data using TSNE basing on original data, selected data from feature engineering, scaled and dimension deduction data, removed outliner data. Firstly, we see that using feature engineer or remove outliners in this case do not bring significant impact. Secondly, we identify relatively suitable clustering methods: Gaussian Mixture, Bayes Gaussian Mixture, and K-Means. After tuning parameters, Gaussian Mixture with scaled data input is the best option. The best output of clustering works well with SVC and Decision Tree, Random Forest, Gradient Boosting.