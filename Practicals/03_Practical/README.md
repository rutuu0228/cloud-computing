# Azure Practical No. 03

## Build a Simple Website Endpoint with Azure Functions

### 1. Aim
To create, deploy and test a simple HTTP-triggered website endpoint using Azure Functions, monitor its execution and apply access control.

### 2. Theory

#### Azure Functions
- Azure Functions is a serverless service used to run code without managing servers.
- It supports event-driven functions such as HTTP triggers.

#### Function App
- A Function App provides the environment for hosting and running functions.

#### HTTP Trigger
- An HTTP trigger runs a function when an HTTP request is received and provides an endpoint URL.

#### Application Insights
- Application Insights helps monitor function requests and execution details.

### 3. Procedure / Main Tasks

## Task 1 — Create the resource group

**Steps:**
1. Sign in to the Azure portal and open **Resource groups**.
2. Select **Create**.
3. Enter the required resource group name and region, then create it.

**Observation:** The resource group was created successfully.

### 📸 Screenshots
![Task 1 Screenshot](Screenshots/Screenshot%202026-08-25%20201044.png)

---

## Task 2 — Configure the Function App

**Steps:**
1. Select **Function App → Create** and choose **Flex Consumption**.
2. Select the resource group and enter the required Function App name.
3. Configure the region, **Node.js** runtime and required monitoring settings.
4. Select **Review + create**, then create the Function App.

**Observation:** The Function App was configured and deployed successfully.

### 📸 Screenshots
![Task 2 Screenshot 1](Screenshots/Screenshot%202026-08-25%20201232.png)

![Task 2 Screenshot 2](Screenshots/Screenshot%202026-08-25%20201436.png)

![Task 2 Screenshot 3](Screenshots/Screenshot%202026-08-25%20201509.png)

---

## Task 3 — Open Cloud Shell

**Steps:**
1. Select the **Cloud Shell** icon in the Azure portal.
2. Select **Bash** and the required subscription.
3. Wait for the terminal to open and display the `$` prompt.

**Observation:** Azure Cloud Shell was opened successfully.

### 📸 Screenshots
![Task 3 Screenshot 1](Screenshots/Screenshot%202026-08-25%20202138.png)

![Task 3 Screenshot 2](Screenshots/Screenshot%202026-08-25%20202505.png)

---

## Task 4 — Create the function project

**Steps:**
1. Create and initialize the function project using the Node.js runtime.
2. Create the **GetStatus** HTTP-triggered function.
3. Verify that the project and function files are created.

**Observation:** The function project and HTTP-triggered function were created successfully.

### 📸 Screenshots
![Task 4 Screenshot 1](Screenshots/Screenshot%202026-08-25%20202810.png)

![Task 4 Screenshot 2](Screenshots/Screenshot%202026-08-25%20202957.png)

---

## Task 5 — Deploy the function to Azure

**Steps:**
1. Find the Function App name using Azure CLI.
2. Publish the function project to the Function App.
3. Wait for deployment and copy the **Invoke URL**.

**Observation:** The GetStatus function was deployed successfully and an Invoke URL was provided.

### 📸 Screenshots
![Task 5 Screenshot](Screenshots/Screenshot%202026-08-25%20203609.png)

---

## Task 6 — Test the HTTP endpoint in a browser

**Steps:**
1. Open a browser and enter the function **Invoke URL**.
2. Verify the response from the function.
3. Confirm that the expected **Hello, world!** response is displayed.

**Observation:** The HTTP endpoint responded successfully.

### 📸 Screenshots
![Task 6 Screenshot 1](Screenshots/Screenshot%202026-08-25%20214953.png)

![Task 6 Screenshot 2](Screenshots/Screenshot%202026-08-25%20215342.png)

---

## Task 7 — Verify the function in the portal

**Steps:**
1. Open the Function App and select **Functions**.
2. Verify that **GetStatus** is listed.
3. Confirm that its trigger type is **HTTP**.

**Observation:** The GetStatus function was available with an HTTP trigger.

### 📸 Screenshots
![Task 7 Screenshot](Screenshots/Screenshot%202026-08-25%20215752.png)

---

## Task 8 — Verify monitoring connection

**Steps:**
1. Open the Function App and go to **Application Insights**.
2. Verify that Application Insights is enabled and connected.

**Observation:** Application Insights was connected for monitoring and diagnostics.

### 📸 Screenshots
![Task 8 Screenshot](Screenshots/Screenshot%202026-08-25%20220337.png)

---

## Task 9 — Restrict access to the function

**Steps:**
1. Open the function project in Cloud Shell.
2. Change the authorization level from **anonymous** to **function**.
3. Redeploy the function and verify the updated setting.

**Observation:** Function-level authorization was enabled, requiring a function key for access.

### 📸 Screenshots
![Task 9 Screenshot 1](Screenshots/Screenshot%202026-08-25%20220527.png)

![Task 9 Screenshot 2](Screenshots/Screenshot%202026-08-25%20220724.png)

---

## Task 10 — Test restricted access

**Steps:**
1. Open the function URL without a key and verify **401 Unauthorized**.
2. Open **GetStatus → Function Keys** and copy the default key.
3. Add the key using `?code=` and test the endpoint again.

**Observation:** Unauthenticated access was rejected and authorized access using the function key was successful.

### 📸 Screenshots
![Task 10 Screenshot 1](Screenshots/Screenshot%202026-08-25%20220915.png)

![Task 10 Screenshot 2](Screenshots/Screenshot%202026-08-25%20221131.png)

---

## Task 11 — Review invocation logs

**Steps:**
1. Open the connected **Application Insights** resource.
2. Open **Transaction search** and search for function requests.
3. Review the invocation and execution details.

**Observation:** Function invocations were successfully reviewed using Application Insights.

### 📸 Screenshots
![Task 11 Screenshot 1](Screenshots/Screenshot%202026-08-25%20221606.png)

![Task 11 Screenshot 2](Screenshots/Screenshot%202026-08-25%20221617.png)

---

## Task 12 — Delete the resource group

**Steps:**
1. Open **Resource groups** and select the practical's resource group.
2. Select **Delete resource group**.
3. Confirm the resource group name and select **Delete**.

### 📸 Screenshots
![Task 12 Screenshot 1](Screenshots/Screenshot%202026-08-25%20221710.png)

![Task 12 Screenshot 2](Screenshots/Screenshot%202026-08-25%20221733.png)

---

## Task 13 — Clean up Cloud Shell files

**Steps:**
1. Open Azure Cloud Shell.
2. Remove the function project folder created during the practical.
3. Verify that the cleanup is complete.

**Observation:** The Azure resources and project files were cleaned up successfully.

### 📸 Screenshot
![Task 13 Screenshot](Screenshots/Screenshot%202026-08-25%20222242.png)

### 4. Result
The website endpoint was successfully created using Azure Functions, deployed and tested. Function-level access control and Application Insights monitoring were also configured and verified.

### 5. Conclusion
The practical demonstrated Function App configuration, HTTP function creation, deployment, endpoint testing, monitoring, access control and resource cleanup using Azure Functions.