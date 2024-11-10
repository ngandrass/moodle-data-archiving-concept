# Archiving Manager

!!! warning "TODO"
    This section is still work in progress (WIP) and might contain incomplete, incorrect, or outdated information.

- Central entry point for archiving tasks
- Provides an overview of archivable data inside each course and whether it has already been archived or not
- Provides a global overview of archivable data across all courses
- Manages archiving jobs and provides access to archived data
    - Create, inspect, delete archiving jobs
    - Archiving of activity data is handled by the respective [Activity Archiving Drivers](#activity-archiving-drivers)
- Manages archived data
    - Auto-deletion / GDPR retention
    - Digital signatures (TSP)
- Handles interfacing of external services for storing archived data
    - External services are handled by the respective [External Service Drivers](#external-service-drivers)
- Manages policies for archiving data
    - Enforces filenames, file formats, retention time, ...
    - Enabling / disabling of archiving for course categories
    - Access management via Moodle capabilities

