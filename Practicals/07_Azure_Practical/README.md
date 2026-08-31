# Azure Practical No. 07

## Monitor Azure with Service Health and Activity Log Alerts

### 1. Aim

To configure Azure Service Health and Activity Log alerts and connect them with an action group for monitoring Azure issues and resource changes.

---

## 2. Theory

### Azure Service Health
- Provides information about Azure service issues, planned maintenance, and health advisories.
- Service Health alerts notify users about events that may affect Azure resources.

### Azure Activity Log Alerts
- Activity Log records management operations on Azure resources.
- Alerts can notify users when selected operations occur.

### Action Group
- Defines the notification method and recipients for an alert.
- The same action group can be used by multiple alerts.

---

## 3. Procedure / Main Tasks

### Task 1 — Prepare the environment

**Steps:**
1. Sign in to the Azure portal.
2. Open **Resource groups** and select **+ Create**.
3. Enter **rg-gp-monitoring-alerts** and select the required region.
4. Select **Review + create → Create**.
5. Note the email address to be used for notifications.

**Observation:** The resource group was created successfully for the monitoring resources.

![Task 1 — Prepare the environment](./Screenshtos/Screenshot%202026-08-31%20213029.png)

---

### Task 2 — Create the action group

**Steps:**
1. Open **Monitor → Alerts → Action groups**.
2. Select **+ Create** and choose **rg-gp-monitoring-alerts**.
3. Enter **ag-gp-ops-email** as the action group name and **OpsEmail** as the display name.
4. Add the required email notification.
5. Select **Review + create → Create**.
6. Test the action group if required.

**Observation:** The action group was created and configured for email notifications.

![Task 2 — Create the action group](./Screenshtos/Screenshot%202026-08-31%20213521.png)

![Task 2 — Test the action group](./Screenshtos/Screenshot%202026-08-31%20214038.png)

---

### Task 3 — Navigate to Service Health

**Steps:**
1. Search for and open **Service Health**.
2. Review **Service issues**.
3. Review **Planned maintenance**.
4. Review **Health advisories**.

**Observation:** Service Health was reviewed for incidents, maintenance, and advisories.

![Task 3 — Navigate to Service Health](./Screenshtos/Screenshot%202026-08-31%20214207.png)

---

### Task 4 — Create the Service Health alert rule

**Steps:**
1. In Service Health, select **Health alerts → + Create service health alert**.
2. Select the required subscription and region **Global**.
3. Select **Service issue** and **Planned maintenance** as event types.
4. Under Actions, select **ag-gp-ops-email**.
5. Select **rg-gp-monitoring-alerts** and enter **ar-gp-service-health**.
6. Keep the alert enabled and select **Create**.

**Observation:** A Service Health alert was configured for service issues and planned maintenance.

*No screenshot included because the available capture was an instruction screen.*

---

### Task 5 — Open the Activity Log alert creation page

**Steps:**
1. Open **Monitor → Alerts**.
2. Select **+ Create → Alert rule**.
3. Open the Activity Log alert creation page.

**Observation:** The Activity Log alert creation page was opened successfully.

---

### Task 6 — Configure the Activity Log alert condition

**Steps:**
1. Select **Select scope** and choose **rg-gp-monitoring-alerts**.
2. Open **Condition**.
3. Select **Delete resource group** as the signal.
4. Set **Severity** to **Sev 2 - Warning**.
5. Keep the remaining settings as required by the lab.

**Observation:** The condition was configured to detect resource-group deletion events.

*No screenshot included because the available capture showed the lab instructions.*

---

### Task 7 — Attach the action group and create the alert

**Steps:**
1. Open **Actions** and select **ag-gp-ops-email**.
2. Open **Details** and select **rg-gp-monitoring-alerts**.
3. Enter **ar-gp-activity-delete** as the alert rule name.
4. Set severity to **Sev 2 - Warning** and keep the alert enabled.
5. Select **Review + create → Create**.
6. Verify both alert rules under **Monitor → Alerts → Alert rules**.

**Observation:** The Activity Log alert was created and connected to the action group.

---

### Task 8 — Review alert rule details

**Steps:**
1. Open **ar-gp-service-health** and review its conditions and action group.
2. Open **ar-gp-activity-delete** and review its condition, severity, and action group.
3. Confirm that both alerts are enabled.

**Observation:** Both alert rules were reviewed successfully.

---

### Task 9 — Cleanup

**Steps:**
1. Delete **ar-gp-activity-delete** and **ar-gp-service-health**.
2. Delete **ag-gp-ops-email**.
3. Delete **rg-gp-monitoring-alerts** and confirm cleanup.

**Observation:** The monitoring resources were cleaned up successfully.

---

## 4. Result

Azure Service Health and Activity Log alerts were configured successfully with an action group for notifications.

## 5. Conclusion

This practical demonstrated how **Service Health, Activity Log alerts, and Action Groups** can be used to monitor Azure issues and important resource-management activities.
