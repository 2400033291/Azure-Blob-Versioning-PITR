# Project Modules

## Project Title

Azure Blob Versioning and Point-in-Time Restore

## Project Number

P054

## Overview

The project is divided into multiple modules to provide secure blob storage, data protection, version management, recovery, and storage optimization.

## Module 1 – Storage Account Management

This module manages the Azure Storage Account used by the project.

**Resource Used:**

`blobrestoreproject2026`

The Storage Account provides the storage infrastructure required for Blob Storage and Azure Files.

### Main Functions

- Create and configure the Storage Account
- Configure storage performance
- Configure redundancy
- Manage storage services
- Provide access to blob and file storage

## Module 2 – Blob Container Management

This module manages the blob container used to organize project data.

**Container Used:**

`project-data`

### Main Functions

- Create a blob container
- Configure container access
- Store project blobs
- Manage blobs inside the container

## Module 3 – Blob Versioning and Data Recovery

This module provides protection against accidental modification and overwriting of blob data.

**Blob Used:**

`travel-data.txt`

Blob Versioning maintains previous versions whenever the blob content is modified.

### Main Functions

- Enable Blob Versioning
- Create and maintain previous blob versions
- View available versions
- Recover an earlier version
- Make a previous version the current version

## Module 4 – Data Protection Configuration

This module provides additional protection against accidental deletion and data changes.

The following features were configured:

- Blob Soft Delete
- Container Soft Delete
- Blob Versioning
- Blob Change Feed

### Main Functions

- Protect blobs from accidental deletion
- Protect containers from accidental deletion
- Maintain previous versions
- Record changes made to blobs

## Module 5 – Point-in-Time Restore

This module provides a recovery capability for supported blob data.

Point-in-Time Restore was configured with a:

**30-day recovery window**

### Main Functions

- Configure Point-in-Time Restore
- Maintain a recovery window
- Support recovery of supported blob data to an earlier point in time

The project configuration demonstrates the Point-in-Time Restore capability. The practical recovery demonstration was performed using Blob Versioning by restoring an earlier blob version.

## Module 6 – Lifecycle Management

This module manages older blob versions to help control storage consumption.

A Lifecycle Management rule was configured to manage older blob versions after a specified period.

### Main Functions

- Manage older blob versions
- Automatically apply lifecycle rules
- Reduce unnecessary storage consumption
- Support storage cost management

## Module 7 – Recovery Demonstration

This module demonstrates the recovery of blob data after an accidental overwrite.

An accidental modification was simulated on the blob.

A previously stored version containing the original data was selected and made the current version.

### Recovery Flow

```text
Original Blob Data
        ↓
Blob Modified
        ↓
Accidental Overwrite
        ↓
Previous Versions Available
        ↓
Select Original Version
        ↓
Make Current Version
        ↓
Original Data Recovered
