# Azure Practical No. 03

## Build a Simple Website Endpoint with Azure Functions

### 1. Aim
To create and deploy a simple HTTP-triggered website endpoint using Azure Functions, test the endpoint, review invocation information, and apply access control.

### 2. Theory

#### Azure Functions
- Azure Functions is a serverless compute service used to run code without managing traditional servers.
- It supports event-driven execution, including HTTP-triggered functions.

#### Function App
- A Function App provides the environment for hosting and running Azure Functions.
- It manages the function configuration, execution and monitoring.

#### HTTP Trigger
- An HTTP trigger starts a function when an HTTP request is received.
- The function can be accessed and tested through a public endpoint URL.

#### Application Insights
- Application Insights provides monitoring and diagnostic information about function executions and requests.

### 3. Procedure / Main Tasks

## Task 1 — Create the resource group

**Steps:**
1. Sign in to the Azure portal using the lab account.
2. Open **Resource groups** from the Azure portal.
3. Select **Create**.
4. Enter the resource group name specified in the lab, select the required region, and create the resource group.

**Observation:** The required resource group was created successfully and was ready to contain the Function App resources.

### 📸 Screenshots
![Task 1 Screenshot](Screenshots/Screenshot%202026-08-25%20201044.png)

---

## Task 2 — Configure the Function App

**Steps:**
1. Search for **Function App** in the Azure portal and select **Create**.
2. Select **Flex Consumption** as the hosting option.
3. Select the created resource group and enter the required Function App name.
4. Configure the region, **Node.js** runtime stack and required version.
5. Keep the required monitoring settings enabled and select **Review + create**.
6. Create the Function App and wait for deployment to complete.

**Observation:** The Function App was configured with Flex Consumption hosting and the required runtime and monitoring settings.

### 📸 Screenshots
![Task 2 Screenshot 1](Screenshots/Screenshot%202026-08-25%20201232.png)

![Task 2 Screenshot 2](Screenshots/Screenshot%202026-08-25%20201436.png)

![Task 2 Screenshot 3](Screenshots/Screenshot%202026-08-25%20201509.png)

---

## Task 3 — Open Cloud Shell

**Steps:**
1. Select the **Cloud Shell** icon in the Azure portal.
2. Select **Bash** when prompted.
3. Select the required subscription and complete the Cloud Shell setup.
4. Wait until the Bash terminal opens and displays a `$` prompt.

**Observation:** Azure Cloud Shell was opened successfully and the Bash command prompt was available.

### 📸 Screenshots
![Task 3 Screenshot 1](Screenshots/Screenshot%202026-08-25%20202138.png)

![Task 3 Screenshot 2](Screenshots/Screenshot%202026-08-25%20202505.png)

---

## Task 4 — Create the function project

**Steps:**
1. Create a new function project folder in Cloud Shell.
2. Initialize the project using the Node.js runtime.
3. Create the **GetStatus** HTTP-triggered function.
4. Verify that the function files are created successfully.

**Observation:** The Node.js function project and HTTP-triggered function were created successfully.

### 📸 Screenshots
![Task 4 Screenshot 1](Screenshots/Screenshot%202026-08-25%20202810.png)

![Task 4 Screenshot 2](Screenshots/Screenshot%202026-08-25%20202957.png)

---

## Task 5 — Deploy the function to Azure

**Steps:**
1. Find the Function App name using Azure CLI.
2. Publish the function project to the Function App using the Azure Functions Core Tools command.
3. Wait for the deployment to complete.
4. Copy the **Invoke URL** shown in the deployment output.

**Observation:** The GetStatus function was successfully deployed to the Azure Function App and an Invoke URL was provided.

### 📸 Screenshots
![Task 5 Screenshot](Screenshots/Screenshot%202026-08-25%20203609.png)

---

## Task 6 — Test the HTTP endpoint in a browser

**Steps:**
1. Open a new browser tab.
2. Paste the function **Invoke URL** into the address bar.
3. Open the URL and verify the response.
4. Confirm that the function returns the expected greeting without requiring sign-in.

**Observation:** The HTTP endpoint responded successfully with the expected **Hello, world!** response.

### 📸 Screenshots
![Task 6 Screenshot 1](Screenshots/Screenshot%202026-08-25%20214953.png)

