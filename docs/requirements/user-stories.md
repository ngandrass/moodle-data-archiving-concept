# User Stories

This section contains user stories that were identified during a stakeholder workshop which was conducted with
e-learning personal and IT administrators of various universities from Germany, Austria, and Switzerland. The user
stories are structured into different categories, each focusing on a specific aspect of the archiving ecosystem.

Together with the [generic base requirements](../base-requirements), they form the base for formulating concrete
feature requests for and to establish the technical architecture drafts of the aspired archiving solution on.


## Stakeholders

- **Teacher (Examiner)**: Creates, organizes, and conducts exams. Grades exams and provides feedback to students. Has
  full access to all exam data.
- **Student (Examinee)**: Takes exams, receives grades and feedback. Can have access to their own exam data, depending
  on the respective exam and teacher.
- **Chief Operations Officer (COO)**: Makes executive decisions about the operational activities of the university. This
  especially includes, but is not limited to, the examination processes and study path organization.
- **Legal Staff Member**: Responsible for ensuring that the exams themselves, the exam systems, and related procedures
  are compliant with relevant laws and regulations. Does not implement required measures themselves, but provides the
  necessary information to administrators and teachers.
- **Moodle Administrator**: Administrates Moodle instances. Has full administrative access to the Moodle website
  administration.
- **System Administrator**: Administrates the servers that run a Moodle instance. Has full access to the server and the
  database the Moodle LMS is running on.


## User Stories

This section lists the identified user stories.

!!! warning "TODO"
    Assign final IDs to user stories before release


### Scope

This section lists user stories that define the scope of the archiving system. This includes, for example, the different
Moodle activities that should be archived and which courses should be archived.

#### Activities and Data Types

!!! abstract "[US-SC-00] Archiving quiz attempts"
    As a <b>teacher</b>, I want to archive quiz attempts as PDF files.

    As a <b>student</b>, I want to store my quiz results to be able to look back at them at a later point in time.

!!! abstract "[US-SC-00] Archiving assignments"
    As a <b>teacher</b>, I want to archive assignments, so that I can have all submissions within a single archive
    without the need to download all files manually.
    
    As a <b>student</b>, I want to be able to easily access both the files I submitted and the feedback (e.g., PDF
    annotations) I received for an assignment.

!!! abstract "[US-SC-00] Additional files"
    As a <b>teacher</b>, I want to be able to include additional files in the archives, such as seating plans. Such
    files would be uploaded manually by the teacher prior to or after an exam.

!!! abstract "[US-SC-00] Completeness of archives"
    As a <b>teacher</b>, <b>student</b>, or <b>legal staff member</b>, I want the archives to include all relevant data
    that was created during the exam. This includes, for example, exam metadata, questions, final answers, answer
    history, file submissions, grades, feedback, and more.

!!! abstract "[US-SC-00] Archiving original unprocessed exams"
    As a <b>legal staff member</b>, I want to have the original, unedited exams that are given to the students at the
    beginning of an exam archived, so that I can clearly see what was given and what was added by the students.

#### Control of Scope

!!! abstract "[US-SC-00] Enabling or disabling archiving for specific activities"
    As a <b>Moodle administrator</b> or <b>COO</b>, I want to enable or disable the archiving of specific activities, so that I can
    ensure that only the relevant data is archived.

!!! abstract "[US-SC-00] Enabling or disabling archiving for specific course categories"
    As a <b>Moodle administrator</b> or <b>COO</b>, I want to enable or disable the archiving of quiz attempts and assignments for
    specific course categories, so that I can ensure that only the relevant data (e.g., actual exams) is archived.

!!! abstract "[US-SC-00] Making archiving of certain activities mandatory or optional"
    As a <b>COO</b> or <b>Moodle administrator</b>, I want to be able to define whether the archiving of certain
    activities or courses is mandatory or optional, so that I can ensure that all relevant data is always archived but
    leave <b>teachers</b> the freedom to decide whether they want to archive additional data.

#### Size of Scope

!!! abstract "[US-SC-00] Data from big cohorts"
    As a <b>teacher</b>, I want the archiving solution to be able to handle event large cohorts of students reliably, so
    that I do not encounter limitations if my courses have many students.

    As a <b>system administrator</b>, I want the archiving solution to be able to handle large cohorts of students
    effectively without consuming too many resources or failing due to the size.


