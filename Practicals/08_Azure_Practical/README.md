# Azure Practical No. 08

## Manage Azure Resources with Cloud Shell and the Azure CLI

### 1. Aim
To manage Azure resources using Cloud Shell and Azure CLI, create and list resources, apply tags, and query resource information.

### 2. Theory
- **Azure Cloud Shell:** Browser-based command-line environment for managing Azure resources.
- **Azure CLI:** Command-line tool used to create, manage, list, and update Azure resources.
- **Resource Tags:** Key-value pairs used to organize and identify resources.
- **JMESPath:** Used with Azure CLI to filter and reshape JSON output.

### 3. Procedure / Main Tasks

### Task 1 — Create a resource group
1. Open Azure Cloud Shell and select Bash if required.
2. Run the command to create `rg-gp-cli-demo` in the required region.
3. Confirm `provisioningState` is **Succeeded**.
4. Verify the resource group with `az group show`.

**Observation:** The resource group was created and verified successfully.

![Task 1](./screenshots/Screenshot%202026-08-26%20183153.png)

### Task 2 — Create a storage account
1. Run `az storage account create` inside `rg-gp-cli-demo`.
2. Provide a unique name, region, and required SKU.
3. Wait for provisioning to complete.

**Observation:** The storage account was created successfully using Azure CLI.

![Task 2](./screenshots/Screenshot%202026-08-26%20183358.png)

### Task 3 — Create a second storage account
1. Run the storage-account creation command with a different unique name.
2. Use the same resource group and required region/SKU.
3. Confirm provisioning is complete.

**Observation:** A second storage account was created successfully.

![Task 3](./screenshots/Screenshot%202026-08-26%20183515.png)

### Task 4 — List and filter resources
1. Run `az resource list --resource-group rg-gp-cli-demo`.
2. Confirm both storage accounts are displayed.
3. Use the CLI filter to list only storage accounts.
4. Review the table output.

**Observation:** Resources were listed and filtered successfully.

![Task 4](./screenshots/Screenshot%202026-08-26%20183612.png)

### Task 5 — Tag the resource group
1. Use `az group update` to add the required tags.
2. Run `az group show --query tags` to verify them.
3. Confirm the required key-value pairs.

**Observation:** The resource group was tagged successfully.

![Task 5](./screenshots/Screenshot%202026-08-26%20183916.png)

### Task 6 — Tag individual resources
1. Use `az resource tag` to tag the first storage account.
2. Repeat for the second storage account with the required values.
3. Verify the tags on the individual resources.

**Observation:** Tags were applied to the storage accounts individually.

![Task 6](./screenshots/Screenshot%202026-08-26%20184030.png)

### Task 7 — Query resources with JMESPath filters
1. Use `az resource list` with the `--query` parameter.
2. Select the required resource names and tag values.
3. Apply the required filter.
4. Review the filtered output.

**Observation:** JMESPath was used to filter and format resource information.

![Task 7](./screenshots/Screenshot%202026-08-26%20184233.png)

### Task 8 — Compare CLI output to the portal
1. Open **Resource groups** in the Azure portal.
2. Select `rg-gp-cli-demo`.
3. Confirm the same storage accounts are shown.
4. Open **Tags** and verify the tag values.

**Observation:** The portal and CLI showed consistent resource and tag information.

![Task 8](./screenshots/Screenshot%202026-08-26%20184526.png)

**Note:** Resource-group deletion/cleanup is not repeated here because it was already documented in the earlier Azure practicals.

### 4. Result
Azure resources were successfully created and managed using Cloud Shell and Azure CLI. Resource listing, tagging, filtering, and portal verification were completed successfully.

### 5. Conclusion
This practical demonstrated how Azure CLI simplifies resource management and automation. Tags and JMESPath queries helped organize and retrieve resource information efficiently.