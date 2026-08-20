# Azure Practical No. 01
## Deploy a Static Website with Azure Blob Storage

**Subject:** Cloud Computing  
**Practical:** No. 01  
**Platform:** Microsoft Azure

---

## 1. Aim

To deploy and host a static website using Azure Blob Storage and verify its accessibility through the Azure Storage static website endpoint.

## 2. Theory

### Azure Blob Storage

- Azure Blob Storage is an object storage service in Microsoft Azure.
- It is used to store unstructured data such as HTML files, images, documents and videos.
- Data is stored as blobs inside containers.
- A Storage Account provides the storage environment required to store and access these files.

### Static Website Hosting

- Azure Blob Storage can host a static website without managing a traditional web server.
- A static website mainly contains client-side files such as HTML, CSS, JavaScript and images.
- After static website hosting is enabled, Azure creates a special `$web` container.
- Website files are uploaded to the `$web` container and accessed through the Primary Endpoint.

### Important Files / Terms

| File / Term | Purpose |
|---|---|
| `index.html` | Main/default webpage |
| `404.html` | Custom page displayed when requested content is not found |
| `$web` | Container used to store static website files |
| Primary Endpoint | URL used to access the hosted website |

---

# 3. Procedure / Main Tasks

## Task 1 — Create the Resource Group and Storage Account

### Steps

1. Sign in to the Azure portal using the lab credentials.
2. Open **Resource groups** and create the required resource group.
3. Open **Storage accounts** and select **+ Create**.
4. Select the resource group and enter the required Storage Account name.
5. Select the required region and storage settings given in the lab.
6. Select **Review + create → Create**.
7. After deployment, open the Storage Account.

**Observation:** The Storage Account provides the storage environment required to store and serve the website files.

---

## Task 2 — Enable Static Website Hosting

### Steps

1. Open the Storage Account.
2. Go to **Data management → Static website**.
3. Set **Static website** to **Enabled**.
4. Enter `index.html` as the **Index document name**.
5. Enter `404.html` as the **Error document path**.
6. Click **Save**.
7. Note the **Primary Endpoint** displayed by Azure.

**Observation:** Azure creates the `$web` container automatically and provides the Primary Endpoint for accessing the website.

---

## Task 3 — Create and Upload Website Files

### Steps

1. Create the main webpage in a text editor and save it as `index.html`.
2. Create the custom error page and save it as `404.html`.
3. In the Storage Account, open **Containers → `$web`**.
4. Select **Upload** and upload `index.html`.
5. Upload `404.html` in the same way.
6. Verify that both files are present in the `$web` container.

**Observation:** The `$web` container stores the files that make up the static website.

---

## Task 4 — Verify the Website and 404 Page

### Steps

1. Open the **Primary Endpoint** of the Storage Account.
2. Verify that the main webpage is displayed.
3. Enter a non-existing path such as `/fakepage` in the website URL.
4. Press **Enter** and verify that the custom `404.html` page is displayed.

**Observation:** The website is accessible through the Primary Endpoint and the configured error page is displayed for a missing resource.

---

## Task 5 — Update the Website Content

### Steps

1. Open the existing `index.html` file.
2. Modify the webpage content as required by the lab.
3. Save the updated file.
4. Open the `$web` container and upload the updated `index.html`.
5. Enable **Overwrite** if the file already exists.
6. Open the Primary Endpoint and refresh the page.
7. Verify that the updated content is displayed.

**Observation:** The updated file replaces the previous blob content and the changes are reflected on the live website.

---

## Task 6 — Review Properties and Complete Cleanup

### Steps

1. Open the `$web` container and select `index.html`.
2. Review its **Blob URL, Access tier and Content type**.
3. Verify the values required by the lab, such as **Hot** access tier and `text/html` content type.
4. After completing the practical, open **Resource groups**.
5. Select the practical's resource group and choose **Delete resource group**.
6. Confirm the deletion and verify that the resource group is removed.

**Observation:** Blob properties show how the website file is stored and served. Deleting the resource group completes the lab cleanup.

---

# 4. Result

The static website was successfully deployed using Azure Blob Storage. The website was accessed through the Primary Endpoint, the custom 404 page was verified, and the website content was updated successfully.

# 5. Conclusion

Azure Blob Storage provides a simple way to host static websites using a Storage Account, `$web` container and Primary Endpoint. The practical also demonstrated uploading, updating and verifying website files.

---

## Screenshots

The screenshots for this practical are kept in the parent `Practicals` folder, so no files need to be moved or renamed.