### Archiv Contents

This section lists user stories that target the contents of the archives. This includes, for example, the types of data
that should be archived and how the data should be structured.

#### Exam Data

!!! abstract "[US-AC-00] Quiz question types (Moodle core)"
    As a <b>teacher</b>, I want the quiz attempt reports to support all question types that are available in Moodle, so
    that I can continue using my existing questions.

!!! abstract "[US-AC-00] Quiz question types (third party)"
    As a <b>teacher</b>, I want third party question types to be supported, so that I can also export, for example,
    STACK questions.

    As a <b>Moodle administrator</b>, I want third party question types to be supported alongside the core question
    types to eliminate the need for custom archiving solutions or hacks.

    _Commonly used and highly requested question types include: STACK, Gapfill, Coderunner, KPrime, Freehand drawing,
    ..._

!!! abstract "[US-AC-00] Math formulas and other complex content"
    As a <b>teacher</b>, I want the quiz attempt reports to support math formulas and other complex dynamic content,
    e.g., GeoGebra applets.

!!! abstract "[US-AC-00] Rich media content"
    As a <b>teacher</b>, I want to be able to use rich media content in my exams, such as videos and audio files.

    As a <b>system administrator</b>, I want the archiving system to compress rich media content as much as possible in
    order to preserve disk space.

#### Metadata

!!! abstract "[US-AC-00] Metadata availability"
    As a <b>teacher</b>, I want the quiz attempt reports to include metadata, such as the date and time of the quiz
    attempt, the duration, and marks.

    As a <b>legal staff member</b>, I want the quiz attempt reports to include metadata, such as the date and time of the
    quiz attempt, the duration, and the IP address of the student.

!!! abstract "[US-AC-00] Matriculation number"
    As a <b>teacher</b>, I want the matriculation number of the student to be included in the archived data, so that I
    can easily identify the student.

    As a <b>legal staff member</b>, I want the matriculation number to be included in the archive, so that I can
    (automatically) retrieve all records to a given person in case of legal disputes.

!!! abstract "[US-AC-00] Variable file names"
    As a <b>teacher</b>, I want the file names to be configurable, including variables (e.g., student name,
    matriculation number, date, ...), so that I can easily identify the student and the assignment when looking for a
    specific attempt.

    As a <b>system administrator</b>, I want the file names to be configurable, including variables (e.g., student name,
    matriculation number, date, ...), so that I can enforce a consistent naming scheme across all archives and ensure
    compatibility with other systems at our institution.

#### Additional Data

!!! abstract "[US-AC-00] Answer history and log files"
    As a <b>teacher</b> or <b>legal staff member</b>, I want relevant logs from the exam period to be included in the
    archive. These logs include but are not limited to: answer histories, question access logs, submission logs,
    IP addresses, ...

!!! abstract "[US-AC-00] Course backups"
    As a <b>teacher</b>, I want to be able to include a backup of the whole course in the archive, so that I can easily
    reuse the course in the future.

    As a <b>Moodle administrator</b>, I want to be able to include a backup of the whole course in the archive, so that
    I can easily restore the course as a whole if this is needed.

!!! abstract "[US-AC-00] Activity backups"
    As a <b>teacher</b>, I want to be able to include a backup of a single activity in the archive, so that I can easily
    reuse the activity in the future without the need to restore the whole course.

    As a <b>Moodle administrator</b>, I want to be able to include a backup of a single activity in the archive, so that
    I can easily restore the activity if this is needed while preserving storage space that would otherwise be wasted by
    a full course backup that might not be required.

#### Customization and Miscellaneous

!!! abstract "[US-AC-00] Customizable quiz attempt report contents"
    As a <b>teacher</b>, I want to be able to customize the contents of the quiz attempt report, so that I can, for
    example, exclude example solutions from PDFs that I hand out to my students.

!!! abstract "[US-AC-00] Data searchability"
    As a <b>teacher</b>, I want the data in the archives to be searchable, so that I can easily find specific quiz
    attempts or assignments.

    As a <b>teacher</b> or <b>student</b>, I want to be able to search within the contents of quiz attempt reports, so
    that I can easily find specific answers or questions.

!!! abstract "[US-AC-00] Anonymization"
    As a <b>teacher</b>, I want to be able to generated anonymized exports that I can share with colleagues or students,
    so that I can discuss the results without revealing the identity the respective student.


