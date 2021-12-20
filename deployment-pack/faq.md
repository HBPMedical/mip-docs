# FAQ

ACCESS & AUTHORISATION
---
1. **Do I need an HBP account to connect to the MIP?**
- You do need HBP credentials to access a federated MIP. For MIP Local, access is granted by the local administrator.

2. **How can I get my credentials for a MIP federation?**
- Please refer to the MIP user manual.

GENERAL QUESTIONS
---
1. **How long has the MIP been working?**
- The MIP has been working since 2015.

2. **Do we need two independent servers to install the MIP?**
- In order to perform federated analysis, the MIP local and the MIP federated must be installed on 2 separated servers.

3. **What are the requirements to install the MIP?**
- Please refer to the Installation Prerequisites document.

4. **Can I install the MIP in my laptop?**
- This is an interesting option that is being tested and may be available in the future.

TRAINING
---
1. **Will users have a training on the MIP?**
- A set of training videos is already available from the MIP user interface. A more detailed training can be organised on request.

2. **Are regular webinars planned in order to show the users the last updates of the system and to allow the centres to ask their questions to the HPB team?**
- Yes, webinars will be organised regularly.

SERVICES
---
1. **In case of MIP malfunction, is there a technical service support department?**
- Yes we will provide technical support free of charge. In case of technical problems, please write to <support@ebrains.eu>, we will reach out to you in the briefest delay.

2. **When the MIP is installed locally, how will the technical team is going to solve the issues without connecting to the local server?**
- Our engineers will provide you support by phone, email and skype. 

3. **If we are not able to solve the problem, is there any possibility that one of your engineers come help us in situ?**
- Your request will be studied on a case-by-case basis. Normally all cases can be resolved by remote access to your servers by our engineer.

4. **Will the opinions/questions of users be requested by the HBP as part of a quality assessment process?**
- A Quality Assessment program will be implemented in the following months in order to analyse user's MIP evaluation.

DATA
---
1. **Which kind of analysis can we perform with the MIP?**
- Run exploratory data analyses, create and share analysis models, execute descriptive statistics, inferential statistics and machine-learning algorithms on user-defined analysis models on the data reunited from an increasing number of datasets.

As of May 2020, the following algorithms are available in the system:
 - ANOVA
 - CART
 - Calibration Belt
 - ID3
 - Kaplan-Meier Estimator
 - Linear Regression
 - Logistic Regression
 - Naive Bayes Training 
 - Naive Bayes with Cross Validation
 - Pearson Correlation 
 - Principal Components analysis 
 - T-Test Independent
 - T-Test One-Sample 
 - T-Test Paired 
 - k-Means Clustering

> All the analysis on MIP is aggregated and can't be made on an individual level. However, sampling and filtering the data within certain groups is possible.

2. **Will the dataset we introduced to the MIP local be automatically transferred to the MIP federated or we will have to enter the data again?**
- At the time of joining the MIP federation, the hospital will run the "MIP anonymization" module whose function is to anonymize and copy MIP local data to the server (OR NODE). It is this second dataset (anonymized) that will then be used by the federation. 

3. **Who has to anonymize the data?**
- Data anonymization is supported by the "MIP anonymization module" whose main function is to create a second dataset identical to the source be fully anonymized. Running the module is performed by the hospital personnel.

4. **Can we share any kind of data or there are already pre-selected variables?**
- There definitely is an existing set of variables that the MIP
 knows and recognizes. This data set can be extended hospital by
 hospital under certain circumstances.  If the new variables are
 considered "common" they are added to the common set of variables 
 the MIP uses and recognizes.  If considered as local only then 
 the variable can be added to the MIP but as a local extension. 
 Note that the objective is to ensure the set of variables (common 
 or local) the MIP supports must have a justification.  There is a 
 selection / approval process that will take place before the MIP 
 set of variables is extended or augmented.  


5. **Can we publish the data obtained with the MIP?**
- No problem with publishing results obtained using the hospital 
 data on the MIP in local mode.  In a federated mode and before 
 joining the federation of hospitals, the new hospital will be 
 requested to sign an agreement to use the data made available 
 (shared) by others wisely.  This includes the rights to publish
 experiences and papers based on the use of the data accessed.


6. **Is there any system to detect/eliminate duplicated patients across the databases?**
- This will have to be done for a large part by the hospital 
 personnel before starting the data ingestion process.  During the 
 ingestion processes mechanisms are in place to verify and
 harmonize data across data from different origins.  This includes 
 detecting duplications.


7. **If we analyse some data today, are we going to obtain the same results if we analyse the same datasets in the future? If not, how can we come back to the same dataset to repeat our analysis?**
- Assuming the content of the dataset has not changed, and the
 parameters used are the same, the answer is YES.  The answer is
 NO if new data have been added over time or if parameters
 changed.  We are aware of this limitation and have a pending
 requirement to allow the same "experiment" to be run more than 
 once over time making the experiment reproducible.  It shall be
 implemented at a later date.


8. **Is it mandatory to share data in the MIP federated if we want to have access to the other datasets?**
- By joining the federation, the new hospital obtains access to 
 data of other hospital in the federation and by joining 
 authorizes de facto other hospitals access to its data. 


9. **Can I choose with which hospitals we want to share our data?**
- Interested groups of researchers with a common use case can 
 propose to form a federation, define the data format and limit 
 who can participate. Please contact the MIP management team for
 more information. 


10. **How can I connect clinical data to image data that came from the same patient?**
- You need to add an ID (a number) that connects data from both 
 sources. The data ingestion process and the data factory set of
 tools is designed to identify and manage these cases. Quality and 
 consistency of data is ensured by such mechanisms.  However, this 
 ID will be anonymized after the anonymization process to assure
 the minimum security measurment and prevent people from 
 reidentifying the record. 


11. **After pre-processing the images, can they be deleted, or should they be kept stored?**
- For MIP usage the extract from the pre-orocessing step is
 sufficient. However, it's within the best practice and the 
 accounatbility of the hospital to keep a back-up of such 
 important data as part of their own database.


12. **Could it affect other data stored in the same server?**
- MIP could affect the execution of other programs only if the disk/server is saturated and there is not enough free space.


***

***
