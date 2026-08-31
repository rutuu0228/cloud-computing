# Azure Practical No. 07

## Monitor Azure with Service Health and Activity Log Alerts

### 1. Aim

To configure Azure Service Health and Activity Log alerts and connect them with an action group for monitoring Azure platform issues and resource changes.

---

## 2. Theory

### Azure Service Health
- Azure Service Health provides information about Azure service issues, planned maintenance, and health advisories.
- **Service Health alerts** notify the operations team about events that may affect Azure resources.

### Azure Activity Log Alerts
- Activity Log records management operations performed on Azure resources.
- Activity Log alerts can notify users when selected operations, such as resource deletion, occur.

### Action Group
- An action group defines the notification method and recipients for an Azure alert.
- The same action group can be reused by multiple alert rules.

---

## 3. Procedure / Main Tasks

### Task 1 — Prepare the environment

**Steps:**
1. Sign in to the Azure portal using the lab account.
2. Search for **Resource groups** and select it.
3. Select **+ Create**.
4. Enter the resource group name **rg-gp-monitoring-alerts**.
5. Select the required region.
6. Select **Review + create** and then **Create**.
7. Note the email address to be used for alert notifications.

**Observation:** The resource group was created successfully for the monitoring resources.

![Task 1 — Prepare the environment](./Screenshtos/Screenshot%202026-08-31%20213029.png)

---

### Task 2 — Create the action group

**Steps:**
1. Search for **Monitor** and open it.
2. Select **Alerts** from the left menu.
3. Select **Action groups**.
4. Select **+ Create**.
5. Select **rg-gp-monitoring-alerts** as the resource group.
6. Enter **ag-gp-ops-email** as the action group name and **OpsEmail** as the display name.
7. Add the required email notification.
8. Review the configuration and select **Create**.
9. Test the action group if required and verify the notification configuration.

**Observation:** The action group was created successfully and configured to notify the operations team.

![Task 2 — Create the action group](./Screenshtos/Screenshot%202026-08-31%20213521.png)

![Task 2 — Test the action group](./Screenshtos/Screenshot%202026-08-31%20214038.png)

---

### Task 3 — Navigate to Service Health

**Steps:**
1. Search for **Service Health** in the Azure portal.
2. Open **Service Health**.
3. Select **Service issues** and review active incidents.
4. Select **Planned maintenance** and review upcoming maintenance.
5. Select **Health advisories** to review other Azure recommendations.

**Observation:** Service Health was reviewed to understand current incidents, planned maintenance, and health advisories.

![Task 3 — Navigate to Service Health](./Screenshtos/Screenshot%202026-08-31%20214207.png)

---

### Task 4 — Create the Service Health alert rule

**Steps:**
1. In Service Health, select **Health alerts** and choose **+ Create service health alert**.
2. Select the required subscription.
3. Keep all services selected or select the required services.
4. Set the region to **Global**.
5. Select **Service issue** and **Planned maintenance** as event types.
6. In **Actions**, select **ag-gp-ops-email**.
7. In **Details**, select **rg-gp-monitoring-alerts** as the resource group.
8. Enter **ar-gp-service-health** as the alert rule name.
9. Keep the alert enabled and select **Create**.

**Observation:** A Service Health alert was configured to notify the operations team about service issues and planned maintenance.

> **Note:** The available captures for this task were lab instruction screens, so no instruction screenshot is included here.

---

### Task 5 — Open the Activity Log alert creation page

**Steps:**
1. Search for **Monitor** and open it.
2. Select **Alerts**.
3. Select **+ Create** and then **Alert rule**.
4. Open the alert creation page for the Activity Log alert.

**Observation:** The Activity Log alert creation page was opened successfully.

---

### Task 6 — Configure the Activity Log alert condition

**Steps:**
1. For **Scope**, select **Select scope**.
2. Filter by resource type **Resource groups**.
3. Select **rg-gp-monitoring-alerts** and apply the scope.
4. Open the **Condition** tab.
5. For Signal name, select **Delete resource group**.
6. Set **Severity** to **Sev 2 - Warning**.
7. Keep the remaining signal settings as required by the lab.

**Observation:** The alert condition was configured to detect resource-group deletion events.

> **Note:** No practical screenshot is included because the available capture shows the lab instructions rather than the completed Azure configuration.

---

### Task 7 — Attach the action group and create the alert

**Steps:**
1. Open the **Actions** tab.
2. Select **Select action groups** and choose **ag-gp-ops-email**.
3. Open the **Details** tab.
4. Select **rg-gp-monitoring-alerts** as the resource group.
5. Enter **ar-gp-activity-delete** as the alert rule name.
6. Set **Severity** to **Sev 2 - Warning**.
7. Keep **Enable alert rule upon creation** selected.
8. Select **Review + create** and then **Create**.
9. Return to **Monitor → Alerts → Alert rules** and verify both alert rules.

**Observation:** The Activity Log alert was created and connected to the same action group.

> **Note:** No screenshot is included because the available capture is an instruction/validation screen.

---

### Task 8 — Review alert rule details

**Steps:**
1. In the alert rules list, open **ar-gp-service-health**.
2. Review the Condition section and confirm **Service issue** and **Planned maintenance** events.
3. Review the Actions section and confirm **ag-gp-ops-email**.
4. Return to the alert rules list.
5. Open **ar-gp-activity-delete**.
6. Review its condition, action group, severity, and enabled status.

**Observation:** Both alert rules were reviewed and their conditions, notification actions, and severity settings were verified.

---

### Task 9 — Cleanup

**Steps:**
1. Open **Monitor → Alerts → Alert rules**.
2. Delete **ar-gp-activity-delete** and **ar-gp-service-health**.
3. Delete the **ag-gp-ops-email** action group.
4. Open **Resource groups** and delete **rg-gp-monitoring-alerts**.
5. Confirm that the resource group and monitoring resources are removed.

**Observation:** The monitoring resources created for the practical were cleaned up successfully.

---

## 4. Result

The Azure Service Health and Activity Log alerts were configured successfully. An action group was created for notifications, and alerts were configured to monitor Azure service events and resource-group deletion activities.

## 5. Conclusion

This practical demonstrated how **Azure Service Health, Activity Log alerts, and Action Groups** can be used together to monitor Azure platform issues and important resource-management activities.