### File Formats and Data Handling

This section lists user stories that describe the used file formats of the archives and the data within. This includes,
for example, the container format used to group archived data and the file format of individual files.

#### Data Formats

!!! abstract "[US-FF-00] Open file formats and protocols"
    As a <b>system administrator</b>, I want the archives to be in open and standardized file formats, so that I can
    ensure that the data can be read in the future.

    As a <b>system administrator</b>, I want the archiving systems to use open and standardized protocols, so that I
    can connect them with existing external systems and other university IT infrastructure (e.g., s3, FTP, ...).

!!! abstract "[US-FF-00] ZIP archives"
    As a <b>teacher</b>, I want to have the quiz attempts and assignments archived in ZIP files, so that I can easily
    download and extract the files without requiring third party software.

!!! abstract "[US-FF-00] Export of single quiz attempts as PDF"
    As a <b>teacher</b>, I want to be able to export single quiz attempts as PDF files, so that I can easily share them
    with students.

    As a <b>student</b>, I want to be able to export a PDF report of my quiz attempt, so that I can archive my answers
    and grades for myself.

#### Storage and Space

!!! abstract "[US-FF-00] Archive size"
    As a <b>system administrator</b>, I want the archives to preserve as much space as possible, so that the archives
    do not take up too much space on the server.

    As a <b>teacher</b>, I want the archives to be small, so that I can download them quickly.

!!! abstract "[US-FF-00] PDF/A file format"
    As a <b>legal staff member</b>, I want the archives to be in the `PDF/A` file format, so that the data is stored in
    a standardized format that is designed for long-term data readability.

#### Copy Protection

!!! abstract "[US-FF-00] Watermarks and copy protection"
    As a <b>teacher</b>, I want to be able to include watermarks or other forms of copy traceability / protection in the
    archives, so that I can prevent students from sharing their exam results with others or trace back the ones that did.


### Data Integrity and Data Protection

This section lists user stories that target the data integrity and data protection requirements of the archives. This,
for example, includes the compliance with the General Data Protection Regulation (GDPR) and the data integrity of the
archived data.

#### Data Integrity and Legal

!!! abstract "[US-DI-00] Data integrity"
    As a <b>legal staff member</b>, I want to be able to verify that the data in the archives has not been tampered with,
    and did not get corrupted in any way.

!!! abstract "[US-DI-00] Data attestation"
    As a <b>legal staff member</b>, I want to be able to prove that the data in the archives is authentic, has not been
    tampered with, and was created at a specific point in time so that I can use the data in legal disputes.

    As a <b>legal staff member</b>, I want the data to be signed with a digital signature by an external authority, so
    that I can prove the authenticity of the data in court.

#### Data Protection

!!! abstract "[US-DI-00] Rights management"
    As a <b>Moodle administrator</b>, I want to be able to define who has access to the archived data, so that I can
    ensure that only authorized persons can access the data and prevent unauthorized people from deleting archives.

    As a <b>legal staff member</b>, I want to be able to prevent the deletion of archives once created, e.g., through
    a WORM (write-once-read-many) storage solution.

!!! abstract "[US-DI-00] Future readability"
    As a <b>legal staff member</b>, I want the archives to be stored in a way that ensures that the data can be read in
    the far future (5 to 10 years), so that the data can be retrieved in case of legal disputes.

    As a <b>system administrator</b>, I want the archives to be stored in a way that is independent of specific software
    and its versions, so that I do not need to restore an ancient Moodle instance to retrieve data. This explicitly
    includes storing the data in a way that is independent of the Moodle LMS.

#### General Data Protection Regulation (GDPR)

!!! abstract "[US-DI-00] GDPR compliance"
    As a <b>legal staff member</b>, I want the archiving process to be compliant with the General Data Protection
    Regulation (GDPR).

    As a <b>student</b>, I want to be able to request the data that is stored about me and have it deleted once archived
    data passed its legal retention time.

    As a <b>Moodle administrator</b> or <b>system administrator</b>, I want the system to handle deletion of archived
    data beyond its legal retention time automatically.


### Automation

This section lists user stories that outline the needs for automation of the archiving process. This includes, for
example, the automatic archiving of quiz attempts and assignments and the automatic transfer of archives into external
storage systems.

#### Process Automation

