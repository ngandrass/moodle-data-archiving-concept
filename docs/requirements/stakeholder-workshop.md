# Stakeholder Workshop

TODO

## Stakeholders

- **Teacher (Examiner)**: Creates, organizes, and conducts exams. Grades exams and provides feedback to students. Has
  full access to all exam data.
- **Student (Examinee)**: Takes exams, receives grades and feedback. Can have access to their own exam data, depending
  on the respective exam and teacher.
- **Legal Staff Member**: Responsible for ensuring that the exams themselves, the exam systems, and related procedures
  are compliant with relevant laws and regulations. Does not implement required measures themselves, but provides the
    necessary information to administrators and teachers.
- **Moodle Administrator**: Administrates Moodle instances. Has full administrative access to the Moodle website
  administration.
- **System Administrator**: Administrates the servers that run a Moodle instance. Has full access to the server and the
  database the Moodle LMS is running on.


## User Stories

TODO

### Scope

- TODO

!!! abstract "[US-SC-00] Archiving quiz attempts"
    As a <b>teacher</b>, I want to archive quiz attempts as PDF files.

!!! abstract "[US-SC-00] Archiving assignments"
    As a <b>teacher</b>, I want to archive assignments, so that I can have all submissions within a single archive
    without the need to download all files manually.

!!! abstract "[US-SC-00] Enabling or disabling archiving for specific course categories"
    As a <b>Moodle administrator</b>, I want to enable or disable the archiving of quiz attempts and assignments for
    specific course categories, so that I can ensure that only the relevant data (e.g., actual exams) is archived.


### Archiv Contents

- TODO

!!! abstract "[US-AC-00] Matriculation number"
    As a <b>teacher</b>, I want the matriculation number of the student to be included in the archived data, so that I
    can easily identify the student.

    As a <b>legal staff member</b>, I want the matriculation number to be included in the archive, so that I can
    (automatically) retrieve all records to a given person in case of legal disputes.

!!! abstract "[US-AC-00] Variable file names"
    As a <b>teacher</b>, I want the file names to be configurable to include variables (e.g., student name, matriculation
    number, date, ...), so that I can easily identify the student and the assignment when looking for a specific attempt.

!!! abstract "[US-AC-00] Customizable quiz attempt report contents"
    As a <b>teacher</b>, I want to be able to customize the contents of the quiz attempt report, so that I can, for
    example, exclude example solutions from PDFs that I hand out to my students.

!!! abstract "[US-AC-00] Quiz question types"
    As a <b>teacher</b>, I want the quiz attempt reports to support all question types that are available in Moodle, so
    that I can continue using my existing questions.

    As a <b>teacher</b>, I want third party question types to be supported, so that I can also export, for example,
    STACK questions.

!!! abstract "[US-AC-00] Math formulas and other complex content"
    As a <b>teacher</b>, I want the quiz attempt reports to support math formulas and other complex dynamic content,
    e.g., GeoGebra applets.

!!! abstract "[US-AC-00] Data searchability"
    As a <b>teacher</b>, I want the data in the archives to be searchable, so that I can easily find specific quiz
    attempts or assignments.

    As a <b>teacher</b> or <b>student</b>, I want to be able to search within the contents of quiz attempt reports, so
    that I can easily find specific answers or questions.


### File Formats and Data Handling

- TODO

!!! abstract "[US-FF-00] ZIP archives"
    As a <b>teacher</b>, I want to have the quiz attempts and assignments archived in ZIP files, so that I can easily
    download and extract the files without requiring third party software.

!!! abstract "[US-FF-00] Archive size"
    As a <b>system administrator</b>, I want the archives to preserve as much space as possible, so that the archives
    do not take up too much space on the server.

    As a <b>teacher</b>, I want the archives to be small, so that I can download them quickly.

!!! abstract "[US-FF-00] Open file formats and protocols"
    As a <b>system administrator</b>, I want the archives to be in open and standardized file formats, so that I can
    ensure that the data can be read in the future.

    As a <b>system administrator</b>, I want the archiving systems to use open and standardized protocols, so that I
    can connect them with existing external systems and other university IT infrastructure (e.g., s3, FTP, ...).

