# Moodle Data Archiving Concept

[![Latest Version](https://img.shields.io/github/v/release/ngandrass/moodle-data-archiving-concept)](https://github.com/ngandrass/moodle-data-archiving-concept/releases)
[![Maintenance Status](https://img.shields.io/maintenance/yes/9999)](https://github.com/ngandrass/moodle-data-archiving-concept/)
[![License](https://img.shields.io/github/license/ngandrass/moodle-data-archiving-concept)](https://github.com/ngandrass/moodle-data-archiving-concept/blob/master/LICENSE)
[![GitHub Issues](https://img.shields.io/github/issues/ngandrass/moodle-data-archiving-concept)](https://github.com/ngandrass/moodle-data-archiving-concept/issues)
[![GitHub Pull Requests](https://img.shields.io/github/issues-pr/ngandrass/moodle-data-archiving-concept)](https://github.com/ngandrass/moodle-data-archiving-concept/pulls)
[![Donate with PayPal](https://img.shields.io/badge/PayPal-donate-orange)](https://www.paypal.me/ngandrass)
[![Sponsor with GitHub](https://img.shields.io/badge/GitHub-sponsor-orange)](https://github.com/sponsors/ngandrass)
[![GitHub Stars](https://img.shields.io/github/stars/ngandrass/moodle-data-archiving-concept?style=social)](https://github.com/ngandrass/moodle-data-archiving-concept/stargazers)
[![GitHub Forks](https://img.shields.io/github/forks/ngandrass/moodle-data-archiving-concept?style=social)](https://github.com/ngandrass/moodle-data-archiving-concept/network/members)
[![GitHub Contributors](https://img.shields.io/github/contributors/ngandrass/moodle-data-archiving-concept?style=social)](https://github.com/ngandrass/moodle-data-archiving-concept/graphs/contributors)

Meta repository containing conceptual drafts for generic archiving of exam data from the Moodle LMS.

This collection of documents describes an extensive concept for archiving data from various Moodle activities for
long-term storage independent of Moodle. This includes an analysis of the archivable data within Moodle, respective
requirements engineering, and a technical specification for the aspired archiving solution.

The full table of contents is available online within the [concept document](https://ngandrass.github.io/moodle-data-archiving-concept/).


## Viewing the specification document

You can always find the most recent version of the specification document here: \
https://ngandrass.github.io/moodle-data-archiving-concept/

[![Open concept document](docs/assets/images/btn-open-document.png)](https://ngandrass.github.io/moodle-data-archiving-concept/)


## Building the specification document

Prior to any build, you have to install the dependencies using [Poetry](https://python-poetry.org/):

```bash
poetry install
```

### Locally with live preview

To run a local webserver that automatically re-builds the documentation on changes run:

```bash
poetry run mkdocs serve
```

### Building for online deployment

To build the full documentation for deployment on a webserver run:

```bash
poetry run mkdocs build
```

The resulting HTML files can be found in the `site/` directory.

### Building for offline-use without a webserver

To build the full documentation for offline use without a webserver run:

```bash
OFFLINE=true poetry run mkdocs build
```

The resulting HTML files can be found in the `site/` directory.