!!! abstract "[US-AU-00] Automated archiving"
    As a <b>teacher</b>, I want the archiving process to be automated, so that I do not have to archive quiz attempts
    and assignments manually.

    As a <b>legal staff member</b>, I want the archiving process to be automated, so that I can ensure that all
    relevant data is always archived and can not be forgotten about.

!!! abstract "[US-AU-00] Configurable trigger for archiving"
    As a <b>Moodle administrator</b>, I want to be able to specify which events (e.g., end of an exam, finalization of 
    grades, manual clearance) trigger the archiving process, so that I can adapt the archiving process to the specific
    processes of my institution. If the trigger is time-based, I want to be able to specify the time freely.

#### System Integration

!!! abstract "[US-AU-00] Automated transfer into external systems"
    As a <b>legal staff member</b>, I want the archives to be automatically transferred into external systems, such as
    write-once-read-many (WORM) storage or document management systems (DMS), so that the data is stored appropriately.

    As a <b>system administrator</b>, I want the archives to be automatically transferred into external systems, so that
    the archives do not take up too much space on the server and I do not have to manually transfer data.

!!! abstract "[US-AU-00] Integration with campus management systems"
    As a <b>COO</b>, I want the archiving system to be integrated with the campus management system, so that archived
    data can easily be processed further, e.g., storing it inside a student's digital record file.

    As a <b>teacher</b>, I want the archiving system to be integrated with the campus management system, so that I can
    easily link the archived exam data to the rest of the student's data.

    As a <b>system administrator</b>, I want the archiving system to be integrated with the campus management system, so
    that I do not have to develop custom glue logic.

!!! abstract "[US-AU-00] Archiving reminders"
    As a <b>teacher</b>, I want to receive a reminder if an activity that should be archived is not yet archived, so
    that I can ensure that I do not forget to finalize an exam.

    As a <b>Moodle administrator</b> or <b>COO</b>, I want teachers to receive reminders if an activity that should be
    archived is not yet archived, so that I do not have to manually remind teachers to archive their exams.

#### Data Processing

!!! abstract "[US-AU-00] Parallel processing"
    As a <b>system administrator</b>, I want that multiple archiving jobs can be processed in parallel, so that the
    larger jobs can be processed faster, and they do not block smaller jobs for too long.

    As a <b>system administrator</b>, I want to be able to adjust the number of parallel jobs, so that I can control the
    resourece consumption on the server.

    As a <b>teacher</b>, I want archiving jobs to start as soon as I enqueue them, so that I can access the archived
    data in a timely manner.


### User Interface and User Experience

This section lists user stories that describe the user interface and user experience of the archiving system. This, for
example, includes the overview of archived data and the documentation of the archiving system.

#### Archive Job Management

!!! abstract "[US-UI-00] Archiving overview in every course"
    As a <b>teacher</b>, I want to be able to see an overview of all activities that are potentially archiveable inside
    a given Moodle course, so that I can easily identify what can be archived and start the process.

    As a <b>Moodle administrator</b>, I want to see if all required activities within a course were already archived
    successfully and if not, I want to be able to start the archiving process.

!!! abstract "[US-UI-00] Archive job status updates"
    As a <b>teacher</b>, I want to be able to see the status of the archiving process, so that I can see if the process
    is running and when it has finished.

#### Data Access

!!! abstract "[US-UI-00] Access to archived data (internal)"
    As a <b>teacher</b>, I want to be able to access the archived data, so that I can look at the data at a later point
    in time or use it for a post-exam review.

    As a <b>student</b>, I want to be able to access the archived data, so that I can review my exam performance at a
    later point and keep a copy for myself.

    As a <b>legal staff member</b>, I want to be able to access the archived data, so that I can retrieve the data in
    case of legal disputes.

    As a <b>Moodle administrator</b>, I want to be able to access the archived data, so that I can use it for restoring
    courses or activities.

!!! abstract "[US-UI-00] Access to archived data (external)"
    As a <b>legal staff member</b>, I want to be able to easily provide access to selected data archives to external
    third parties, e.g., in case of legal disputes.

    As a <b>legal staff member</b> or <b>system administrator</b>, I want external access to data archives to be logged.

!!! abstract "[US-UI-00] User-based views"
    As a <b>student</b>, <b>teacher</b>, or <b>legal staff member</b>, I want to be able to view and retrieve all
    archived data that is associated with a single student.

