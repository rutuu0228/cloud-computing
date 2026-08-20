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

## Task 1 — Prepare the Azure Environment

### Steps

1. Sign in to the Azure portal using the credentials provided by the lab environment.
2. Open **Resource groups** from the Azure portal.
3. Select **+ Create** to create a new resource group.
4. Enter the resource group name as `rg-gp-static-website`.
5. Select the required region and create the resource group.
6. Open the created resource group and verify that it is available.

**Theory / Observation:** The resource group keeps the resources created for this practical together and makes cleanup easier.

### 📸 Screenshot Evidence

![Azure Environment](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20203500.png)

![Resource Group](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20203636.png)

---

## Task 2 — Create the Storage Account

### Steps

1. Open **Storage accounts** from the Azure portal.
2. Select **+ Create**.
3. Select `rg-gp-static-website` as the resource group.
4. Enter the storage account name assigned by the lab.
5. Choose the required region and storage configuration.
6. Select **Review + create** and then **Create**.
7. After deployment, select **Go to resource**.

**Theory / Observation:** The Storage Account provides the Azure storage environment in which the static website files are stored and served.

### 📸 Screenshot Evidence

![Storage Account](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20203809.png)

![Storage Account Configuration](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20203950.png)

![Storage Account Created](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20204037.png)

---

## Task 3 — Enable Static Website Hosting

### Steps

1. Open the created Storage Account.
2. Go to **Data management → Static website**.
3. Set **Static website** to **Enabled**.
4. Enter `index.html` as the **Index document name**.
5. Enter `404.html` as the **Error document path**.
6. Select **Save**.
7. Note the **Primary endpoint** displayed by Azure.

**Theory / Observation:** After static website hosting is enabled, Azure creates the `$web` container automatically and provides a Primary Endpoint.

### 📸 Screenshot Evidence

![Static Website Settings](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20204117.png)

![Static Website Enabled](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20204137.png)

![Primary Endpoint](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20205700.png)

![Static Website Configuration](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20205734.png)

---

## Task 4 — Create and Upload Website Files

### Steps

1. Create the main webpage and save it as `index.html`.
2. Create the custom error page and save it as `404.html`.
3. Open **Storage Account → Containers → `$web`**.
4. Select **Upload** and upload `index.html`.
5. Upload `404.html` in the same way.
6. Verify that the website files are present in the `$web` container.

**Theory / Observation:** The `$web` container stores the files that make up the static website. Azure serves these files through the Primary Endpoint.

### 📸 Screenshot Evidence

![Website Files](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20205853.png)

![Web Container](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20205932.png)

![Upload Website Files](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20210232.png)

![Uploaded Files](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20210431.png)

![Web Container Files](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20210528.png)

![Website File Details](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20210602.png)

---

## Task 5 — Verify the Website and Test 404 Page

### Steps

1. Open **Data management → Static website** in the Storage Account.
2. Open the **Primary endpoint**.
3. Verify that the `index.html` webpage is displayed.
4. Enter a URL/path for a page that does not exist.
5. Verify that the configured `404.html` page is displayed.
6. Return to the main page and verify that the website is working correctly.

**Observation:** The website is accessible through the Azure static website endpoint and the custom error page is displayed for a missing resource.

### 📸 Screenshot Evidence

![Primary Endpoint](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20210701.png)

![Website Running](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20210838.png)

![Website Verification](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20210924.png)

![404 Page Test](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20211115.png)

![404 Error Page](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20211408.png)

---

## Task 6 — Update Website Content

### Steps

1. Open the existing `index.html` file in the text editor.
2. Modify the content as required and save the file.
3. Open the `$web` container in Azure.
4. Upload the updated `index.html`.
5. Enable **Overwrite** if the file already exists.
6. Refresh the Primary Endpoint.
7. Verify that the updated content is displayed.

**Theory / Observation:** Uploading the updated blob with overwrite enabled replaces the previous content, so the live website displays the new version.

### 📸 Screenshot Evidence

![Update Website](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20211614.png)

![Updated File](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20211654.png)

![Updated Website](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20211859.png)

![Updated Website Verification](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20212125.png)

---

## Task 7 — Review Blob Properties and Access Tier

### Steps

1. Open the `$web` container.
2. Select `index.html` to open its properties.
3. Review the **Blob URL, Access tier and Content type**.
4. Verify the required settings such as **Hot** access tier and `text/html` content type.
5. Review the properties of `404.html` if required.

**Theory / Observation:** Blob properties show how the website files are stored and served. HTML website files should have the `text/html` content type.

### 📸 Screenshot Evidence

![Blob Content](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20212733.png)

![Blob Properties](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20212805.png)

![Access Tier](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20212838.png)

![Content Type](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20213055.png)

---

## Task 8 — Delete the Resource Group and Verify Cleanup

### Steps

1. Open **Resource groups** from the Azure portal.
2. Select `rg-gp-static-website`.
3. Select **Delete resource group**.
4. Enter the resource group name in the confirmation box.
5. Select **Delete** and confirm the deletion.
6. Verify that the resource group and its lab resources have been removed.

**Theory / Observation:** Deleting the resource group removes the resources created for the practical and completes the lab cleanup.

### 📸 Screenshot Evidence

![Cleanup](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20213158.png)

![Delete Resource Group](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20213217.png)

![Deletion Confirmation](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20213419.png)

![Cleanup Verification](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20213637.png)

![Final Cleanup](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20213804.png)

![Final Verification](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20213822.png)

![Practical Completion](https://raw.githubusercontent.com/rutuu0228/cloud-computing/main/Practicals/Screenshot%202026-08-19%20214005.png)

---

## 4. Result

The static website was successfully deployed using Azure Blob Storage. The `index.html` page was hosted through the Primary Endpoint, the custom `404.html` page was tested, the website content was updated, and the blob properties were reviewed. The resource group was then deleted to complete the cleanup.

## 5. Conclusion

- Azure Static Website Hosting provides a simple method for publishing HTML-based websites.
- The `$web` container stores the website files and the Primary Endpoint provides access to the website.
- A custom 404 page improves the user experience when a requested page is unavailable.
- Website content can be updated by replacing the corresponding blob in the `$web` container.
- Deleting the resource group after the practical completes the lab cleanup.

> **Note:** All original screenshot files remain in the parent `Practicals` folder. They have not been moved, renamed or deleted. The README uses direct raw GitHub image URLs so the screenshots render inside the README itself.