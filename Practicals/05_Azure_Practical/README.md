# Azure Practical No. 05

## Share Files Securely

### 1. Aim
To securely share a file from Azure Blob Storage using a stored access policy and a SAS token, verify controlled access, revoke the access, and configure lifecycle management.

### 2. Theory
**Azure Blob Storage**
- Blob Storage stores unstructured data such as text files and documents.
- A container is used to organize blobs.

**Stored Access Policy**
- Defines permissions and validity settings for shared access.
- A SAS can be generated from the stored policy for controlled access.

**SAS (Shared Access Signature)**
- Provides temporary, limited access to Azure Storage resources without exposing the storage account key.

**Lifecycle Management**
- Automatically moves or deletes blobs according to defined rules.

### 3. Procedure / Main Tasks

#### Task 1 — Prepare the environment
**Steps:**
1. Sign in to the Azure portal using the lab account.
2. Open Resource groups and create the required resource group.
3. Select the required region and create the resource group.

**Observation:** The resource group was created successfully and was ready for the storage resources.

![Task 1](Screenshots/Screenshot%202026-08-28%20192042.png)

#### Task 2 — Create the storage account
**Steps:**
1. Open **Storage accounts** and select **Create**.
2. Select the practical resource group.
3. Enter the required storage account name and region.
4. Keep the required settings and create the storage account.

**Observation:** The storage account was created successfully.

![Task 2](Screenshots/Screenshot%202026-08-28%20192238.png)

#### Task 3 — Create the private container
**Steps:**
1. Open the storage account and select **Containers**.
2. Select **+ Container**.
3. Enter the container name `partner-drop`.
4. Keep anonymous access disabled and create the container.

**Observation:** A private blob container was created to securely store the shared file.

![Task 3](Screenshots/Screenshot%202026-08-28%20192530.png)

#### Task 4 — Upload the report file
**Steps:**
1. Open the `partner-drop` container.
2. Select **Upload**.
3. Select the `monthly-report.txt` file.
4. Upload the file and verify that it appears in the container.

**Observation:** The report file was uploaded successfully.

![Task 4](Screenshots/Screenshot%202026-08-28%20192811.png)

#### Task 5 — Create a stored access policy
**Steps:**
1. Open the container and select **Access policy**.
2. Select **Add policy**.
3. Enter the required policy name.
4. Set the required permissions and expiry time.
5. Save the policy.

**Observation:** A stored access policy was created with controlled permissions and validity.

![Task 5](Screenshots/Screenshot%202026-08-28%20193230.png)

#### Task 6 — Generate a SAS from the stored access policy
**Steps:**
1. Open **Generate SAS** for the container.
2. Select the stored access policy.
3. Generate the SAS token and URL.
4. Copy the Blob SAS URL for testing.

**Observation:** A policy-based SAS URL was generated for secure temporary access.

![Task 6](Screenshots/Screenshot%202026-08-28%20193457.png)

#### Task 7 — Verify direct access is blocked
**Steps:**
1. Open an incognito browser window.
2. Open the blob URL without a SAS token.
3. Verify that direct anonymous access is denied.

**Observation:** The private container blocked unauthenticated direct access.

![Task 7](Screenshots/Screenshot%202026-08-28%20193818.png)

#### Task 8 — Test SAS access
**Steps:**
1. In the same incognito window, open the generated SAS URL.
2. Verify that the report content is displayed.
3. Confirm that access works without signing in.

**Observation:** The SAS token successfully provided controlled access to the private file.

![Task 8](Screenshots/Screenshot%202026-08-28%20194000.png)

#### Task 9 — Revoke SAS access
**Steps:**
1. Return to the container's **Access policy** settings.
2. Select the stored access policy.
3. Delete the policy and save the change.

**Observation:** Deleting the stored access policy revoked the policy-based SAS access.

![Task 9](Screenshots/Screenshot%202026-08-28%20194253.png)

#### Task 10 — Verify access is blocked
**Steps:**
1. Return to the existing SAS URL.
2. Refresh the page.
3. Verify that access is now denied.

**Observation:** The previously valid SAS URL no longer provided access after the policy was deleted.

![Task 10](Screenshots/Screenshot%202026-08-28%20194515.png)

#### Task 11 — Confirm the file still exists
**Steps:**
1. Open the storage account and `partner-drop` container.
2. Verify that `monthly-report.txt` is still present.
3. Confirm that revoking access did not delete the file.

**Observation:** The file remained in the private container after access was revoked.

![Task 11](Screenshots/Screenshot%202026-08-28%20194709.png)

#### Task 12 — Create a lifecycle management rule
**Steps:**
1. Open **Lifecycle management** under Data management.
2. Select **+ Add a rule**.
3. Enter the required rule name.
4. Set the blob scope to the `partner-drop` container.
5. Configure the required delete action and retention period.
6. Save the rule.

**Observation:** A lifecycle rule was configured to automatically delete shared files after the required period.

![Task 12](Screenshots/Screenshot%202026-08-28%20194828.png)

#### Task 13 — Review the rule configuration
**Steps:**
1. Open the lifecycle management rule.
2. Review the configured scope, conditions, and delete action.
3. Confirm that the rule targets only the intended files.

**Observation:** The lifecycle rule was reviewed and confirmed with the required configuration.

![Task 13](Screenshots/Screenshot%202026-08-28%20195019.png)

> **Cleanup:** Delete the resource group after completing the practical to remove the lab resources. No separate screenshot is included because cleanup was already documented in the earlier practicals.

### 4. Result
The file was securely shared using Azure Blob Storage, a stored access policy, and a SAS token. Access was tested, revoked successfully, and lifecycle management was configured.

### 5. Conclusion
This practical demonstrated secure temporary file sharing in Azure using private blob storage, policy-based SAS access, access revocation, and automated lifecycle management.
