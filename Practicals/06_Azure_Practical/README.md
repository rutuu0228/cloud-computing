# Azure Practical No. 06

## Set Up Cost Guardrails in Azure

### 1. Aim

To configure Azure cost guardrails using **budgets, alerts, cost-tracking tags, and Azure Policy** to monitor and control cloud spending.

---

## 2. Theory

### Azure Cost Management
- Azure Cost Management helps monitor and control cloud spending.
- **Budgets** set spending limits and provide alerts when costs reach defined thresholds.
- **Cost-tracking tags** help organize and identify resources for cost analysis.

### Azure Policy
- Azure Policy enforces organizational rules on Azure resources.
- It can prevent non-compliant resource creation, such as creating resources in disallowed regions.

---

## 3. Procedure / Main Tasks

### Task 1 — Open Cost Management and start the budget

**Steps:**
1. Sign in to the Azure portal.
2. Search for **Cost Management** and open **Cost Management + Billing**.
3. Under **Monitoring**, select **Budgets**.
4. Select **+ Add**.

**Observation:** The Cost Management budget creation page was opened successfully.

![Task 1 — Open Cost Management and start the budget](./screenshots/Screenshot%202026-08-28%20222331.png)

---

### Task 2 — Configure and create the budget

**Steps:**
1. Enter **gp-pilot-budget** as the budget name.
2. Select **Monthly** as the reset period.
3. Enter the required test amount.
4. Select **Next** and configure the alert thresholds.
5. Set the required actual-cost thresholds and alert recipient.
6. Select **Create**.

**Observation:** The budget was created with the required alert thresholds.

![Task 2 — Configure and create the budget](./screenshots/Screenshot%202026-08-28%20222849.png)

---

### Task 3 — Find and assign the policy

**Steps:**
1. Search for **Policy** in the Azure portal.
2. Under **Authoring**, select **Definitions**.
3. Search for the **Allowed locations** policy.
4. Select the policy and choose **Assign**.
5. Set the scope to **rg-gp-cost-guardrails**.
6. On the **Parameters** tab, select the permitted region.
7. Select **Review + create**, then **Create**.

**Observation:** The **Allowed locations** policy was assigned to the resource group with the permitted region configured.

![Task 3 — Find and assign the policy](./screenshots/Screenshot%202026-08-28%20223126.png)

---

### Task 4 — Validate policy enforcement

**Steps:**
1. Open **Storage accounts** and select **+ Create**.
2. Select **rg-gp-cost-guardrails** as the resource group.
3. Enter a temporary storage account name.
4. Select a region that is **not allowed** by the policy.
5. Select **Review + create**.
6. Confirm that creation is denied with a policy error.
7. Change the region to the allowed location and verify that validation passes.

**Observation:** Azure Policy prevented resource creation in the disallowed region and allowed it in the permitted region.

> **Note:** The screenshots for this task were instruction/validation captures only, so no screenshot is included in the practical.

---

### Task 5 — Review policy compliance

**Steps:**
1. Search for **Policy** in the Azure portal.
2. Select **Compliance** from the left menu.
3. Find the **Allowed locations** policy assignment.
4. Open it and review the compliance details.
5. Confirm that resources in the allowed region are shown as compliant.

**Observation:** The Policy Compliance dashboard was used to verify the enforcement status of the Allowed locations policy.

> **Note:** No separate screenshot is included because the available capture was an instruction screen rather than practical evidence.

---

## 4. Result

The Azure budget and alert thresholds were configured successfully, and an **Allowed locations** Azure Policy was assigned and validated to control resource creation by region.

## 5. Conclusion

This practical demonstrated how **Azure Cost Management and Azure Policy** can be used together to monitor spending and enforce organizational cost and resource-governance rules.

> **Cleanup:** The policy assignment, budget, and resource group should be removed after the practical as instructed by the lab. Cleanup screenshots are not repeated here because resource deletion was already documented in the earlier practicals.
