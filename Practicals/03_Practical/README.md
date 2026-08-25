# Azure Practical No. 03

## Build a Simple Website Endpoint with Azure Functions

### 1. Aim
To create and deploy a simple HTTP-triggered website endpoint using Azure Functions, test the endpoint, and review its execution information.

### 2. Theory

#### Azure Functions
- Azure Functions is a serverless compute service used to run code without managing servers.
- An HTTP-triggered function runs when an HTTP request is received and provides an endpoint URL.

#### Function App
- A Function App provides the environment required to host and run Azure Functions.
- It manages the execution, configuration, scaling and monitoring of functions.

#### HTTP Trigger
- An HTTP trigger starts a function when an HTTP request is received.
- The function can be tested through its endpoint using a browser.

### 3. Procedure / Main Tasks

## Task 1 — Open Cloud Shell

**Steps:**
1. In the Azure portal, select the **Cloud Shell** icon from the top toolbar.
2. Select **Bash** if prompted.
3. Select the lab subscription and complete the setup if required.
4. Wait until the Bash terminal opens and displays a `$` prompt.

**Observation:** Azure Cloud Shell was opened successfully and the Bash command prompt was available.

### 📸 Screenshots
![Task 1 Screenshot 1](Screenshots/Screenshot%202026-08-25%20200659.png)

![Task 1 Screenshot 2](Screenshots/Screenshot%202026-08-25%20200716.png)

---

## Task 2 — Create the function project

**Steps:**
1. Use Cloud Shell to create the function project as instructed by the lab.
2. Select the required runtime and create the project files.
3. Create the HTTP-triggered function using the specified function name.
4. Verify that the function project is created successfully.

**Observation:** The Azure Functions project and HTTP-triggered function were created successfully in Cloud Shell.

### 📸 Screenshots
![Task 2 Screenshot 1](Screenshots/Screenshot%202026-08-25%20201044.png)

![Task 2 Screenshot 2](Screenshots/Screenshot%202026-08-25%20201232.png)

---

## Task 3 — Deploy the function to Azure

**Steps:**
1. Use the Cloud Shell deployment command provided by the lab.
2. Select the required Function App as the deployment target.
3. Wait for deployment to complete.
4. Verify that the function is available in the Function App.

**Observation:** The function project was deployed to the Azure Function App successfully.

### 📸 Screenshots
![Task 3 Screenshot 1](Screenshots/Screenshot%202026-08-25%20201436.png)

![Task 3 Screenshot 2](Screenshots/Screenshot%202026-08-25%20201913.png)

---

## Task 4 — Test the HTTP endpoint in a browser

**Steps:**
1. Open the deployed function's HTTP endpoint.
2. Enter the endpoint URL in a browser.
3. Send the request and observe the response.
4. Verify that the expected response is displayed.

**Observation:** The HTTP endpoint responded successfully, confirming that the deployed function was running and accessible.

### 📸 Screenshots
![Task 4 Screenshot 1](Screenshots/Screenshot%202026-08-25%20202119.png)

![Task 4 Screenshot 2](Screenshots/Screenshot%202026-08-25%20202505.png)

---

## Task 5 — Verify the function in the portal

**Steps:**
1. Open the Function App in the Azure portal.
2. Open the **Functions** section.
3. Select the deployed HTTP-triggered function.
4. Verify its trigger and configuration details.

**Observation:** The deployed function was visible in the Azure portal with its HTTP trigger configuration.

### 📸 Screenshots
![Task 5 Screenshot 1](Screenshots/Screenshot%202026-08-25%20202810.png)

![Task 5 Screenshot 2](Screenshots/Screenshot%202026-08-25%20203427.png)

---

## Task 6 — Enable Application Insights

**Steps:**
1. Open the monitoring settings for the Function App.
2. Enable or configure **Application Insights** as instructed by the lab.
3. Save the configuration.
4. Verify that monitoring is enabled.

**Observation:** Application Insights was configured to provide monitoring information for the function.

### 📸 Screenshots
![Task 6 Screenshot 1](Screenshots/Screenshot%202026-08-25%20203609.png)

![Task 6 Screenshot 2](Screenshots/Screenshot%202026-08-25%20214818.png)

---

## Task 7 — Restrict access to the function

**Steps:**
1. Open the function's access or authorization settings.
2. Configure the access restriction specified by the lab.
3. Save the changes.
4. Verify that the configured access method is required.

**Observation:** Access to the function was restricted according to the configured security settings.

### 📸 Screenshots
![Task 7 Screenshot 1](Screenshots/Screenshot%202026-08-25%20214953.png)

![Task 7 Screenshot 2](Screenshots/Screenshot%202026-08-25%20215752.png)

---

## Task 8 — Test restricted access

**Steps:**
1. Open the function endpoint without the required access information.
2. Verify that the request is restricted.
3. Use the required function access key or method specified by the lab.
4. Send the request again and verify the expected response.

**Observation:** The configured access restriction was tested successfully and authorized access returned the expected response.

### 📸 Screenshots
![Task 8 Screenshot 1](Screenshots/Screenshot%202026-08-25%20220337.png)

![Task 8 Screenshot 2](Screenshots/Screenshot%202026-08-25%20220724.png)

---

## Task 9 — Review invocation logs

**Steps:**
1. Open the monitoring or Application Insights information for the Function App.
2. Review the function invocation records.
3. Check the request and execution information.
4. Verify that recent function calls are recorded.

**Observation:** Function invocation information was available for monitoring and review.

### 📸 Screenshots
![Task 9 Screenshot 1](Screenshots/Screenshot%202026-08-25%20220807.png)

![Task 9 Screenshot 2](Screenshots/Screenshot%202026-08-25%20221131.png)

---

### 4. Result
The simple website endpoint was successfully created using Azure Functions. The HTTP-triggered function was deployed, tested through its endpoint, secured according to the lab instructions, and monitored using invocation information.

### 5. Conclusion
Azure Functions provides a serverless method for building and deploying HTTP endpoints without managing traditional web servers. The practical demonstrated function creation, deployment, testing, access control and monitoring.
