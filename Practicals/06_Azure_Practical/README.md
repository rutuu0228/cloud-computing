# Azure Practical No. 06

## Set Up Cost Guardrails in Azure

### 1. Aim

To configure Azure cost guardrails using **budgets, alerts, cost-tracking tags, and Azure Policy** to monitor spending and control resource creation.

---

## 2. Theory

### Azure Cost Management
- Azure Cost Management helps monitor, analyze, and control cloud spending.
- **Budgets** define a spending limit for a selected scope and time period.
- **Alerts** notify users when actual or forecasted costs reach configured thresholds.
- **Cost-tracking tags** help identify resources and organize their costs for analysis.

### Azure Policy
- Azure Policy is used to enforce organizational rules on Azure resources.
- Policies can restrict resource creation based on conditions such as allowed locations.
- Policy assignments can be applied at a selected scope such as a resource group.

---

## 3. Procedure / Main Tasks

### Task 1 — Open Cost Management and start the budget

**Steps:**
1. Sign in to the Azure portal.
2. Search for **Cost Management** and open **Cost Management + Billing**.
3. Under **Monitoring**, select **Budgets**.
4. Select **+ Add** to start creating a budget.
5. Check that the required scope is selected before continuing.

**Observation:** The Cost Management budget creation page was opened successfully.

![Task 1 — Open Cost Management and start the budget](./screenshots/Screenshot%202026-08-28%20222331.png)

---

### Task 2 — Configure and create the budget

**Steps:**
1. Enter **gp-pilot-budget** as the budget name.
2. Select **Monthly** as the reset period.
3. Enter the required test budget amount.
4. Select **Next** to configure the alert conditions.
5. Set the required actual-cost thresholds.
6. Enter the required alert recipient.
7. Review the configuration and select **Create**.
8. Verify that the budget appears in the Budgets list.

**Observation:** The budget was created with the required amount, monthly reset period, and alert thresholds.

![Task 2 — Configure and create the budget](./screenshots/Screenshot%202026-08-28%20222849.png)

---

### Task 3 — Find and assign the policy

**Steps:**
1. Search for **Policy** in the Azure portal.
2. Under **Authoring**, select **Definitions**.
3. Search for the **Allowed locations** policy.
4. Open the policy and select **Assign**.
5. Set the assignment scope to **rg-gp-cost-guardrails**.
6. Open the **Parameters** tab.
7. Select the permitted region.
8. Select **Review + create**, check the assignment, and select **Create**.

**Observation:** The **Allowed locations** policy was assigned to the resource group with the permitted region configured.

![Task 3 — Find and assign the policy](./screenshots/Screenshot%202026-08-28%20223126.png)

---

### Task 4 — Validate policy enforcement

**Steps:**
1. Open **Storage accounts** and select **+ Create**.
2. Select **rg-gp-cost-guardrails** as the resource group.
3. Enter a temporary storage account name.
4. Select a region that is **not allowed** by the policy.
5. Select **Review + create** and check the validation result.
6. Confirm that creation is denied because of the policy restriction.
7. Change the region to the allowed location.
8. Verify that the validation passes for the permitted region.

**Observation:** Azure Policy prevented resource creation in the disallowed region and allowed it in the permitted region.

> **Note:** The available captures for this task were instruction/validation screens, so no screenshot is included here.

---

### Task 5 — Review policy compliance

**Steps:**
1. Search for **Policy** in the Azure portal.
2. Select **Compliance** from the left menu.
3. Find the **Allowed locations** policy assignment.
4. Open the assignment to view its compliance information.
5. Review the resources evaluated by the policy.
6. Confirm the compliance status for resources in the allowed region.

**Observation:** The Policy Compliance dashboard was used to review the enforcement status of the **Allowed locations** policy.

> **Note:** No screenshot is included because the available capture was an instruction screen rather than practical evidence.

---

### Task 6 — Cleanup

**Steps:**
1. Remove the budget and policy assignment created for the practical.
2. Delete the lab resource group after completing the required checks.
3. Confirm that the temporary resources are removed.

**Observation:** The resources created for the practical were cleaned up after completion.

---

## 4. Result

The Azure budget and alert thresholds were configured successfully. The **Allowed locations** policy was assigned to the resource group and tested to control resource creation according to the permitted region.

## 5. Conclusion

This practical demonstrated how **Azure Cost Management and Azure Policy** can work together to monitor cloud spending, configure cost alerts, and enforce resource-governance rules.
