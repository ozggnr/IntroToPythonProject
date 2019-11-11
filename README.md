# Homework 8 - Short Report about Visualization of Breast Cancer Wisconsin Dataset

In this short report, Breast Cancer Dataset from sklearn database was investigated. As a first step, effect of
features on the classification of diagnosis (target: Maleign (as 0) or Benign (as 1)) was observed. There are 30 features in this dataset, and 
after plotting each feature against diagnosis, 10 features among them based on their distinctive data distribution against 
diagnosis was selected and presented in Figure 1 below. 20 features were eliminated because their distribution was not clear to identify any region that allow us to differentiate particular diagnosis. 

Figure 1.
![](pairplot_target.png)

As a second step, correlation between these 10 features was analysed, and plotted as a heat map using seaborn in Figure 2. This part is crucial to understand how these features are independent from each other. It is mostly inefficient to use highly correlated features while processing the data. 

Figure 2.
![](breastcancer_heat_map.png)


As it seem in Figure 2 that 'mean radius', 'mean perimeter', 'mean area', 'worst radius', 'worst perimeter', and 'worst area' are highly correlated with each other (>90%). It means that we can select one representative feature among them. Such a selection can reduce dimension significantly, and therefore complexity. For instance, two highly correlated features ('mean area' and 'mean perimeter') and one showing average correlation ('perimeter error') with respect to 'mean radius' are normalized(to see their behaviour in the same range) and plotted in Figure 3. Here, while 'mean area' and 'mean perimeter' are showing almost linear distribution against 'mean radius', 'perimeter error' indicates it as totally different and nonlinear.

Figure 3.
![](similarities.png)

As a result, by eliminating highly correlated features, I end up with three features in total. These features show independent distribution with respect to each other. I can recommend to focus more on these three features while processing the data for future analysis. Moreover, for efficiency, instead of collection thirty features, one can collect data by considering only these three features. Figure 4 shows the pairplot of these three features and corresponding diagnosis was identified with different colors. Distribution of diagnosis as 0 and 1 indicates their regions are almost well seperated. It makes us to be able to decide the diagnosis by considering the corresponding value regions. 

Figure 4.
![](final_feature.png)