![Task 6 Screenshot 2](Screenshots/Screenshot%202026-08-25%20215342.png)

---

## Task 7 — Verify the function in the portal

**Steps:**
1. Open **Function App** in the Azure portal.
2. Select the Function App created for the practical.
3. In the **Functions** section, verify that **GetStatus** appears.
4. Confirm that its trigger type is **HTTP**.

**Observation:** The GetStatus function was visible in the Function App with an enabled HTTP trigger.

### 📸 Screenshots
![Task 7 Screenshot](Screenshots/Screenshot%202026-08-25%20215752.png)

---

## Task 8 — Verify monitoring connection

**Steps:**
1. Open the Function App in the Azure portal.
2. Go to **Application Insights** under Monitoring.
3. Verify that Application Insights is enabled.
4. Confirm that the connected Application Insights resource is displayed.

**Observation:** The Function App was connected to Application Insights for monitoring and diagnostics.

### 📸 Screenshots
![Task 8 Screenshot](Screenshots/Screenshot%202026-08-25%20220337.png)

---

## Task 9 — Restrict access to the function

**Steps:**
1. Open Cloud Shell and return to the function project folder.
2. Change the function authorization level from **anonymous** to **function** as specified in the lab.
3. Verify the updated authorization setting.
4. Redeploy the function and wait for deployment to complete.

**Observation:** The function authorization level was changed so that a function key is required for access.

### 📸 Screenshots
![Task 9 Screenshot 1](Screenshots/Screenshot%202026-08-25%20220527.png)

![Task 9 Screenshot 2](Screenshots/Screenshot%202026-08-25%20220724.png)

---

## Task 10 — Test restricted access

**Steps:**
1. Open the previously tested function URL without a key.
2. Verify that the request returns **401 Unauthorized**.
3. Open the Function App and select **GetStatus → Function Keys**.
4. Copy the default function key.
5. Add the key to the URL using `?code=` and test the endpoint again.
6. Verify that the function responds successfully after authorization.

**Observation:** Unauthenticated access was rejected, while access using the function key was successful.

### 📸 Screenshots
![Task 10 Screenshot 1](Screenshots/Screenshot%202026-08-25%20220915.png)

![Task 10 Screenshot 2](Screenshots/Screenshot%202026-08-25%20221131.png)

---

## Task 11 — Review invocation logs

**Steps:**
1. Open **Application Insights** connected to the Function App.
2. Open **Transaction search** under the Investigate section.
3. Set the required time range and search for function requests.
4. Review successful invocations and their execution details.

**Observation:** Application Insights was used to review successful function invocations and execution information.

### 📸 Screenshots
![Task 11 Screenshot 1](Screenshots/Screenshot%202026-08-25%20221606.png)

![Task 11 Screenshot 2](Screenshots/Screenshot%202026-08-25%20221617.png)

---

## Task 12 — Delete the resource group

**Steps:**
1. Open **Resource groups** in the Azure portal.
2. Select the resource group created for the practical.
3. Select **Delete resource group**.
4. Enter the resource group name for confirmation and select **Delete**.
5. Wait for the deletion notification.

### 📸 Screenshots
![Task 12 Screenshot 1](Screenshots/Screenshot%202026-08-25%20221710.png)

![Task 12 Screenshot 2](Screenshots/Screenshot%202026-08-25%20221733.png)

---

## Task 13 — Clean up Cloud Shell files

**Steps:**
1. Open Azure Cloud Shell.
2. Remove the function project folder created during the practical.
3. Verify that the cleanup is complete.

**Observation:** The Azure resources and Cloud Shell project files were cleaned up after completing the practical.

### 📸 Screenshot
![Task 13 Screenshot](Screenshots/Screenshot%202026-08-25%20222242.png)

### 4. Result
The simple website endpoint was successfully created using Azure Functions. The HTTP-triggered function was configured, deployed, tested, monitored using Application Insights, and protected using function-level authorization.

### 5. Conclusion
Azure Functions provides a serverless way to build and deploy HTTP endpoints without managing traditional servers. The practical demonstrated Function App configuration, function creation, deployment, endpoint testing, monitoring, access control and cleanup.
