## **Fraudulent Claim Detection**

## Problem Statement
Global Insure, a leading insurance company, processes thousands of claims annually. However, a significant percentage of these claims turn out to be fraudulent, resulting in considerable financial losses. The company’s current process for identifying fraudulent claims involves manual inspections, which is time-consuming and inefficient. Fraudulent claims are often detected too late in the process, after the company has already paid out significant amounts. Global Insure wants to improve its fraud detection process using data-driven insights to classify claims as fraudulent or legitimate early in the approval process. This would minimise financial losses and optimise the overall claims handling process.

## Business Objective
Global Insure wants to build a model to classify insurance claims as either fraudulent or legitimate based on historical claim details and customer profiles. By using features like claim amounts, customer profiles and claim types, the company aims to predict which claims are likely to be fraudulent before they are approved.


Based on this assignment, you have to answer the following questions:<br>

● How can we analyse historical claim data to detect patterns that indicate fraudulent claims?<br>
● Which features are most predictive of fraudulent behaviour?<br>
● Can we predict the likelihood of fraud for an incoming claim, based on past data?<br>
● What insights can be drawn from the model that can help in improving the fraud detection process?<br>

## Assignment Tasks
You need to perform the following steps for successfully completing this assignment:
1. Data Preparation
2. Data Cleaning
3. Train Validation Split 70-30
4. EDA on Training Data
5. EDA on Validation Data (optional)
6. Feature Engineering
7. Model Building
8. Predicting and Model Evaluation

9. ## Data Dictionary
The insurance claims data has 40 Columns and 1000 Rows. Following data dictionary provides the description for each column present in dataset:<br>

<table>
  <thead>
    <tr>
      <th>Column Name</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>months_as_customer</td>
      <td>Represents the duration in months that a customer has been associated with the insurance company.</td>
    </tr>
    <tr>
      <td>age</td>
      <td>Represents the age of the insured person.</td>
    </tr>
    <tr>
      <td>policy_number</td>
      <td>Represents a unique identifier for each insurance policy.</td>
    </tr>
    <tr>
      <td>policy_bind_date</td>
      <td>Represents the date when the insurance policy was initiated.</td>
    </tr>
    <tr>
      <td>policy_state</td>
      <td>Represents the state where the insurance policy is applicable.</td>
    </tr>
    <tr>
      <td>policy_csl</td>
      <td>Represents the combined single limit for the insurance policy.</td>
    </tr>
    <tr>
      <td>policy_deductable</td>
      <td>Represents the amount that the insured person needs to pay before the insurance coverage kicks in.</td>
    </tr>
    <tr>
      <td>policy_annual_premium</td>
      <td>Represents the yearly cost of the insurance policy.</td>
    </tr>
    <tr>
      <td>umbrella_limit</td>
      <td>Represents an additional layer of liability coverage provided beyond the limits of the primary insurance policy.</td>
    </tr>
    <tr>
      <td>insured_zip</td>
      <td>Represents the zip code of the insured person.</td>
    </tr>
    <tr>
      <td>insured_sex</td>
      <td>Represents the gender of the insured person.</td>
    </tr>
    <tr>
      <td>insured_education_level</td>
      <td>Represents the highest educational qualification of the insured person.</td>
    </tr>
    <tr>
      <td>insured_occupation</td>
      <td>Represents the profession or job of the insured person.</td>
    </tr>
    <tr>
      <td>insured_hobbies</td>
      <td>Represents the hobbies or leisure activities of the insured person.</td>
    </tr>
    <tr>
      <td>insured_relationship</td>
      <td>Represents the relationship of the insured person to the policyholder.</td>
    </tr>
    <tr>
      <td>capital-gains</td>
      <td>Represents the profit earned from the sale of assets such as stocks, bonds, or real estate.</td>
    </tr>
    <tr>
      <td>capital-loss</td>
      <td>Represents the loss incurred from the sale of assets such as stocks, bonds, or real estate.</td>
    </tr>
    <tr>
      <td>incident_date</td>
      <td>Represents the date when the incident or accident occurred.</td>
    </tr>
    <tr>
      <td>incident_type</td>
      <td>Represents the category or type of incident that led to the claim.</td>
    </tr>
    <tr>
      <td>collision_type</td>
      <td>Represents the type of collision that occurred in an accident.</td>
    </tr>
    <tr>
      <td>incident_severity</td>
      <td>Represents the extent of damage or injury caused by the incident.</td>
    </tr>
    <tr>
      <td>authorities_contacted</td>
      <td>Represents the authorities or agencies that were contacted after the incident.</td>
    </tr>
    <tr>
      <td>incident_state</td>
      <td>Represents the state where the incident occurred.</td>
    </tr>
    <tr>
      <td>incident_city</td>
      <td>Represents the city where the incident occurred.</td>
    </tr>
    <tr>
      <td>incident_location</td>
      <td>Represents the specific location or address where the incident occurred.</td>
    </tr>
    <tr>
      <td>incident_hour_of_the_day</td>
      <td>Represents the hour of the day when the incident occurred.</td>
    </tr>
    <tr>
      <td>number_of_vehicles_involved</td>
      <td>Represents the total number of vehicles involved in the incident.</td>
    </tr>
    <tr>
      <td>property_damage</td>
      <td>Represents whether there was any damage to property in the incident.</td>
    </tr>
    <tr>
      <td>bodily_injuries</td>
      <td>Represents the number of bodily injuries resulting from the incident.</td>
    </tr>
    <tr>
      <td>witnesses</td>
      <td>Represents the number of witnesses present at the scene of the incident.</td>
    </tr>
    <tr>
      <td>police_report_available</td>
      <td>Represents whether a police report is available for the incident.</td>
    </tr>
    <tr>
      <td>total_claim_amount</td>
      <td>Represents the total amount claimed by the insured person for the incident.</td>
    </tr>
    <tr>
      <td>injury_claim</td>
      <td>Represents the amount claimed for injuries sustained in the incident.</td>
    </tr>
    <tr>
      <td>property_claim</td>
      <td>Represents the amount claimed for property damage in the incident.</td>
    </tr>
    <tr>
      <td>vehicle_claim</td>
      <td>Represents the amount claimed for vehicle damage in the incident.</td>
    </tr>
    <tr>
      <td>auto_make</td>
      <td>Represents the manufacturer of the insured vehicle.</td>
    </tr>
    <tr>
      <td>auto_model</td>
      <td>Represents the specific model of the insured vehicle.</td>
    </tr>
    <tr>
      <td>auto_year</td>
      <td>Represents the year of manufacture of the insured vehicle.</td>
    </tr>
    <tr>
      <td>fraud_reported</td>
      <td>Represents whether the claim was reported as fraudulent or not.</td>
    </tr>
    <tr>
      <td>_c39</td>
      <td>Represents an unknown or unspecified variable.</td>
    </tr>
  </tbody>
</table>

## **1. Data Preparation**
In this step, read the dataset provided in CSV format and look at basic statistics of the data, including preview of data, dimension of data, column descriptions and data types.
