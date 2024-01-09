# **ITSM (IT Service Management)**

---------
## **Business Case-Study**

ABC Tech is an mid-size organisation operation in IT-enabled business
segment over a decade. On an average ABC Tech receives 22-25k IT
incidents/tickets , which were handled to best practice ITIL framework
with incident management , problem management, change management
and configuration management processes. These ITIL practices attained
matured process level and a recent audit confirmed that further
improvement initiatives may not yield return of investment.
ABC Tech management is looking for ways to improve the incident
management process as recent customer survey results shows that
incident management is rated as poor.

Machine learning looks prospective to improve ITSM processes through
prediction and automation. They came up with key areas, where ML can
help ITSM process in ABC Tech.

**1)** Predicting High Priority Tickets so that they can take preventive measures or fix the problem before it surfaces.

**2)** Forecast the incident volume monthwise and quarterwise. So that they can be better prepared with resources and technology planning.

**3)** Auto tag the tickets with right priorities and right departments so
that reassigning and related delay can be reduced.

--------
## **Dataset Description**

This Dataset contain Total of 24 features and 1 Target(Priority)

1) CI_Name: Represents the Configuration Item (CI) Name, which is an element of
the IT infrastructure that is managed in the context of IT Service Management.

2) CI_Cat: Denotes the category of the Configuration Item.

3) CI_Subcat: Specifies the subcategory of the Configuration Item. It provides more detailed information about the type of CI.

4) WBS: Stands for Work Breakdown Structure. It is a project management tool that represents a hierarchical decomposition of the total scope of work to be carried out by the project team.

5) Incident_ID: Unique identifier for each incident. It is a reference number or code assigned to each reported incident.

6) Status: Represents the current status of the incident.

7) Impact: Indicates the impact of the incident on the business or IT services.

8) Urgency: Reflects the urgency of addressing the incident.

9) Priority: Represents the overall priority assigned to the incident, which is often a combination of impact and urgency.

10) number_cnt: It's not explicitly described, but it may be a numerical count  associated with something in the dataset.

11) Category: Denotes the category of the incident, providing additional classification information.

12) KB_number: May refer to a Knowledge Base (KB) article number. Knowledge base articles are often used for documenting solutions to common issues.

13) Alert_Status: Represents the status of any alerts associated with the incident.

14) No_of_Reassignments: Indicates the number of times the incident has been reassigned or transferred to different support personnel or groups.

15) Open_Time: Represents the timestamp when the incident was initially reported or opened.

16) Reopen_Time: Timestamp indicating when the incident was reopened, if applicable.

17) Resolved_Time: Timestamp indicating when the incident was resolved or fixed.

18) Close_Time: Timestamp indicating when the incident was closed or marked as completed.

19) Handle_Time_hrs: Represents the time taken to handle or resolve the incident, often measured in hours.

20) Closure_Code: Denotes the code or reason for closing the incident.

21) No_of_Related_Interactions: Indicates the number of related interactions associated with the incident.

22) Related_Interaction: Information about the related interactions associated with the incident.

23) No_of_Related_Incidents: Represents the number of incidents related to the current incident.

24) No_of_Related_Changes: Indicates the number of related changes associated   with the incident.

25) Related_Change: Information about the related changes associated with the incident.

-------------
### **Analysis for Categorical data:**

