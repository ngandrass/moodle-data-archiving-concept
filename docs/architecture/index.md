# Architecture

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
    - Allow to be handled by individual observers or by a central manager.
    - Can contain arbitrary data
    - Can contain snapshots of database data at a given point in time
    - Follow a strict and useful naming convention
    - Are fully supported by all targeted Moodle versions


## Misc

![](./architecture-overview.drawio)

![](./quiz-archiver-architecture.drawio)

```mermaid
flowchart TB
    subgraph moodle[Moodle]
        %% States
        manager[<tt>Moodle Plugin</tt><br>Course Archiving Manager]
        eventsapi[[<tt>Core API</tt><br>Moodle Events API]]
        assignmentarchiver[<tt>Moodle Plugin</tt><br>Assignment Archiver]
        quizarchiver[<tt>Moodle Plugin</tt><br>Quiz Archiver]
        anotherarchiver[<tt>Moodle Plugin</tt><br>Another Archiver]
        
        %% Connections
        manager <--> eventsapi
        eventsapi <--> quizarchiver
        eventsapi <--> assignmentarchiver
        eventsapi <-.-> anotherarchiver
        
        %% Styles
        style eventsapi fill:#cccccc,stroke:#666666
        style anotherarchiver stroke-dasharray:5 5, opacity:0.5
    end
    
    subgraph workers[Worker Services]
        %% States
        quizarchiveworker[<tt>External Service</tt><br>Quiz Archive Worker]
        anotherworker[<tt>External Service</tt><br>Another Archive Worker]

        %% Connections
        quizarchiver <--> quizarchiveworker
        anotherarchiver <-.-> anotherworker

        %% Styles
        style anotherworker fill:#b9e0a5,stroke:#97d077,stroke-dasharray:5 5, opacity:0.5
        style quizarchiveworker fill:#b9e0a5,stroke:#97d077
    end

    netstorage@{shape: lin-cyl, label: "<tt>External Service</tt><br>Network Storage"}
    dms@{shape: docs, label: "<tt>External Service</tt><br>Document Management System"}
    manager --> netstorage
    manager --> dms
    
```