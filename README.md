# Note
Final Code: Team_2_SECOM_Pres_2_(Michael).ipynb

# Summary of the Project 
## Summary, Lessons Learned, and Best Practices 

The Semiconductor manufacturing industry is highly capital intensive with over 500 steps (Lam). Accurate detection of equipment faults is necessary to prevent abrupt equipment breakdowns and increase the efficiency of assembly lines, which are crucial for the world economy. In this project, literature was first reviewed to inform our decision-making around what data mining techniques to use to produce the best predictive model for wafer status detection on the SECOM dataset. The CRISP-DM model was used as a structured approach to planning our project, starting with business understanding to get a clear idea of our industry and business case.  Next, this project moved into data understanding to do an exploratory analysis of the data files to produce a direction for the next phase – data preparation. This research delivers various data cleaning techniques in an orderly process: first, merge & split data, then outlier analysis and treatment, rough feature removal, missing value imputation, feature selection, and finally, data balancing. They are to ensure data used for model construction is as neat as possible, which plays a crucial role in the model’s accuracy. Reaching the model building phase, the project team performed grid search and cross-validation to tune our hyperparameters before the final evaluation using confusion matrices and a custom weighted performance metric. The model with the best results is a combination of KNN imputation, ROSE Balancing, Lasso Feature Selection, keeping the outliers, and using a Random Forest Classifier. This model gives us 98% accuracy, 98% precision, 100% recall, 71% specificity, and a weighted metric of 84%.   

The main lessons learned around a data project like the SECOM Case are iterations, model requirements, CRISP-DM, testing, workflow, and documentation. Iterations are essential during our project to ensure that results are not just statistical anomalies. Understanding the requirements of each model is critical to ensure that the tools used do not rely on unsatisfied preconditions. Trying as many combinations in our pipeline as possible, fine-tuning, and revisiting all steps in the CRISP-DM process are necessary, particularly data preparation, as this step defines the quality of the data which the model gets trained with. And of course, documenting our process is crucial to track the workflow and determine unobserved areas.  

Classification prediction models are beneficial for the prediction of faults in the semiconductor wafer fabrication process. Our research provides a method for predictive maintenance by collecting and processing raw data from the hundreds of built-in sensors on the manufacturing floor and then performing classification through predictive models. This paper and related research become even more relevant as semiconductor manufacturing continues to become more complex and the industry continues to grow exponentially.  

# Data Set Information:

A complex modern semi-conductor manufacturing process is normally under consistent surveillance via the monitoring of signals/variables collected from sensors and or process measurement points. However, not all of these signals are equally valuable in a specific monitoring system. The measured signals contain a combination of useful information, irrelevant information as well as noise. It is often the case that useful information is buried in the latter two. Engineers typically have a much larger number of signals than are actually required. If we consider each type of signal as a feature, then feature selection may be applied to identify the most relevant signals. The Process Engineers may then use these signals to determine key factors contributing to yield excursions downstream in the process. This will enable an increase in process throughput, decreased time to learning and reduce the per unit production costs.

To enhance current business improvement techniques the application of feature selection as an intelligent systems technique is being investigated.

The dataset presented in this case represents a selection of such features where each example represents a single production entity with associated measured features and the labels represent a simple pass/fail yield for in house line testing, figure 2, and associated date time stamp. Where –1 corresponds to a pass and 1 corresponds to a fail and the data time stamp is for that specific test point.


Using feature selection techniques it is desired to rank features according to their impact on the overall yield for the product, causal relationships may also be considered with a view to identifying the key features.

Results may be submitted in terms of feature relevance for predictability using error rates as our evaluation metrics. It is suggested that cross validation be applied to generate these results. Some baseline results are shown below for basic feature selection techniques using a simple kernel ridge classifier and 10 fold cross validation.

Baseline Results: Pre-processing objects were applied to the dataset simply to standardize the data and remove the constant features and then a number of different feature selection objects selecting 40 highest ranked features were applied with a simple classifier to achieve some initial results. 10 fold cross validation was used and the balanced error rate (*BER) generated as our initial performance metric to help investigate this dataset.


SECOM Dataset: 1567 examples 591 features, 104 fails


# Attribute Information:

Key facts: Data Structure: The data consists of 2 files the dataset file SECOM consisting of 1567 examples each with 591 features a 1567 x 591 matrix and a labels file containing the classifications and date time stamp for each example.

As with any real life data situations this data contains null values varying in intensity depending on the individuals features. This needs to be taken into consideration when investigating the data either through pre-processing or within the technique applied.

The data is represented in a raw text file each line representing an individual example and the features seperated by spaces. The null values are represented by the 'NaN' value as per MatLab.
