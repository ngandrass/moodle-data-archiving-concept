# Events

This document defines all events that are emitted by the archiving system to the Moodle Events API.

!!! warning "TODO"
    This section is still work in progress (WIP) and might contain incomplete, incorrect, or outdated information.

!!! question "Check subplugin frankenstyle naming"
    It needs to be verified how the frankenstyle names of subplugins are generated. Adjust class names accordingly.


## Archive Jobs

The following events are related to the top-level archiving jobs.

| Class name                                                  | Trigger                               | CRUD   | Payload        | Record snapshot |
|-------------------------------------------------------------|---------------------------------------|--------|----------------|-----------------|
| `\{{moodle_component_manager}}\event\archive_job_created`   | A new archive job was created         | create |                | Archive job     |
| `\{{moodle_component_manager}}\event\archive_job_updated`   | An archive job was updated            | update | Updated fields | Archive job     |
| `\{{moodle_component_manager}}\event\archive_job_completed` | An archive job completed successfully | update |                | Archive job     |
| `\{{moodle_component_manager}}\event\archive_job_failed`    | An archive job failed                 | update |                | Archive job     |
| `\{{moodle_component_manager}}\event\archive_job_aborted`   | An archive job was aborted gracefully | update |                | Archive job     |
| `\{{moodle_component_manager}}\event\archive_job_deleted`   | An archive job was deleted            | delete |                | Archive job     |


## Activity archiving tasks

The following events are used for the communication with the [activity archiving drivers](../../components/activity-archiving-drivers).

| Class name                                                               | Trigger                                                                         | CRUD   | Payload  | Record snapshot |
|--------------------------------------------------------------------------|---------------------------------------------------------------------------------|--------|----------|-----------------|
| `\{{moodle_component_manager}}_archiver_<activity>\event\task_created`   | An archive job requests data from an activity of type `activity` to be archived | create | {{todo}} | {{todo}}        |
| `\{{moodle_component_manager}}_archiver_<activity>\event\task_updated`   | An archive task for an activity of type `activity` was updated                  | update | {{todo}} | {{todo}}        |
| `\{{moodle_component_manager}}_archiver_<activity>\event\task_completed` | An archive task for an activity of type `activity` was completed successfully   | update | {{todo}} | {{todo}}        |
| `\{{moodle_component_manager}}_archiver_<activity>\event\task_failed`    | An archive task for an activity of type `activity` failed                       | update | {{todo}} | {{todo}}        |
| `\{{moodle_component_manager}}_archiver_<activity>\event\task_aborted`   | An archive task for an activity of type `activity` was aborted gracefully       | update | {{todo}} | {{todo}}        |


## Storage tasks

The following events are used for the communication with the [storage drivers](../../components/storage-drivers).

| Class name                                                                 | Trigger                                                                 | CRUD   | Payload  | Record snapshot |
|----------------------------------------------------------------------------|-------------------------------------------------------------------------|--------|----------|-----------------|
| `\{{moodle_component_manager}}_store_<storage>\event\read_task_created`    | Retrieval of an artifact from a storage of type `storage` was requested | create | {{todo}} | {{todo}}        |
| `\{{moodle_component_manager}}_store_<storage>\event\read_task_updated`    | A read task for a storage of type `storage` was updated                 | update | {{todo}} | {{todo}}        |
| `\{{moodle_component_manager}}_store_<storage>\event\read_task_completed`  | An artifact was successfully retrieved from a storage of type `storage` | update | {{todo}} | {{todo}}        |
| `\{{moodle_component_manager}}_store_<storage>\event\read_task_failed`     | A read from a storage of type `storage` failed                          | update | {{todo}} | {{todo}}        |
| `\{{moodle_component_manager}}_store_<storage>\event\read_task_aborted`    | A read from a storage of type `storage` was aborted gracefully          | update | {{todo}} | {{todo}}        |

| Class name                                                                 | Trigger                                                                 | CRUD   | Payload  | Record snapshot |
|----------------------------------------------------------------------------|-------------------------------------------------------------------------|--------|----------|-----------------|
| `\{{moodle_component_manager}}_store_<storage>\event\write_task_created`   | Transfer of an artifact to a storage of type `storage` was requested    | create | {{todo}} | {{todo}}        |
| `\{{moodle_component_manager}}_store_<storage>\event\write_task_updated`   | A write task for a storage of type `storage` was updated                | update | {{todo}} | {{todo}}        |
| `\{{moodle_component_manager}}_store_<storage>\event\write_task_completed` | An artifact was successfully transferred to a storage of type `storage` | update | {{todo}} | {{todo}}        |
| `\{{moodle_component_manager}}_store_<storage>\event\write_task_failed`    | A transfer to a storage of type `storage` failed                        | update | {{todo}} | {{todo}}        |
| `\{{moodle_component_manager}}_store_<storage>\event\write_task_aborted`   | A transfer to a storage of type `storage` was aborted gracefully        | update | {{todo}} | {{todo}}        |


## External event connectors

The following events are used for communication with [external event connectors](../../components/external-event-connectors).

| Class name                                                                     | Trigger                                                                               | CRUD   | Payload                              | Record snapshot |
|--------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|--------|--------------------------------------|-----------------|
| `\{{moodle_component_manager}}_exteventcon_<eec>\event\transmission_completed` | Transmission of an event via an external event connector of type `eec` was successful | update | Service-specific metadata (optional) | Event object    |
| `\{{moodle_component_manager}}_exteventcon_<eec>\event\transmission_failed`    | Transmission of an event via an external event connector of type `eec` failed         | update | Service-specific metadata (optional) | Event object    |
