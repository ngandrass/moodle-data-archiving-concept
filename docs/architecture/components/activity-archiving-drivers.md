# Activity Archiving Drivers

!!! warning "TODO"
    This section is still work in progress (WIP) and might contain incomplete, incorrect, or outdated information.

- Executes an archiving job
    - Transforms existing user data into an archivable format
    - Creates digital archive files
    - Sends archived data back to the [Archiving Manager](#archiving-manager)
- Archiving jobs are executed asynchronously
- Tailored to one specific Moodle activity (e.g., Quiz, Assignment, ...)


## Quiz (mod_quiz)

!!! warning "TODO"
    This section is still work in progress (WIP) and might contain incomplete, incorrect, or outdated information.

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


## Assignment (mod_assign)

!!! warning "TODO"
    This section is still work in progress (WIP) and might contain incomplete, incorrect, or outdated information.

- Exports ...
    - Assignment metadata, instructions, text submissions, submission metadata, grading, feedback, and comments as PDF
      file(s)
    - Submitted files
    - Annotated feedback / PDF files
- Text submissions are fully-rendered PDF files to support complex content and formatting
- Generation of Moodle backups (.mbz) of the assignment
- Generation of checksums for every file within the archive and the archive itself
- Data compression and vector based MathJax formulas to preserve disk space
