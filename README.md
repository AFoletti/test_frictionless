# SFOE continuous data delivery - Overview
This repository contains the configuration files for the continuous data delivery of the Swiss Federal Office of Energy.
This fully automated process ensures that the published data is formally and technically of the highest possible quality. This allows every user to confidently use it without the need of long and boring data cleaning exercices.

## The main components
* A data staging area, where the various units upload their ready-to-be-tested data
* An automated checker on FME Server, testing for new uploads
* A frictionless datapackage for every dataset
* This repository, containing the GitHub Actions needed to perform the automated data validation runs
* A productive data repository for the validated data
* opendata.swiss data catalog as the main point of entry and discovery of our published data


## The process
Data publishers in the Office upload new data to a staging area. An automated FME script periodically checks the staging area for updated files and triggers the associated workflow here on GitHub.
The GitHub workflow uses publicly available Actions to test the data against a Frictionless data model. If the data passes the test, the workflow moves the data to the productive environment. From this moment onwards, the new data is available at opendata.swiss for the public to download.
Should the data not pass the test, it remains in the staging area and the responsible unit in the Office is automatically informed of the error. The Frictionless Action delivers a detailed report about the error and thus enables an easy handling of the issue.

## Currently automated tests
* [![ogd47](https://github.com/AFoletti/test_frictionless/actions/workflows/ogd47.yaml/badge.svg)](https://github.com/AFoletti/test_frictionless/actions/workflows/ogd47.yaml) - Vollzugsresultate der CO2-Emissionsvorschriften für Personenwagen
* (badge) - (dataset)
* ...
