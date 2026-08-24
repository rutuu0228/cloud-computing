# Azure Practical No. 02 — Organize and Protect Resources with Tags and Locks

**Subject:** Cloud Computing  
**Platform:** Microsoft Azure  
**Practical:** No. 02

---

## 1. Aim

To organize Azure resources using tags and protect them from accidental deletion by applying and testing resource locks.

## 2. Theory

### Azure Resource Tags

- Tags are name-value pairs used to organize and identify Azure resources.
- Tags help in resource management, filtering, organization and cost tracking.
- A tag consists of a **Name** and a corresponding **Value**.

### Azure Resource Locks

- Resource locks help prevent accidental modification or deletion of Azure resources.
- The two main lock types are **Read-only** and **Delete**.
- A **Delete** lock allows normal use of a resource but prevents its deletion until the lock is removed.

---

## 3. Procedure / Main Tasks

### Task 1 — Create resources and apply tags

**Steps:**

1. Sign in to the Azure portal using the provided lab environment.
2. Create or open the required resources specified in the lab.
3. Open the **Tags** section for the required resource.
4. Add the required tag **Name** and **Value** pairs.
5. Save the changes and verify that the tags are displayed.

**Observation:** Tags organize Azure resources using useful name-value information for identification and management.

**📸 Screenshots**

![Create resources](Screenshots./Screenshot%202026-08-24%20205054.png)

![Apply tags](Screenshots./Screenshot%202026-08-24%20205405.png)

![Tags applied](Screenshots./Screenshot%202026-08-24%20205825.png)

---

### Task 2 — Apply resource locks

**Steps:**

1. Open the required Azure resource or resource group.
2. Go to **Settings → Locks**.
3. Select **Add**.
4. Enter the required lock name.
5. Select the **Delete** lock type.
6. Create the lock and verify that it is listed for the resource.

**Observation:** A Delete lock protects the resource from accidental deletion while allowing normal operations.

**📸 Screenshots**

![Locks settings](Screenshots./Screenshot%202026-08-24%20210030.png)

![Add resource lock](Screenshots./Screenshot%202026-08-24%20210424.png)

![Delete lock applied](Screenshots./Screenshot%202026-08-24%20210853.png)

---

### Task 3 — Test lock enforcement

**Steps:**

1. Select the protected resource.
2. Attempt to delete the resource.
3. Verify that Azure prevents the deletion because the Delete lock is applied.
4. Return to **Settings → Locks**.
5. Remove the lock when instructed by the lab.
6. Verify that the lock has been removed.

**Observation:** The Delete lock prevents deletion until the lock is removed.

**📸 Screenshots**

![Delete attempt](Screenshots./Screenshot%202026-08-24%20211035.png)

![Deletion blocked](Screenshots./Screenshot%202026-08-24%20211436.png)

![Lock removal](Screenshots./Screenshot%202026-08-24%20211827.png)

---

### Task 4 — Validate success

**Steps:**

1. Verify that the required resources were created successfully.
2. Verify that the required tags are present.
3. Verify that the resource lock was created and tested successfully.
4. Confirm the success result shown by the lab.

**Observation:** The required resource organization and protection were configured and verified successfully.

**📸 Screenshots**

![Success validation](Screenshots./Screenshot%202026-08-24%20211536.png)

![Validation result](Screenshots./Screenshot%202026-08-24%20211752.png)

---

### Task 5 — Clean up resources

**Steps:**

1. Remove the Delete lock if it is still present and deletion is required.
2. Delete the resources created for the practical.
3. Delete the resource group when instructed.
4. Confirm that the resources have been removed.

**Observation:** Cleaning up the resources prevents unnecessary resource usage and possible charges after completing the practical.

**📸 Screenshots**

![Resource cleanup](Screenshots./Screenshot%202026-08-24%20212004.png)

![Resource deletion](Screenshots./Screenshot%202026-08-24%20212030.png)

![Cleanup completed](Screenshots./Screenshot%202026-08-24%20212234.png)

---

## 4. Result

Azure resources were successfully organized using tags and protected using a Delete lock. Lock enforcement was tested successfully and the resources were cleaned up.

## 5. Conclusion

Azure tags provide an effective method for organizing and tracking resources, while resource locks help protect resources from accidental deletion. Together, they improve Azure resource management and governance.

---

### Screenshot Evidence

The screenshots are stored in the **`Screenshots.`** folder of this practical and are placed directly after their corresponding tasks.