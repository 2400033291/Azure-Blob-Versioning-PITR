# Architecture Diagram and Explanation.
![Azure Blob Versioning and Point-in-Time Restore Architecture](architecture-diagram.png)
## Architecture Explanation

The architecture represents a cloud-based data protection solution implemented using Microsoft Azure Blob Storage. The solution is designed to protect important blob data from accidental overwriting, modification, and deletion.

### 1. User

The user interacts with the Azure Storage resources through the Azure Portal. The user can upload, modify, view, and recover blob data.

### 2. Resource Group

The Resource Group `rg-blob-restore-project` is used to organize and manage all Azure resources related to the project.

### 3. Storage Account

The Storage Account `blobrestoreproject2026` provides the storage infrastructure for the project. Azure Blob Storage is used to store the project data.

### 4. Blob Container

The `project-data` container organizes the blobs stored inside the storage account.

### 5. Blob

The project uses `travel-data.txt` as the sample blob. Different versions of this file are maintained when changes are made.

### 6. Data Protection Features

The project uses four main data protection features:

- **Blob Versioning:** Maintains previous versions of a blob when the blob is modified or overwritten.
- **Blob Soft Delete:** Protects individual blobs from accidental deletion during the configured retention period.
- **Container Soft Delete:** Provides protection against accidental deletion of containers.
- **Change Feed:** Records changes made to blobs and supports point-in-time recovery capabilities.

### 7. Point-in-Time Restore

Point-in-Time Restore is configured with a **30-day recovery window**. It provides the capability to restore supported blob data to an earlier point in time.

### 8. Data Recovery

The recovery process allows previously stored data to be recovered after an accidental change or overwrite. In the project demonstration, an accidentally overwritten blob was recovered by making the required previous blob version current.

### 9. Lifecycle Management

Lifecycle Management is used to manage older blob versions. It helps control unnecessary storage consumption and addresses the storage-cost issue caused by accumulation of old versions.

## Overall Data Flow

The overall flow of the architecture is:

**User → Resource Group → Storage Account → Blob Container → Blob → Data Protection Features → Recovery**

The protection features work together to provide data durability and recovery capabilities, while Lifecycle Management helps manage storage usage and cost.
## Architecture Components
