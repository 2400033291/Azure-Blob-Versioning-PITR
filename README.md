# Azure Blob Versioning and Point-in-Time Restore

## Project Information

- **Project Title:** Azure Blob Versioning and Point-in-Time Restore
- **Project Number:** P054
- **Department:** CSE
- **Technology:** Microsoft Azure
- **Domain:** Cloud Data Protection

## Project Abstract

Azure Blob Versioning and Point-in-Time Restore is a cloud-based data protection solution implemented using Microsoft Azure Blob Storage.

The project addresses accidental data modification, overwriting, and deletion by maintaining previous versions of blob data and providing recovery mechanisms.

Blob Versioning is enabled to retain previous versions of data. Blob Soft Delete and Container Soft Delete provide protection against accidental deletion. Change Feed records changes made to blobs and supports point-in-time recovery.

Point-in-Time Restore is configured with a 30-day retention period to enable recovery of supported block blob data to an earlier state. Lifecycle Management is also configured to manage older blob versions and reduce unnecessary storage consumption.

The solution is demonstrated using a travel-data text file. An accidental overwrite is simulated and the original data is recovered using a previous blob version.

## Use Cases

- Recover from accidental blob overwrites
- Protect data from accidental deletion
- Maintain previous versions of blob data
- Provide a 30-day recovery window
- Manage older versions to control storage costs

## Key Azure Services

- Azure Storage Account
- Azure Blob Storage
- Blob Container
- Blob Versioning
- Blob Soft Delete
- Container Soft Delete
- Blob Change Feed
- Point-in-Time Restore
- Azure Storage Lifecycle Management

## Project Modules

1. Storage Account Management
2. Blob Container Management
3. Blob Versioning and Data Recovery
4. Data Protection Configuration
5. Point-in-Time Restore
6. Lifecycle Management
7. Recovery Demonstration

## Project Outcome

The project demonstrates how Azure Blob Storage can be configured to protect data from accidental overwrites and deletions while maintaining a recovery window and controlling storage growth.