!!! abstract "[US-UI-00] Accessibility"
    As a <b>teacher</b> or <b>student</b>, I want the archived data to be as accessible ("barrier-free"), as the exam
    itself to be able to browse the archived data without any problems.


#### Traceability and Documentation

!!! abstract "[US-UI-00] Archiving history"
    As a <b>teacher</b>, <b>Moodle administrator</b> or <b>legal staff member</b>, I want to be able to see the history
    of archiving jobs. I want to be able to identify at which point in time archives were created.

!!! abstract "[US-UI-00] Documentation"
    As a <b>teacher</b>, I want to have a user documentation that explains how to use the archiving system, so that I
    can use the system without having to ask other staff members for help.

    As a <b>Moodle administrator</b>, I want to have a user documentation that explains how to use the archiving system,
    so that I can send it to teachers who ask for help.

    As a <b>Moodle administrator</b>, I want to have a technical documentation that explains the different plugin
    settings and how to configure them, so that I can tweak the archiving system to my universities needs.

    As a <b>system administrator</b>, I want to have a technical documentation that explains how to install and
    troubleshoot the different components in case of error.


### Administration and Maintenance

This section lists user stories that describe the administration and maintenance procedure of the archiving system. This
includes, for example, the enforcement of corporate policies and the software security of the archiving system.

#### Resilience

!!! abstract "[US-AM-00] Reliability and correctness"
    As a <b>teacher</b>, I want the archiving process to be reliable, so that I can trust that all relevant data is
    archived and I do not have to worry about it.

    As a <b>legal staff member</b>, I want the archiving process to be automatically testet to work correctly, so that I
    can trust that the data is archived correctly and can be retrieved in case of legal disputes.

    As a <b>Moodle administrator</b>, I want to know which versions of Moodle, PHP, and my DBMS are tested and work.

!!! abstract "[US-AM-00] Corporate policies"
    As a <b>legal staff member</b>, I want to be able to define certain rules and standards for what and how data is
    archived, so that I can ensure that the data is archived in a way that is compliant with relevant laws.

    As a <b>Moodle administrator</b>, I want to be able to define certain rules and standards for what and how data is
    archived, so that I can ensure that data is archived in a way that meets our universities requirements.

    As a <b>teacher</b>, I do not want to worry about what data needs to be archived in which fashion.

#### Security

!!! abstract "[US-AM-00] Software security"
    As a <b>system administrator</b>, I want the software to be maintained and updated regularly, so that I can ensure
    that the software and its dependencies are secure and up-to-date.

    As a <b>system administrator</b>, I want the developers to act upon found security vulnerabilities in a timely
    manner, so that I can ensure that the software stays secure.

!!! abstract "[US-AM-00] Future maintenance"
    As a <b>Moodle administrator</b> or <b>system administrator</b>, I want a solution that will be maintained in the
    foreseeable future, so that I do not have to switch to another system again in a few years.

    As a <b>legal staff member</b> or <b>COO</b>, I want the archiving system to be maintained in the foreseeable future,
    so that I do not have to evaluate and integrate a new software and archiving process again in a few years.

#### Installation and Operation

!!! abstract "[US-AM-00] Easy setup"
    As a <b>system administrator</b> or <b>Moodle administrator</b>, I want the setup of the archiving system to be
    easy, so that I can install and configure the system without requiring too much time and effort.

!!! abstract "[US-AM-00] Easy operations"
    As a <b>system administrator</b> or <b>Moodle administrator</b>, I want the operation of the archiving system to be
    easy, so that I can use the system without requiring too much time and effort.

!!! abstract "[US-AM-00] Compatibility with used software"
    As a <b>system administrator</b>, I want the archiving system to be compatible with my existing software versions,
    especially the used Moodle version. The archiving solution must at least support all Moodle LTS versions that are
    currently maintained, including the supported PHP and DBMS versions.

!!! abstract "[US-AM-00] Configurability and scalability"
    As a <b>system administrator</b>, I want to control the resource consumption of the archiving system, so that I can
    ensure that the system does not consume too many resources.

    As a <b>system administrator</b>, I want to be able to easily scale the archiving system, so that I can ensure that
    the system can handle the load of all Moodle instances at my university, even during exam times, but also scale down
    during low load times.
