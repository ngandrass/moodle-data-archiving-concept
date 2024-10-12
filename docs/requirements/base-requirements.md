# Base Requirements

This section describes base requirements for the archiving solution and the data that it archives. These requirements
apply to all archivable data, regardless of the specific Moodle activity it originates from. Therefore, this set of
requirements can be extended by additional requirements for specific Moodle activities.


## Data Integrity

TODO

- The archived data must resemble the original data as closely as possible and no critical information, e.g., grades,
  must be lost or altered.
- Display / rendering of archived data must not change in the future. All data must be fully rendered at the point of
  archiving so that it does not depend on future software behavior[^1]. For PDF files, the PDF/A standard should be used.
- Archived data must be stored alongside SHA256 checksums to verify the integrity of the archived data.
- Digital cryptographic signatures should be able to be issued for archived data by a third party to attest their 
  integrity and time of creation using the Time-Stamp Protocol (TSP).

[^1]: This explicitly excludes dynamic web content (HTML files), such as JavaScript-based applets or similar, from being
      a valid archiving format on its own. This is due to it requiring rendering inside a browser, which is not
      guaranteed to be reproducible in the future.


## Traceability

TODO

- Extensive metadata must be stored alongside the archived data and be kept until the archived data can be deleted.
- It must be traceable who archived a set of data.


## Compatibility and Autonomy

TODO

- Archives must be readable in up to 10 years.
- Archives must be readable without requiring the Moodle instance it was created on.
- Archives must be transferable to external third party systems, such as network storages or document management systems.


## Data Protection, Regulatory, and Privacy

TODO

- The archiving process must comply with the general data protection regulation (GDPR).
- Users must be able to request the data stored about them.
- Archived data should automatically be deleted after the legal retention period.
- Access to archived data must be controlled by appropriate capabilities, integrating with the Moodle role concept.
- Private data must not compulsorily be sent to third-party services that are not under the control of the institution.


## Accessibility

TODO

- The archiving software must use open standards for data storage and data transmission to ensure that the data can
  still be accessed in the future, without requiring specific software.
- The code of the archiving solution should be publicly available, free of charge.


## Miscellaneous

- Archives should be compressed to preserve storage space.
