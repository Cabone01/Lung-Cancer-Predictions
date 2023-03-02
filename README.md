# Lung-Cancer-Severity-Predictions
Lung cancer is an issue that can affect anyone whether they smoke or not. To make matters worse, it is the leading cause of cancer death. Those that are affected can be left with constant coughing with and without blood, chest pains, and shortness of breath. So to start, data was collected from [Kaggle](https://www.kaggle.com/datasets/thedevastator/cancer-patients-and-air-pollution-a-new-link) from a study that was published in Nature Medicine on cancer patients. The way the study was made was by giving a value of 1-7, 1-8, or 1-9. Lower values mean little to none and infrequent while upper values mean in great quantity and frequently. The dataset information is from a thousand patients and can be seen below with the number of unique values in each variable.    
![Data_nunique](https://user-images.githubusercontent.com/89541481/221752392-4335f88f-1851-4cd5-b7d3-3e86bcb3c632.PNG)

  
Tools
- Scikit-learn
- Pandas
- Numpy
- Seaborn
- Plotly
- Tableau
    
## Objective
The main objective here was to utilize machine learning to create a model to detect the severity of lung cancer of a patient. The different objective was to find the highest risk factors for lung cancer.

## Process
After some quick cleaning, I did a bit of unsupervised learning using PCA to find the number of components to variance. This was done to potentially find out the variables that I would need for supervised learning. Though the results made from this later proved to be insufficient when I began supervised learning. Before I created the model, I first created three heatmaps to see the correlation between the Cancer_Level and other variables.
    
![Correlation_Matrix_0](https://user-images.githubusercontent.com/89541481/221752362-5a24a8e2-ada5-4d02-82a6-9613ea7aa65a.PNG)    
In the first heat map, we can see in the top row that all the variables besides Age and Gender are moderately correlated with the Cancer_Level. With Age and Gender, there is essentially little to no correlation.
    
![Correlation_Matrix_1](https://user-images.githubusercontent.com/89541481/221752312-b9f91c12-86a0-4211-98e9-d21ad1e8dc4a.PNG)    
In the second heat map, we can see in the top row Obesity, Coughing of Blood, Balanced Diet, and Passive Smoker are more highly correlated. While the rest besides Weight Loss is moderate. Shockingly, Smoking had a lower correlation of 0.52 compared to Passive Smoker of 0.7. 
  
![Correlation_Matrix_2](https://user-images.githubusercontent.com/89541481/221752279-ea58f8bf-af3d-4347-8ef5-b2f28c25f50f.PNG)    
The third heat map shows that most of the variables besides Shortness of Breath are not correlated with the Cancer_Level. It is safe to assume that these can be somewhat ignored when considering risk factors.  

With those heat maps, I was able to determine both the highest and lowest risk factors for lung cancer. I then moved on to the next step which was to train test split for supervised learning. For this I ended up using half of the data for the test size and the rest for training. Then to create the model I used Multinomial Logistic Regression since three outcomes could be made from the Cancer_Level. The solver I used was newton-cg since there was not much data so I was able to make use of the more intensive solver. I was able to get an astonding training and testing score of 100%. As it can be seen below in the confusion matrix, The model was able to correctly predict the Cancer_Level from the testing sample.      
![Confusion_matrix_accuracy](https://user-images.githubusercontent.com/89541481/222294764-fdd070a6-694e-4347-ab91-ed9e37bf4fbd.png)

## Results
I was able to complete the main objective with a Multinomial Logistic Regression model that can detect the severity of lung cancer in a patient. I was also able to complete the extra objective of finding out the factors that posed the most risk in lung cancer as shown below.    

**Highest Risk Factors**
1. Obesity (0.83)
2. Coughing of Blood (0.78)
3. Alcohol Use (0.72)
4. Dust allergy (0.72)
5. Balanced Diet (0.71)
6. Passive Smoker (0.70)
   
   
**Lowest Risk Factors**
1. Gender (-0.16)
2. Age (0.06)
3. Wheezing (0.24)
4. Swallowing Difficulty (0.25)
5. Chubbing of Finger Nails (0.28)
6. Snoring (0.29)
      
Follow the link below for more information or a slightly deeper dive into the data. In there I used tableau to provide visuals to better display the affect on some risk factors and damages to the body.   
[Tableau](https://public.tableau.com/app/profile/taco5815/viz/LungCancerStudy/Sheet8?publish=yes)

## Source
[Kaggle](https://www.kaggle.com/datasets/thedevastator/cancer-patients-and-air-pollution-a-new-link)
