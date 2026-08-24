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
- Tags can help in resource management, filtering, organization and cost tracking.
- A tag consists of a **Name** and a corresponding **Value**.

### Azure Resource Locks

- Resource locks help prevent accidental modification or deletion of Azure resources.
- The main lock types are **Read-only** and **Delete**.
- A **Delete lock** allows normal use of a resource but prevents its deletion until the lock is removed.
- Locks can be applied at different scopes such as a resource, resource group or subscription.

---

## 3. Procedure / Main Tasks

### Task 1 — Create Resources and Apply Tags

**Steps:**

1. Sign in to the Azure portal using the provided lab environment.
2. Create/open the required resource group and resources specified in the lab.
3. Open the **Tags** section for the required resource.
4. Add the required tag **Name** and **Value** pairs.
5. Save the changes.
6. Verify that the tags are displayed on the resource.

**Observation:** Tags provide a simple way to organize Azure resources and associate them with useful information such as environment, department, owner or cost category.

**📸 Screenshot — Resource Creation / Tags**

![Resource and Tags](Screenshots./Screenshot%202026-08-24%20205054.png)

![Tag Configuration](Screenshots./Screenshot%202026-08-24%20205405.png)

![Tags Applied](Screenshots./Screenshot%202026-08-24%20205825.png)

---

### Task 2 — Apply a Resource Lock

**Steps:**

1. Open the required Azure resource or resource group.
2. Go to **Settings → Locks**.
3. Select **Add** to create a new resource lock.
4. Enter the required lock name.
5. Select the **Delete** lock type.
6. Add a suitable note if required and create the lock.
7. Verify that the lock is listed for the resource.

**Observation:** A Delete lock protects the resource from accidental deletion while allowing normal operations on the resource.

**📸 Screenshot — Locks Settings**

![Locks Settings](Screenshots./Screenshot%202026-08-24%20210030.png)

![Add Resource Lock](Screenshots./Screenshot%202026-08-24%20210424.png)

![Delete Lock Applied](Screenshots./Screenshot%202026-08-24%20210853.png)

---

### Task 3 — Test Lock Enforcement

**Steps:**

1. Select the protected resource or resource group.
2. Attempt to delete the resource.
3. Verify that Azure prevents the deletion because a Delete lock is applied.
4. Return to **Settings → Locks**.
5. Remove the lock when instructed by the lab.
6. Verify that the lock has been removed.

**Observation:** The Delete lock successfully blocks deletion. After removing the lock, the resource can be deleted normally.

**📸 Screenshot — Delete Attempt / Lock Enforcement**

![Lock Enforcement](Screenshots./Screenshot%202026-08-24%20211035.png)

![Deletion Blocked](Screenshots./Screenshot%202026-08-24%20211436.png)

![Lock Removal](Screenshots./Screenshot%202026-08-24%20211827.png)

---

### Task 4 — Validate the Practical

**Steps:**

1. Verify that the required resources were created successfully.
2. Verify that the required tags are present.
3. Verify that the resource lock was created and tested successfully.
4. Confirm the expected lab validation or success message.

**Observation:** The required resource organization and protection controls were successfully configured and verified.

**📸 Screenshot — Validation / Success**

![Validation](Screenshots./Screenshot%202026-08-24%20211536.png)

![Validation Result](Screenshots./Screenshot%202026-08-24%20211752.png)

---

### Task 5 — Clean Up Resources

**Steps:**

1. Remove the resource lock if it is still present and the lab requires deletion.
2. Delete the resources created for the practical.
3. Delete the resource group when instructed.
4. Confirm that the resources have been removed.

**Observation:** Cleaning up the resources prevents unnecessary resource usage and possible charges after completing the practical.

**📸 Screenshot — Resource Cleanup**

![Cleanup](Screenshots./Screenshot%202026-08-24%20212004.png)

![Resource Deletion](Screenshots./Screenshot%202026-08-24%20212030.png)

![Cleanup Completed](Screenshots./Screenshot%202026-08-24%20212234.png)

---

## 4. Result

Azure resources were successfully organized using tags and protected using a Delete lock. The lock enforcement was tested successfully, the lock was removed as required, and the resources were cleaned up.

## 5. Conclusion

Azure tags provide an effective method for organizing and tracking resources, while resource locks help protect important resources from accidental deletion. Together, they improve Azure resource management and governance.

---

### Screenshot Evidence

All Practical 02 screenshots are stored in the **`Screenshots.`** folder of this practical. The selected screenshots above are placed directly after the corresponding tasks as evidence of the completed lab activities.

**Source:** Microsoft Learn guided project — *Organize and protect resources with tags and locks*. The project covers creating resources and applying tags, applying resource locks, testing lock enforcement, validating success and cleaning up resources. citeturn1view0
