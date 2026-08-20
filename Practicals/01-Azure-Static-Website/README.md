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

- Azure Blob Storage is an object storage service provided by Microsoft Azure.
- It is used to store unstructured data such as HTML files, images, documents, videos and other files.
- Data is stored as blobs inside containers.
- A Storage Account provides the storage environment required for storing and accessing these files.
- In this practical, Blob Storage is used to host the files of a static website.

### Static Website Hosting

- Azure Blob Storage can host a static website without managing a traditional web server.
- A static website mainly contains client-side files such as HTML, CSS, JavaScript and images.
- When static website hosting is enabled, Azure creates a special container named `$web`.
- The website files are uploaded to the `$web` container.
- Azure provides a Primary Endpoint through which the website can be opened in a browser.

### Important Files / Terms

| File / Term | Purpose |
|---|---|
| `index.html` | Main/default webpage of the website. |
| `404.html` | Custom page displayed when a requested page is not found. |
| `$web` | Special container used to store static website files. |
| Primary Endpoint | URL provided by Azure to access the hosted website. |

---

## 3. Procedure / Main Tasks

The practical is divided into the following major activities so that each step can be performed and verified separately.

---

## Task 1 — Prepare the Azure Environment

### Steps

1. Sign in to the Azure portal using the credentials provided by the lab environment.
2. Open **Resource groups** from the Azure portal.
3. Select **+ Create** to create a new resource group.
4. Enter the resource group name as `rg-gp-static-website`.
5. Select the required region and create the resource group.
6. Open the created resource group and verify that it is available.

**Theory / Observation:** The resource group is used to keep the resources created for this practical together. It also makes it easier to remove all the lab resources at the end.

---

## Task 2 — Create the Storage Account

### Steps

1. Open **Storage accounts** from the Azure portal.
2. Select **+ Create**.
3. Select `rg-gp-static-website` as the resource group.
4. Enter the storage account name assigned by the lab.
5. Choose the required region.
6. Select the required storage configuration shown in the lab, such as Standard performance and LRS redundancy.
7. Select **Review + create** and then **Create**.
8. After deployment is completed, select **Go to resource**.

**Theory / Observation:** The Storage Account provides the storage environment in which the static website files are stored and served.

---

## Task 3 — Enable Static Website Hosting

### Steps

1. Open the created Storage Account.
2. From the left menu, go to **Data management → Static website**.
3. Set **Static website** to **Enabled**.
4. Enter `index.html` as the **Index document name**.
5. Enter `404.html` as the **Error document path**.
6. Select **Save**.
7. Note the **Primary endpoint** displayed by Azure.

**Theory / Observation:** After enabling static website hosting, Azure creates the `$web` container automatically and provides a Primary Endpoint for accessing the website.

---

## Task 4 — Create the Website File Locally

### Steps

1. Open a text editor such as Notepad on the local computer.
2. Create the main webpage using the HTML content given in the lab.
3. Save the file with the exact name `index.html`.
4. Keep the file ready for uploading to Azure.

**Theory / Observation:** `index.html` is the default document of the static website. It is displayed when the Primary Endpoint is opened.

---

## Task 5 — Upload `index.html` to the `$web` Container

### Steps

1. Return to the Azure portal and open the Storage Account.
2. Under **Data storage**, select **Containers**.
3. Open the `$web` container.
4. Select **Upload**.
5. Browse and select the `index.html` file.
6. Upload the file.
7. Verify that `index.html` appears in the `$web` container.

**Theory / Observation:** The `$web` container stores the files that make up the static website. Azure serves these files through the Primary Endpoint.

---

## Task 6 — Create and Upload the Custom 404 Page

### Steps

1. Create the custom error webpage in the text editor.
2. Use the required heading such as **404 - Page Not Found**.
3. Save the file exactly as `404.html`.
4. Open the `$web` container in Azure.
5. Select **Upload** and choose `404.html`.
6. Verify that both `index.html` and `404.html` are present.

**Theory / Observation:** The `404.html` file is used as the custom error document when a requested webpage or file does not exist.

---

## Task 7 — Verify the Website and 404 Page

### Steps

1. Open **Data management → Static website** in the Storage Account.
2. Open the **Primary endpoint**.
3. Verify that the main landing page is displayed.
4. Add a non-existing path such as `/fakepage` to the website URL.
5. Press **Enter** and verify that the custom **404 - Page Not Found** page is displayed.
6. Use the home-page link, if provided, and verify that it returns to the main page.

**Theory / Observation:** This verifies both normal website access and custom error handling through the Azure static website endpoint.

---

## Task 8 — Update the Website Content

### Steps

1. Open the existing `index.html` file in the text editor.
2. Replace the old content with the updated Version 2 content given in the lab.
3. Save the file as `index.html`.
4. Open the `$web` container in Azure.
5. Select **Upload** and choose the updated `index.html`.
6. Enable **Overwrite** if the file already exists.
7. Upload the updated file.
8. Open the Primary Endpoint and refresh the page.
9. Verify that the updated Version 2 landing page is displayed.

**Theory / Observation:** When the same blob is uploaded again with overwrite enabled, the previous version is replaced. The website then serves the updated content through the same Primary Endpoint.

---

## Task 9 — Review Blob Properties and Access Tier

### Steps

1. Open the `$web` container.
2. Select `index.html` to open its properties.
3. On the Overview tab, review the **Blob URL, Access tier and Content type**.
4. Verify the access tier and content type required by the lab, such as **Hot** and `text/html`.
5. Select **Edit** to review the stored HTML content if required.
6. Cancel without making unnecessary changes.
7. Review the properties of `404.html` in the same way.

**Theory / Observation:** Blob properties show how the website files are stored and served. For HTML website files, the Content type should be `text/html`. The Hot access tier is suitable when the content is accessed frequently.

---

## Task 10 — Delete the Resource Group and Verify Cleanup

### Steps

1. Open **Resource groups** from the Azure portal.
2. Select `rg-gp-static-website`.
3. Select **Delete resource group**.
4. Enter the resource group name in the confirmation box.
5. Select **Delete** and confirm the deletion.
6. Wait for the deletion notification.
7. Search Resource groups again and verify that `rg-gp-static-website` is no longer available.
8. Optionally try the old Primary Endpoint and verify that the website is no longer accessible.

**Theory / Observation:** Deleting the resource group removes the resources created inside it. Cleanup is important after an Azure lab so that unused resources do not continue to consume Azure resources or cause unnecessary charges.

---

## 4. Result

The static website was successfully deployed using Azure Blob Storage. The `index.html` page was hosted through the Primary Endpoint, the custom `404.html` page was tested, the website content was updated, and the blob properties were reviewed. The resource group was then deleted to complete the cleanup.

## 5. Conclusion

- Azure Static Website Hosting provides a simple method for publishing HTML-based websites.
- The `$web` container stores the website files and the Primary Endpoint provides access to the website.
- A custom 404 page improves the user experience when a requested page is unavailable.
- Website content can be updated by replacing the corresponding blob in the `$web` container.
- Deleting the resource group after the practical completes the lab cleanup.

---

## Screenshots

The original screenshots are kept in the parent `Practicals` folder with their original names. They have not been moved, renamed or deleted.
