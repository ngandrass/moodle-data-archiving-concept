# Architecture

!!! danger "Work in Progress"
    This document is still work in progress (WIP) and might contain incomplete, incorrect, or outdated information.

TODO


## Findings

- Not all Moodle activities offer sub-plugin structures in which additional archiving plugins can be integrated.
    - `mod_quiz` offers an applicable sub-plugin structure (quiz report plugins), but `mod_assign` does not.
    - This means, that archiving plugins must be implemented as a `local` plugins. In theory, a `coursereport` or
      `report` would suffice for now, but might limit the flexibility of the archiving system in the future.
    - A `local` plugin could inject appropriate sub-sites directly into different parts of the Moodle navigation. This
      would allow for a more seamless integration of the archiving system into the Moodle user interface (e.g., one
      overview page per course but also a global system-wide overview / status page).
- Defining an own "sub-plugin" infrastructure for the central archiving plugin is the most clean and maintainable
  solution. It would be extended by plugins for archiving specific activities or transferring archived data to external
  systems.
    - This must not be a full-blown Moodle plugin type, but can rather be a simple interface that is implemented by
      archiving plugins, resembling a driver-like structure.
    - Each (sub-)system could communicate via the [Moodle Events API](https://docs.moodle.org/dev/Events_API) if found
      useful.
- The [Moodle Events API](https://docs.moodle.org/dev/Events_API) ...
    - Allows components to dispatch events that other components can listen to, if desired.
    - Enable a decoupled architecture, where different components are only loosely connected, hence allow for easier
      maintenance and extension.
    - Allows both, communication between components within a single plugin, and with other plugins.
    - Allows to be handled by individual observers or by a central manager.
    - Can contain arbitrary data
    - Can contain snapshots of database data at a given point in time
    - Follow a strict and useful naming convention
    - Are fully supported by all targeted Moodle versions


## Components

![](./architecture-overview.drawio)

### Archiving Manager

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


### Activity Archiving Drivers

- Executes an archiving job
    - Transforms existing user data into an archivable format
    - Creates digital archive files
    - Sends archived data back to the [Archiving Manager](#archiving-manager)
- Archiving jobs are executed asynchronously
- Tailored to one specific Moodle activity (e.g., Quiz, Assignment, ...)


#### Quiz (mod_quiz)

- Exports quiz attempts as fully-rendered PDF files
- Support for complex content and question types, including Drag and Drop, MathJax formulas, STACK plots, and other
  question / content types that require JavaScript processing
- Support for file submissions / attachments (e.g., essay files)
- Customization of generated PDF and HTML reports
- Quiz attempt reports are fully text-searchable, including mathematical formulas
- Generation of Moodle backups (.mbz) of the quiz
- Generation of checksums for every file within the archive and the archive itself
- Data compression and vector based MathJax formulas to preserve disk space
- Based on the Moodle [Quiz Archiver](https://moodle.org/plugins/quiz_archiver) Plugin


#### Assignment (mod_assign)

- Exports ...
    - Assignment metadata, instructions, text submissions, submission metadata, grading, feedback, and comments as PDF
      file(s)
    - Submitted files
    - Annotated feedback / PDF files
- Text submissions are fully-rendered PDF files to support complex content and formatting
- Generation of Moodle backups (.mbz) of the assignment
- Generation of checksums for every file within the archive and the archive itself
- Data compression and vector based MathJax formulas to preserve disk space


### Storage Drivers

#### Moodledata Storage

- Stores archived data in the Moodle storage system

#### File System Storage

- Copies archived data to a given filesystem path

#### S3 Object Storage

- Sends archived data to a s3 object storage system (e.g., WORM storage)

#### FTP

- Uploads archived data to a FTP server


### Worker Services

- Performs off-loaded archiving tasks, e.g., web page to PDF rendering
- Communicates via the Moodle Webservice API
- Usage depends on activity archiving drivers


## Misc

![](./quiz-archiver-architecture.drawio)