!!! abstract "[US-FF-00] Export of single quiz attempts as PDF"
    As a <b>teacher</b>, I want to be able to export single quiz attempts as PDF files, so that I can easily share them
    with students.

    As a <b>student</b>, I want to be able to export a PDF report of my quiz attempt, so that I can archive my answers
    and grades for myself.

!!! abstract "[US-FF-00] PDF/A file format"
    As a <b>legal staff member</b>, I want the archives to be in the `PDF/A` file format, so that the data is stored in
    a standardized format that is designed for long-term data readability.


### Data Integrity and Data Protection

- TODO

!!! abstract "[US-DI-00] GDPR compliance"
    As a <b>legal staff member</b>, I want the archiving process to be compliant with the General Data Protection
    Regulation (GDPR).

    As a <b>student</b>, I want to be able to request the data that is stored about me and have it deleted once archived
    data passed its legal retention time.

!!! abstract "[US-DI-00] Future readability"
    As a <b>legal staff member</b>, I want the archives to be stored in a way that ensures that the data can be read in
    the far future (5 to 10 years), so that the data can be retrieved in case of legal disputes.

    As a <b>system administrator</b>, I want the archives to be stored in a way that is independent of specific software
    and its versions, so that I do not need to restore an ancient Moodle instance to retrieve data.

!!! abstract "[US-DI-00] Data integrity"
    As a <b>legal staff member</b>, I want to be able to verify that the data in the archives has not been tampered with,
    and did not get corrupted in any way.

!!! abstract "[US-DI-00] Data attestation"
    As a <b>legal staff member</b>, I want to be able to prove that the data in the archives is authentic, has not been
    tampered with, and was created at a specific point in time so that I can use the data in legal disputes.

    As a <b>legal staff member</b>, I want the data to be signed with a digital signature by an external authority, so
    that I can prove the authenticity of the data in court.


### Automation

- TODO

!!! abstract "[US-AU-00] Automated archiving"
    As a <b>teacher</b>, I want the archiving process to be automated, so that I do not have to archive quiz attempts
    and assignments manually.

    As a <b>legal staff member</b>, I want the archiving process to be automated, so that I can ensure that all
    relevant data is always archived and can not be forgotten about.

!!! abstract "[US-AU-00] Automated transfer into external systems"
    As a <b>legal staff member</b>, I want the archives to be automatically transferred into external systems, such as
    write-once-read-many (WORM) storage or document management systems (DMS), so that the data is stored appropriately.

    As a <b>system administrator</b>, I want the archives to be automatically transferred into external systems, so that
    the archives do not take up too much space on the server and I do not have to manually transfer data.


### User Interface and User Experience

- TODO

!!! abstract "[US-UI-00] Archive job status updates"
    As a <b>teacher</b>, I want to be able to see the status of the archiving process, so that I can see if the process
    is running and when it has finished.

!!! abstract "[US-UI-00] Archiving overview in every course"
    As a <b>teacher</b>, I want to be able to see an overview of all activities that are potentially archiveable inside
    a given Moodle course, so that I can easily identify what can be archived and start the process.

    As a <b>Moodle administrator</b>, I want to see if all required activities within a course were already archived
    successfully and if not, I want to be able to start the archiving process.

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

- TODO

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

!!! abstract "[US-AM-00] Software security"
    As a <b>system administrator</b>, I want the software to be maintained and updated regularly, so that I can ensure
    that the software and its dependencies are secure and up-to-date.

    As a <b>system administrator</b>, I want the developers to act upon found security vulnerabilities in a timely
    manner, so that I can ensure that the software stays secure.

!!! abstract "[US-AM-00] Easy setup"
    As a <b>system administrator</b> or <b>Moodle administrator</b>, I want the setup of the archiving system to be
    easy, so that I can install and configure the system without requiring too much time and effort.