1) For CI_Cat graph, it is not an ordinal data so we have to perform one hot encoding in preprocessing.
![image](https://github.com/anjanikmr39/ITSM-IT-Service-Management-/assets/67219753/957c62a9-4673-4342-9645-cf04b6debf75)

2) For CI_Subcat graph, it is not an ordinal data so we have to perform one hot encoding in preprocessing.
![image](https://github.com/anjanikmr39/ITSM-IT-Service-Management-/assets/67219753/920631cd-534c-42da-82d0-238d3e0947b7)

3) For Status graph, all new user data will come under work in progress, so there is no meaning to keep that feature.
4) Impact and Urgency have proportional relationship with Priority.
5) For Impact and Urgency, it have high correlation with Priority so we have to drop these features.
![image](https://github.com/anjanikmr39/ITSM-IT-Service-Management-/assets/67219753/e17a64d4-8742-48d0-ad96-119841b4c2bd)

6) For Category graph, it is not an ordinal data so we have to perform one hot encoding in preprocessing.
![image](https://github.com/anjanikmr39/ITSM-IT-Service-Management-/assets/67219753/234d7a17-668b-4d24-ad9d-b737bc83b231)

7) For Closure_Code graph, it is not an ordinal data so we have to perform one hot encoding in preprocessing.
![image](https://github.com/anjanikmr39/ITSM-IT-Service-Management-/assets/67219753/5ed9d558-54ca-4f6e-9cb3-6bfc0379c65e)

----------------
### **Analysis for Numerical data**

1) Open_Time, Resolved_Time and Close_Time have almost uniform distribution with time zone.
2) We re-created Handle_Time_hrs from Open_Time and Resolved_Time that's why we do no need these three time features.
![image](https://github.com/anjanikmr39/ITSM-IT-Service-Management-/assets/67219753/4e2c7473-dfa1-45df-b500-c8cb2159bc3b)


3) As No_of_Reassignments increase, Priority also increases means they have directly proportional to each other.
4) As No_of Related_Interactions decrease, Priority increases means they have inversely proportional to each other.
![image](https://github.com/anjanikmr39/ITSM-IT-Service-Management-/assets/67219753/ff73d808-9797-4968-9156-6c4d1f87b574)

5) Handle_Time_hrs have very good relation with Priority as it increases with Priority from 2 to 5.
![image](https://github.com/anjanikmr39/ITSM-IT-Service-Management-/assets/67219753/ce492cd2-2e8e-43bd-b3fd-43e59e13e636)

---------

## **Model Comparison Report (Predicting High Priority Tickets)**

![image](https://github.com/anjanikmr39/ITSM-IT-Service-Management-/assets/67219753/06415b47-6b76-4d2a-bba3-40ff9c4b2682)

**For Random Forest**
![image](https://github.com/anjanikmr39/ITSM-IT-Service-Management-/assets/67219753/5e35cbff-dd40-40cc-87f1-77d6c305c1a1)

--------------

## **Forecasting Incidents Monthwise and Quaterwise using ARIMA Model**

```
Next 6 Monthwise Prediction of Incidents:
2015-01-01     252.197412
2015-02-01     352.553861
2015-03-01     666.475410
2015-04-01     686.779352
2015-05-01     460.035020
2015-06-01     376.535520
```

![image](https://github.com/anjanikmr39/ITSM-IT-Service-Management-/assets/67219753/88d332a2-3f9c-4f0e-a8d1-903f74df5de2)


```
Next 3 Quarterwise Prediction of Incidents:
2015-03-31    16193.964191
2015-06-30    14089.153918
2015-09-30     3120.236192
```

![image](https://github.com/anjanikmr39/ITSM-IT-Service-Management-/assets/67219753/7b379180-b3ca-437f-b431-8294fe293930)

------------

## **Auto Tag the Tickets with right Priorities and right Departments**


1) We only requires (CI_Cat, CI_Subcat, Priority, Category, No_of_Reassignments, Handle_Time_hrs, Closure_Code, No_of_Related_Interactions) for Auto Tag.

2) CI_Cat will be the Target, So,we are doing Label Encoding of CI_Cat, since it is not ordinal data.

3) Since For this model we need right priorities and right departments. Thus No of Reassignments can be 0 or 1 so we drop 8673 rows where No of Reassignments greater than 1.

4) One hot encoding of these (CI_Subcat, Category, Closure_Code) features will be required, since it is not ordinal data.

5) We have to scale entire dataset between 0 to 1 that is MinMAx scaling because Handle_Time_hrs feature should not goes below zero.


```
Model Comparison Report (Auto tag the tickets with right priorities and right departments):
+-------------------+----------------------------+---------------------------+
| Model Name        |   Before Hyperparameter(%) | After Hyperparameter(%)   |
+===================+============================+===========================+
| Decision Tree     |                      82.53 | 82.03                     |
+-------------------+----------------------------+---------------------------+
| Random Forest     |                      82.63 | 83.23                     |
+-------------------+----------------------------+---------------------------+
| Gradient Boosting |                      84.08 | NA                        |
+-------------------+----------------------------+---------------------------+
```

**For Gradient Boosting**

![image](https://github.com/anjanikmr39/ITSM-IT-Service-Management-/assets/67219753/ebeeff3f-c2f8-4424-a342-4f364875942f)

-------

## **Challenges Faced:**

1) Empty cell present in features but not showing in isnull().sum() code , so we have to perform logic to show it into null values.

2) Given handle time hr is not understood so we create our own handle time from open time and resolve time.

3) Selecting best parameter range for Hyperparameter tuning in Decision Tree and Random Forest model for High priority Tickets and Auto Tag objectives.

4) Creating Monthwise features with incidents from open time and CI_Cat is tricky and requires logic.

5) Creating Quarterwise features with incidents from open time and CI_Cat is tricky and require logic.

-------

## **More information**
Visit this python file for more detailed analysis [ITSM.ipynb](https://github.com/anjanikmr39/ITSM-IT-Service-Management-/blob/master/ITSM.ipynb)
