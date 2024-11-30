# External Event Connectors

External event connectors allow forwarding of specific events within the archiving system to external services, such as
campus management systems. This can be used to trigger specific actions in external systems, such as storing the path to
an archived exam file for a given student inside a student record.

!!! warning "TODO"
    This section is still work in progress (WIP) and might contain incomplete, incorrect, or outdated information.


## Tasks and Responsibilities

!!! abstract "Event Forwarding"
    Forwards specific events to external systems, such as the successful creation of a new artifact for a student.

    - External event connectors primarily transmit information / metadata. Full archive files are primarily transmitted by
      the respective [storage drivers](../storage-drivers).

!!! abstract "Transformation of Data"
    Transforms internal event data into a format that is understandable by the external system.
    
!!! abstract "Configurability"
    Allowing independent configuration of the different connectors (e.g., event sensitivity list, API credentials, ...)


## Interfaced Components

- [Archiving Manager](../archiving-manager)


## Implementations

!!! warning "Needs further analysis"
    An analysis of the currently used campus management solutions and the specific business processes of the target
    institutions must be conducted to determine a list of relevant external systems to be supported and what APIs to
    address.
