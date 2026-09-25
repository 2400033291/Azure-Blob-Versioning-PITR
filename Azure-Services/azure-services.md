# Azure Services Required to Implement the Project

The Azure Blob Versioning and Point-in-Time Restore project uses the following Microsoft Azure services and features to provide secure data storage, version management, recovery, and storage optimization.

## 1. Azure Storage Account

The Azure Storage Account provides the main storage infrastructure for the project. It contains the blob container and stores the project data.

**Resource Used:** `blobrestoreproject2026`

## 2. Azure Blob Storage

Azure Blob Storage is used to store unstructured data such as text files. In this project, it is used to store the travel data file.

## 3. Blob Container

A blob container is used to organize blobs inside the storage account.

**Container Used:** `project-data`

## 4. Blob Versioning

Blob Versioning automatically maintains previous versions of a blob when its contents are modified or overwritten. It allows an earlier version of the data to be recovered.

## 5. Blob Soft Delete

Blob Soft Delete protects individual blobs from accidental deletion. Deleted blobs can be recovered during the configured retention period.

**Configured Retention:** 31 days

## 6. Container Soft Delete

Container Soft Delete protects containers from accidental deletion and allows recovery during the configured retention period.

**Configured Retention:** 31 days

## 7. Blob Change Feed

Blob Change Feed records changes made to blobs. It provides a log of blob changes and supports data recovery and auditing scenarios.

## 8. Point-in-Time Restore

Point-in-Time Restore provides the capability to restore supported blob data to an earlier point in time.

**Configured Recovery Window:** 30 days

## 9. Azure Storage Lifecycle Management

Lifecycle Management is used to automatically manage older blob versions based on defined rules.

In this project, a lifecycle rule is configured to manage older blob versions after a specified period. This helps control unnecessary storage consumption.

## Overall Service Flow

The main Azure service flow is:

**Azure Storage Account → Blob Container → Blob Storage → Data Protection Features → Data Recovery**

The combination of these Azure services provides protection against accidental modification, overwriting, and deletion while supporting recovery and storage management.
