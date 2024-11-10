# Archiving Manager

The archiving manager is the central entry point for archiving tasks.

!!! warning "TODO"
    This section is still work in progress (WIP) and might contain incomplete, incorrect, or outdated information.


## Tasks and Responsibilities

!!! abstract "Course Archiving Overview"
    Providing an overview of archivable data inside each course and whether it has already been archived or not 

!!! abstract "Global Archiving Overview"
    Providing a global overview of archivable data across all courses. Also provides an overview of connected storage
    systems and their status.

!!! abstract "Archive Job Handling"
    Managing archiving tasks as distinct jobs

    - Create, inspect, delete archiving jobs
    - Delegates archiving of activity data to the respective [Activity Archiving Drivers](activity-archiving-drivers)
    - Displays progress and status of archiving jobs
    - Handling of multiple archiving jobs in parallel

!!! abstract "Common Post-Processing"
    Handling common post-processing steps for archived data

    - Requesting of digital signatures using TSP

!!! abstract "Automation"
    Automation of archiving tasks

    - Initiating archive jobs periodically or on specific signals
    - Selection of criteria for automated archiving (e.g., course categories, activity types, activity status, ...)
    - Sending of error notifications if automated archiving jobs failed

!!! abstract "Auto-deletion / GDPR Compliance"
    Management of auto-deletion of archived data after a certain retention time (GDPR compliance)

    - Keeping track of retention times for archived data
    - Initiating deletion of archived data after retention time has passed 
    
    Handling of GDPR requests for retrieval of personal data

!!! abstract "Archive File Handling"
    Forwarding finalized archives to storage drivers

!!! abstract "Global Defaults and Policies"
    Management of global defaults and policies for archiving data

    - Filename patterns, archive formats, retention time, ...
    - Enabling / disabling of archiving for course categories


## Interfaced Components

- [Activity Archiving Drivers](../activity-archiving-drivers)
- [Storage Drivers](../storage-drivers)


## Details

### Archive Job Flow

The following sequence diagram illustrated the basic information flow of a successful archiving job.

```mermaid
sequenceDiagram
    autonumber
    actor User
    
    %% User input
    User ->> Archiving Manager: Request activity archiving

    %% Job start
    activate Archiving Manager
    Archiving Manager ->> Archiving Manager: Init archiving job
    Archiving Manager --) Activity Archiving Driver: Enqueue task
    deactivate Archiving Manager
    
    %% Job processing
    activate Activity Archiving Driver
    Activity Archiving Driver ->> Activity Archiving Driver: Process activity data
    opt Task Offloading
        Activity Archiving Driver --) Worker Service: Enqueue tasks
        activate Worker Service
        Worker Service --) Activity Archiving Driver: Processed data
        deactivate Worker Service
    end
    Activity Archiving Driver --) Archiving Manager: Activity archive
    deactivate Activity Archiving Driver
    
    %% Job postprocessing
    activate Archiving Manager
    Archiving Manager ->> Archiving Manager: Finalize archive job
    Archiving Manager --) Storage Driver: Request archive storing
    deactivate Archiving Manager
    activate Storage Driver
    Storage Driver ->> Storage Driver: Store archive
    Storage Driver --) Archiving Manager: Storage confirmation
    deactivate Storage Driver
    activate Archiving Manager
    deactivate Archiving Manager
```