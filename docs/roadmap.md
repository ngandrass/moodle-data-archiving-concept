# Roadmap

This page outlines the planned steps and milestones for the development of the aspired Moodle Data Archiving Solution.

### Legend

The state of each Milestone is depicted by the respective icon and color:

<div style="max-width: 200px;" markdown>
- !!! success "Completed"
- !!! note "In progress"
- !!! abstract "Not started yet"
</div>

### Milestones

!!! success "Analysis of existing solutions"
    Finding and inspecting existing solutions for extracting data from Moodle activities used for e-assessments.
    Identifying core features and limitations of each solution to gain insight into the current landscape.

    This task is completed. Results can be found here: [Analysis > Existing Solutions](analysis/existingsolutions.md)

    [:material-package-variant-closed: Show Results](analysis/existingsolutions.md){.md-button}

!!! success "Analysis of core Moodle activities available for e-assessments"
    Identifying all Moodle core activities that can be used for e-assessments and therefore should potentially be
    supported by the aspired archiving solution. For each activity, the data that it stores is analyzed. This includes
    listing all relevant user data points, metadata, file submissions, and other relevant information. Moreover, the
    structure of the existing data and how it relates to other data of the activity is analyzed.
    
    This task is completed. Results can be found here: [Analysis > Data Analysis](analysis/data-analysis.md)

    [:material-package-variant-closed: Show Results](analysis/data-analysis.md){.md-button}

!!! success "Stakeholder workshop"
    Conducting a workshop with stakeholders / universities in Germany, Switzerland, and Austria to gather requirements
    for the aspired archiving solution. Identify both general requirements, as well as institution-specific needs and
    weigh them by their perceived relevance. Create a digest of the workshop results and use them as a basis for the
    requirements engineering phase.

    This task is completed. Results can be found here:

    <div style="text-align: center;">
        <figure markdown="span" style="max-width: 256px; display: inline-block;">
            ![Keyword Clustering (German)](assets/artifacts/2024/20241127_Moodle_Archiving_Workshop_Stichwort_Cluster.svg){ loading=lazy }
            <figcaption>
                Keyword Clustering (German)<br>
                <a href="../assets/artifacts/2024/20241127_Moodle_Archiving_Workshop_Stichwort_Cluster.pdf" target="_blank">[Download as PDF]</a>
            </figcaption>
        </figure>
        &nbsp;&nbsp;&nbsp;
        <figure markdown="span" style="max-width: 215px; display: inline-block;">
            ![Identified Use Cases (German)](assets/artifacts/2024/20241127_Moodle_Archiving_Workshop_Use_Cases.svg){ loading=lazy }
            <figcaption>
                Identified Use Cases (German)<br>
                <a href="../assets/artifacts/2024/20241127_Moodle_Archiving_Workshop_Use_Cases.pdf" target="_blank">[Download as PDF]</a>
            </figcaption> 
        </figure>
        <br>
        _Perceived demand is indicated by the amount of dots on each card_
    </div>

!!! success "Formulation of user stories"
    Formulating concrete user stories in a structured fashion to highlight the expectations on the aspired archiving
    solution from various perspectives. Rating of every user story based on the perceived relevance / demand.

    User stories are based on the results of the stakeholder workshop, inputs from multiple conference talks / sessions
    about archiving of Moodle quizzes, and results from personal interviews with members of the Moodle community.

    This task is completed. Results can be found here: [Requirements > User Stories](requirements/user-stories.md)

    [:material-package-variant-closed: Show Results](requirements/user-stories.md){.md-button}

!!! success "Definition of base requirements for archiving exam data from Moodle"
    Defining hard base requirements that the aspired archiving solution must fulfill from a technical, functional and
    legal point of view. These requirements are independent of the actual Moodle activity itself but target general
    topics like data integrity, traceability, compatibility, regulatory topics, and privacy.

    This task is completed. Results can be found here: [Requirements > Base Requirements](requirements/base-requirements.md)

    [:material-package-variant-closed: Show Results](requirements/base-requirements.md){.md-button}

!!! success "First technical architecture draft"
    Creating a first draft of a possible technical architecture for the aspired archiving solution. Defining core
    components, interfaces, process states, and information flow. Forming proper abstractions and interfaces to allow
    flexible embedding in university infrastructures. Defining core implementation philosophies and principles.

    This task is completed. Results can be found here: [Architecture](architecture/index.md)

    [:material-package-variant-closed: Show Results](architecture/index.md){.md-button}

!!! abstract "Public availability of this document and project sources"
    TODO

!!! abstract "Presentation within the Moodle community"
    TODO

!!! note "Prototype implementation"
    TODO

!!! abstract "Re-evaluation of the technical architecture"
    TODO

!!! abstract "Full implementation of the archiving solution for a single activity"
    TODO

!!! abstract "Stable release on GitHub for early-adopters"
    TODO

!!! abstract "User and administrator documentation"
    TODO

!!! abstract "Implementing additional activities, storage backens, ..."
    TODO

!!! abstract "Release within the Moodle Plugin Directory"
    TODO
