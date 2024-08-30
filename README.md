# Call Centre Dataset -Dashboard

### Dashboard Link : https://app.powerbi.com/view?r=eyJrIjoiM2M4ZWM0ZDMtMjhhNy00ODkxLTlkY2UtNTBmNTI1OTQ4NWY5IiwidCI6IjE1NTE1N2M3LTc5MzUtNDkxYi04OWQxLWY5NTJhYWQ1YzYwOSJ9

## Problem Statement

Develop a Power BI dashboard to analyze customer churn, service subscriptions, and demographic data for a telecommunications company. The dashboard will track key KPIs, including total customers, number of tech and admin tickets, churned percentage, and yearly charges. It will provide insights into why customers left within the last month, highlighting patterns based on contract types, service usage, billing methods, and support ticket history. 
Additionally, it will identify popular services, assess the impact of billing and account management on customer satisfaction, and explore demographic factors influencing retention. This data-driven tool will help the company reduce churn, optimize services, and improve customer satisfaction. Here is the [Data File](https://drive.google.com/drive/folders/1ly71LbR0uw0suMjJuJlpjZGlwQVK7bnu?usp=drive_link) 

### Steps followed 

### 1. Data Preparation
- Loaded the call center dataset into Power Query.
- Checked the column distribution to understand data structure and quality.

### 2. Measure Creation
- % of Dependents:  This measure calculates the percentage of churned customers who have dependents.
  ```DAX
  % of Dependents = DIVIDE(
    CALCULATE(COUNT('01 Churn-Dataset'[Dependents]), 
    '01 Churn-Dataset'[Dependents] = "Yes", 
    '01 Churn-Dataset'[Churn] = "Yes"), 
    CALCULATE(COUNT('01 Churn-Dataset'[Dependents]), 
    '01 Churn-Dataset'[Churn] = "Yes"), 
    0))
- Churned %:  This measure calculates the overall churn percentage based on the total number of customers.
    ```DAX
  Churned % = DIVIDE(
    CALCULATE(COUNT('01 Churn-Dataset'[Churn]), 
    '01 Churn-Dataset'[Churn] = "Yes"), 
    CALCULATE(COUNT('01 Churn-Dataset'[Churn]), 
    ALLSELECTED('01 Churn-Dataset'[Churn])))

- Partner Percentage:  This measure calculates the percentage of churned customers who have a partner.
    ```DAX
  Partner Percentage = DIVIDE(
    CALCULATE(COUNT('01 Churn-Dataset'[Partner]), 
    '01 Churn-Dataset'[Partner] = "Yes", 
    '01 Churn-Dataset'[Churn] = "Yes"), 
    CALCULATE(COUNT('01 Churn-Dataset'[Partner]), 
    '01 Churn-Dataset'[Churn] = "Yes"), 
    0)

- Phone Service:  This measure calculates the percentage of churned customers who have a phone service.
    ```DAX
  Phone Service = DIVIDE(
    CALCULATE(COUNT('01 Churn-Dataset'[PhoneService]), 
    '01 Churn-Dataset'[PhoneService] = "Yes", 
    '01 Churn-Dataset'[Churn] = "Yes"), 
    CALCULATE(COUNT('01 Churn-Dataset'[PhoneService]), 
    '01 Churn-Dataset'[Churn] = "Yes"), 
    0)

- Streaming Movies:  This measure calculates the percentage of churned customers who have a streaming movies service.
    ```DAX
  Streaming Movies = DIVIDE(
    CALCULATE(COUNT('01 Churn-Dataset'[StreamingMovies]), 
    '01 Churn-Dataset'[StreamingMovies] = "Yes", 
    '01 Churn-Dataset'[Churn] = "Yes"), 
    CALCULATE(COUNT('01 Churn-Dataset'[StreamingMovies]), 
    '01 Churn-Dataset'[Churn] = "Yes"), 
    0
)

- Online Security:  This measure calculates the percentage of churned customers who have online security services.
    ```DAX
  Online Security = DIVIDE(
    CALCULATE(COUNT('01 Churn-Dataset'[OnlineSecurity]), 
    '01 Churn-Dataset'[OnlineSecurity] = "Yes", 
    '01 Churn-Dataset'[Churn] = "Yes"), 
    CALCULATE(COUNT('01 Churn-Dataset'[OnlineSecurity]), 
    '01 Churn-Dataset'[Churn] = "Yes"), 
    0)

- Online Backup % :  This measure calculates the percentage of churned customers who have online backup services.

    ```DAX
  Online Backup % = DIVIDE(
    CALCULATE(COUNT('01 Churn-Dataset'[OnlineBackup]), 
    '01 Churn-Dataset'[OnlineBackup] = "Yes", 
    '01 Churn-Dataset'[Churn] = "Yes"), 
    CALCULATE(COUNT('01 Churn-Dataset'[OnlineBackup]), 
    '01 Churn-Dataset'[Churn] = "Yes"), 
    0)
### 3. Dashboard Visuals
The dashboard includes the following visualizations:

- **Card**: Displays all key performance indicators (KPIs) for a quick overview of essential metrics.

- **Bar Chart**: Provides detailed insights into:
  - Subscription duration of customers
  - Payment methods
  - Types of contracts chosen by customers

These visualizations help in understanding the data and making informed decisions. For a deeper analysis, please interact with the dashboard elements.

# Key Insights from the Dashboard



## Key Metrics

- **Customer Churn**: 27% of customers have churned the services.
- **Tech Support Tickets**: 2,955 tech support tickets were raised.
- **Admin Support Tickets**: 3,632 admin support tickets were recorded.
- **Partner Churn**: 36% of customers with partners have churned the services.
- **Senior Citizen Churn**: 25% of senior citizens have churned the services.
- **Dependent Churn**: 17% of customers with dependents have churned the services.
- **Preferred Payment Method**: Electric check was the most used payment method.
- **Contract Preference**: The month-to-month contract was the most popular among customers.
- **Phone Services Churn**: 91% of customers who churned had phone services, indicating a need for improvement in this area.

For further insights, please refer to the detailed dashboards.
## Snapshot of the dashboard
![Screenshot 2024-08-30 144921](https://github.com/user-attachments/assets/c1a2e6fb-0da4-45fb-b650-b9f4fa23d4f8)
