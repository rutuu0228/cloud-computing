# Azure Practical No. 04

## Set up New Employee Access: Entra ID and RBAC

## 1. Aim

To set up a new employee's access using Microsoft Entra ID and Azure Role-Based Access Control (RBAC), and verify the assigned permissions at the resource-group scope.

## 2. Theory

### Microsoft Entra ID
- Microsoft Entra ID is Microsoft's cloud identity and access management service.
- It manages users, groups and identities used to access Azure resources.

### Azure RBAC
- Azure RBAC controls **who** can access Azure resources, **what** they can do, and **where** they can do it.
- The **Reader** role allows users to view resources but does not allow them to make changes.
- Assigning a role to a group allows all members of that group to inherit the assigned permissions.

## 3. Procedure / Main Tasks

### Task 1 — Prepare the environment

1. Sign in to the Azure portal with an account that can manage users and role assignments.
2. Open **Resource groups** and select **Create**.
3. Create the resource group `rg-gp-access-model` in the required region.
4. Review the settings and create the resource group.

**Observation:** The resource group was created successfully and provides the scope for the access-control practical.

**Screenshot:**

![Task 1 – Prepare the environment](./screenshots/Screenshot%202026-08-27%20212938.png)

---

### Task 2 — Create a test storage account

1. Open **Storage accounts** in the Azure portal.
2. Select **+ Create**.
3. Select the practical resource group and enter the required storage account name.
4. Keep the required default settings and select **Review + create**.
5. Select **Create** and wait for deployment to complete.

**Observation:** The storage account was created inside the resource group and provides a test resource for checking RBAC access.

**Screenshot:**

![Task 2 – Create a test storage account](./screenshots/Screenshot%202026-08-27%20213122.png)

---

### Task 3 — Create the security group

1. Open **Microsoft Entra ID** and select **Groups** under Manage.
2. Select **New group**.
3. Set **Group type** to **Security**.
4. Enter the required group name and description.
5. Select **Create**.

**Observation:** The security group was created and will be used to manage RBAC permissions for its members.

**Screenshot:**

![Task 3 – Create the security group](./screenshots/Screenshot%202026-08-27%20213309.png)

---

### Task 4 — Create the user account

1. Open **Microsoft Entra ID → Users**.
2. Select **New user → Create new user**.
3. Enter the required user principal name and display name.
4. Review the settings and create the user.
5. Refresh the Users list to verify the account.

**Note:** In the lab environment, this task was **pre-created and could be skipped**. The steps were reviewed for understanding.

---

### Task 5 — Add the user to the group

1. In the Users list, select the required user.
2. Select **Edit** and then **Add to group**.
3. Search for the security group `gp-rg-readers64509061`.
4. Select the group and confirm the membership.

**Observation:** Adding the user to the group allows the user to inherit the permissions assigned to that group.

---

### Task 6 — Assign Reader role to the group

1. Open the practical resource group and select **Access control (IAM)**.
2. Select **Add → Add role assignment**.
3. On the Role tab, search for and select **Reader**.
4. On the Members tab, select **User, group, or service principal** and choose the security group.
5. Review the assignment and select **Review + assign**.

**Observation:** The Reader role was assigned to the security group at the resource-group scope.

**Screenshots:**

![Task 6 – Assign Reader role](./screenshots/Screenshot%202026-08-27%20213601.png)

![Task 6 – Select group](./screenshots/Screenshot%202026-08-27%20213723.png)

---

### Task 7 — Check access with IAM

1. Open **Access control (IAM)** for the resource group.
2. Select **Check access**.
3. Search for the user account created for the practical.
4. Review the displayed role assignments.
5. Confirm that the **Reader** role is inherited from the security group.

**Observation:** IAM showed that the user receives Reader permissions through group membership.

---

### Task 8 — Review the role assignment in the Activity Log

1. Open the practical resource group.
2. Select **Activity log**.
3. Find the entry with the operation name **Create role assignment**.
4. Open the entry and review the event details and initiating account.

**Observation:** The Activity Log provided an audit record of the RBAC role assignment.

**Screenshot:**

![Task 8 – Review role assignment in Activity Log](./screenshots/Screenshot%202026-08-27%20214308.png)

---

### Task 9 — Enable Temporary Access Pass

1. Open Microsoft Entra ID and review the Temporary Access Pass settings.
2. Follow the lab steps only if the feature is not already enabled.

**Note:** In the lab environment, Temporary Access Pass was already enabled, so this task was **skipped**.

---

### Task 10 — Generate a Temporary Access Pass for Alex

1. Open the user account settings and review the Temporary Access Pass option.
2. Generate a pass only if it has not already been created.

**Note:** The lab environment had the required pass pre-created, so this task was **skipped**.

---

### Task 11 — Sign in as Alex and test permissions

1. Use the provided Alex account and Temporary Access Pass when required.
2. Sign in to the Azure portal.
3. Check whether the user can view the assigned resources.
4. Verify that the Reader permissions do not allow resource modification or deletion.

**Note:** This task was reviewed from the lab instructions; no separate screenshot was captured for this step.

---

### Task 12 — Delete the resource group

1. Open **Resource groups** in the Azure portal.
2. Select `rg-gp-access-model`.
3. Select **Delete resource group**.
4. Enter the resource group name for confirmation.
5. Select **Delete** and wait for the deletion to complete.

**Observation:** The test resource group and its resources were removed after completing the practical.

**Screenshot:**

![Task 12 – Delete the resource group](./screenshots/Screenshot%202026-08-27%20214615.png)

---

### Task 13 — Disable Temporary Access Pass and verify cleanup

1. If Temporary Access Pass was enabled only for the practical, disable it as instructed by the lab.
2. Verify that the resource group and test resources have been removed.
3. Confirm that no practical resources remain.

**Note:** Cleanup steps were reviewed according to the lab instructions. Tasks that were already enabled, pre-created, or not required in the lab environment were not repeated.

## 4. Result

The employee access model was successfully configured using Microsoft Entra ID and Azure RBAC. A security group was created, the user was associated with the group, the Reader role was assigned at resource-group scope, and the permissions and audit trail were verified.

## 5. Conclusion

This practical demonstrated how Microsoft Entra ID and Azure RBAC can be used together to provide controlled and least-privilege access to Azure resources through group-based role assignment.
