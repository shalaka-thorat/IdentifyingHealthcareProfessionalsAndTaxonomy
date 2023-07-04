# Identifying Healthcare Professionals and their Taxonomy
TechGig Doceree Machine Learning Hackathon: Identifying Healthcare Professionals (HCP) and their Taxonomy / Specialization<br>
<a href="https://www.techgig.com/codegladiators/machine-learning-hackathon">https://www.techgig.com/codegladiators/machine-learning-hackathon</a>

## Problem Statement:
▪ We are provided with ad server logs of users that contain information like IP addresses, geographic locations, site URLs, and related data. <br>
▪ The task is to build a machine learning model using the ad server logs data and predict whether a user belongs to HCP (Healthcare Professionals) category or not. <br>
▪ And if the user belongs to the HCP category, we must predict the taxonomy of the HCP as well. <br><br>

## Solution Proposed and Description:
▪ We start with data transformation such as Data pre-processing and Label Encoding on the Test Data we have, so as to make the data suitable for our ML Model. <br>
▪ Later on, we feed the data to our ML model, which in turn outputs the predictions with respective ID and IS_HCP, whether the user is HCP or not (1: HCP, 0: Non-HCP). <br>
▪ Furthermore, if the user is HCP, the model also provides the Taxonomy of HCP. The prediction files and their contents are as follows. <br>
▪ File Name: Doceree_HCP_Submission.csv <br>
▪ Columns:  <br>
  o  ID: Key<br>
  o IS_HCP: Indicates whether the user is Healthcare Professional (HCP) or not<br>
▪ File Name: Doceree_Taxonomy_Submission.csv<br>
▪ Columns: <br>
  o ID: Key<br>
  o IS_HCP: Indicates whether the user is Healthcare Professional (HCP) or not<br>
  o Taxonomy: Specialization code for HCP<br><br>

## Approach:
▪ Firstly, we import the train data and perform data analysis and pre-processing steps. We remove the data where the IS_HCP value is null, the Target column being null will not be useful for prediction. Later, we study each column and steps namely, null value identification and replacement, the importance of the column, and removing redundant columns.<br>
▪ Depending on our study, we perform Feature Engineering such as, we create CIDRBLOCK and URLDOMAIN columns by leveraging data from BIDREQUESTIP and URL columns resp. We create a DEVICE column and try to find the device type using the USERAGENT column, where DEVICETYPE is Unknown. Furthermore, we perform Label Encoding, Building Train, and Validation Sets.<br>
▪ Next, we enter the Model Building phase, we choose 2 algorithms depending on data size, and speed: Decision Tree Algorithm and Random Forest Algorithm, and compare their accuracy performance. The Random Forest model outperforms, so we choose it as our Final Model. Finally, we import our test data and perform data transformation to 
make the data suitable for the model, and get the predictions of whether the person is HCP or not.<br>
▪ For Taxonomy prediction, we take a subset of Training data where IS_HCP is 1 and perform steps such as Data Analysis, Pre-processing, Label Encoding, and training our ML model. For Test Data Prediction, if IS_HCP is predicted as 1 by our HCP Prediction Model, it is further passed on for Taxonomy Prediction. We store all these predictions in a CSV file as ID, IS_HCP, and Taxonomy columns. <br><br>

## Output:

### Model Evaluation:
<img src="https://github.com/shalaka-thorat/IdentifyingHealthcareProfessionalsAndTaxonomy/blob/main/Screenshots/Confusion%20Matrix%20of%20HCP%20Model.PNG"><br>

### Model Output for IS_HCP and Taxonomy columns:
<img src="https://github.com/shalaka-thorat/IdentifyingHealthcareProfessionalsAndTaxonomy/blob/main/Screenshots/Final%20Result%20IS_HCP%20and%20Taxonomy.PNG"><br>

### Model Output stored in CSV File:
<img src="https://github.com/shalaka-thorat/IdentifyingHealthcareProfessionalsAndTaxonomy/blob/main/Screenshots/Final%20HCP%20and%20Taxonomy%20Prediction%20File.PNG"><br><br><br>
### More Project Screenshots are <a href="https://github.com/shalaka-thorat/IdentifyingHealthcareProfessionalsAndTaxonomy/tree/main/Screenshots/">Here</a><br><br>
### Input Files can be accessed <a href="">Here</a>

