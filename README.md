# Azure Testing

This project tests several interlok-azure components, specifically the
connections, consumers and producers of the mail, OneDrive, and
DataLake.

## Prerequisites

* A Microsoft Azure account
* A Microsoft O365 subscription
* A configured Azure application, that has permission to interact with
  Outlook, OneDrive, and the DataLake

## What it does

This project contains two channels, for the two supported types of
connection to Azure services (Graph API and DataLake), which contain a
number of workflows that each demonstrates an interlok-azure component.

Each workflow is made up of:

* An Azure consumer
* A service to log the received payload
* An Azure producer

## Getting started

* `./gradlew clean build`
* `(cd ./build/distribution && java -jar lib/interlok-boot.jar)`
* Load the config from this directory
  - Update Azure tenant, client secret, account details
* Details for configuring the connections can be found in the
  documentation for [Mail]() and [OneDrive]()

## Mail

* Poll the INBOX of the given user
* Log message payload
* Reply to the original sender with their message

## OneDrive

* Poll the OneDrive root directory for the given user
* Log message payload
* Upload the file to another users OneDrive root directory

### OneDrive Services

There are two workflows that test the OneDrive services upload/download.
As with the consumers/producers these require their connection to be
configured correctly.

## DataLake

* Poll the path /in on the supplied file system of the given user
* Log message payload
* Upload the file to /out for the given user

[Mail]: https://interlok.adaptris.net/interlok-docs/#/pages/cookbook/cookbook-o365
[OneDrive]: https://interlok.adaptris.net/interlok-docs/#/pages/cookbook/cookbook-1drive
