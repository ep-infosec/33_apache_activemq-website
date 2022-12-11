---
layout: default_md
title: NMS API Past Releases
title-class: page-title-nms
type: nms
---

<div class="alert alert-warning">
  These are older releases. To get the current release, please see the <a href="{{site.baseurl}}/components/nms/nms-api-downloads" class="alert-link">download page</a>.
</div>

For any releases not shown here, check the [archive](https://archive.apache.org/dist/activemq/apache-nms-api/) or [even-older archive](https://archive.apache.org/dist/activemq/apache-nms/).

It is important to [verify the integrity]({{site.baseurl}}/components/nms/nms-api-downloads#verify-the-integrity-of-downloads) of the files you download.


{% assign reversed_releases = site["nms_api_releases"] | reverse %}
{% assign current_releases = "" | split: ',' %}

{% for current_release_prefix in site.data.current_releases["nms_api"] %}
    {% for release in reversed_releases %}
        {% if release.version contains current_release_prefix %}
            {% assign current_releases = current_releases | push: release.version %}
            {% break %}
        {% endif %}
    {% endfor %}
{% endfor %}

{% for release in reversed_releases %}
    {% unless current_releases contains release.version %}
#### NMS API {{release.version}} ({{release.release_date | date_to_string: "ordinal", "US"}})
{{ release.shortDescription }}

{% include nms_api_download_links.md release=release is_current_release=false %}

###### Changelog

For a detailed view of new features and bug fixes, see the [Release Notes]({{ release.release_notes }})

<br/>
    {% endunless %}
{% endfor %}


#### NMS API 1.7.1 (09/04/2015)

This is a minor release of the NMS API which adds a few minor fixes for NMS Providers operating in MSDTC Transactions.

|Apache.NMS Source code|[Apache.NMS-1.7.1-src.zip](https://archive.apache.org/dist/activemq/apache-nms/1.7.0/Apache.NMS-1.7.1-src.zip)|[SHA512](https://archive.apache.org/dist/activemq/apache-nms/1.7.0/Apache.NMS-1.7.1-src.zip.sha512)|[PGP Signature](https://archive.apache.org/dist/activemq/apache-nms/1.7.0/Apache.NMS-1.7.1-src.zip.asc)
|Apache.NMS Binary Assemblies|[Apache.NMS-1.7.1-bin.zip](https://archive.apache.org/dist/activemq/apache-nms/1.7.0/Apache.NMS-1.7.1-bin.zip)|[SHA512](https://archive.apache.org/dist/activemq/apache-nms/1.7.0/Apache.NMS-1.7.1-bin.zip.sha512)|[PGP Signature](https://archive.apache.org/dist/activemq/apache-nms/1.7.0/Apache.NMS-1.7.1-src.zip.asc)

###### Changelog

For a more detailed view of new features and bug fixes, see the [release notes](https://issues.apache.org/jira/secure/ReleaseNote.jspa?projectId=12311201&styleName=Html&version=12329541)  
  
<br/>


#### NMS API 1.7.0 (01/08/2015)

This is a major release of the NMS API which adds some new APIs and fixes some minor bugs in the NMS API libraries common code.

*   Added IDisposable as a base of IDestination.
*   Added some improvements to the Unit tests framework.
*   Added some new provider names (AMQP and MQTT) to allow for future clients.

|Description|Download Link|PGP Signature File|Version|
|---|---|---|---|
|Apache.NMS Source code|[Apache.NMS-1.7.0-src.zip](https://archive.apache.org/dist/activemq/apache-nms/1.7.0/Apache.NMS-1.7.0-src.zip)|[Apache.NMS-1.7.0-src.zip.asc](https://archive.apache.org/dist/activemq/apache-nms/1.7.0/Apache.NMS-1.7.0-src.zip.asc)|1.7.0.3635|
|Apache.NMS Binary Assemblies|[Apache.NMS-1.7.0-bin.zip](https://archive.apache.org/dist/activemq/apache-nms/1.7.0/Apache.NMS-1.7.0-bin.zip)|[Apache.NMS-1.7.0-bin.zip.asc](https://archive.apache.org/dist/activemq/apache-nms/1.7.0/Apache.NMS-1.7.0-bin.zip.asc)|1.7.0.3635|

###### Changelog

For a more detailed view of new features and bug fixes, see the [release notes](https://issues.apache.org/jira/secure/ReleaseNote.jspa?projectId=12311201&styleName=Html&version=12325350)

<br/>


#### NMS API 1.6.0 (05/24/2013)

This is a major release of the NMS API which adds some new APIs and fixes some minor bugs in the NMS API libraries common code.

*   Added Recover method to ISession.
*   Added new events to ISession for Transaction begin, commit and rollback.
*   Added method in IConnection to purge created Temp Destinations.

|Description|Download Link|PGP Signature File|Version|
|---|---|---|---|
|Apache.NMS Source code|[Apache.NMS-1.6.0-src.zip](https://archive.apache.org/dist/activemq/apache-nms/1.6.0/Apache.NMS-1.6.0-src.zip)|[Apache.NMS-1.6.0-src.zip.asc](https://archive.apache.org/dist/activemq/apache-nms/1.6.0/Apache.NMS-1.6.0-src.zip.asc)|1.6.0.3061|
|Apache.NMS Binary Assemblies|[Apache.NMS-1.6.0-bin.zip](https://archive.apache.org/dist/activemq/apache-nms/1.6.0/Apache.NMS-1.6.0-bin.zip)|[Apache.NMS-1.6.0-bin.zip.asc](https://archive.apache.org/dist/activemq/apache-nms/1.6.0/Apache.NMS-1.6.0-bin.zip.asc)|1.6.0.3061|

###### Changelog

For a more detailed view of new features and bug fixes, see the [release notes](https://issues.apache.org/jira/secure/ReleaseNote.jspa?projectId=12311201&styleName=Html&version=12315987)

<br/>


#### NMS API 1.5.1 (07/06/2012)

This is a bugfix release of the NMS API there are no API changes in this release.

*   Fixes a bug that can cause the Message properties object to marshal to a byte array that is much larger than needed which adds unwanted overhead on the wire for marshaled Messages.

|Description|Download Link|PGP Signature File|Version|
|---|---|---|---|
|Apache.NMS Source code|[Apache.NMS-1.5.1-src.zip](https://archive.apache.org/dist/activemq/apache-nms/1.5.0/Apache.NMS-1.5.1-src.zip)|[Apache.NMS-1.5.1-src.zip.asc](https://archive.apache.org/dist/activemq/apache-nms/1.5.0/Apache.NMS-1.5.1-src.zip.asc)|1.5.1.2739|
|Apache.NMS Binary Assemblies|[Apache.NMS-1.5.1-bin.zip](https://archive.apache.org/dist/activemq/apache-nms/1.5.0/Apache.NMS-1.5.1-bin.zip)|[Apache.NMS-1.5.1-bin.zip.asc](https://archive.apache.org/dist/activemq/apache-nms/1.5.0/Apache.NMS-1.5.1-bin.zip.asc)|1.5.1.2739|

###### Changelog

For a more detailed view of new features and bug fixes, see the [release notes](https://issues.apache.org/jira/secure/ReleaseNote.jspa?projectId=12311201&styleName=Html&version=12315640)

<br/>


#### NMS API 1.5.0 (01/10/2011)

This release adds some great new features to the NMS API.

*   New Optional .NET Transaction Specific Connection classes that allow a client to offer support for operations within MS .NET Distributed Transactions.

|Description|Download Link|PGP Signature File|Version|
|---|---|---|---|
|Apache.NMS Source code|[Apache.NMS-1.5.0-src.zip](https://archive.apache.org/dist/activemq/apache-nms/1.5.0/Apache.NMS-1.5.0-src.zip)|[Apache.NMS-1.5.0-src.zip.asc](https://archive.apache.org/dist/activemq/apache-nms/1.5.0/Apache.NMS-1.5.0-src.zip.asc)|1.5.0.2194|
|Apache.NMS Binary Assemblies|[Apache.NMS-1.5.0-bin.zip](https://archive.apache.org/dist/activemq/apache-nms/1.5.0/Apache.NMS-1.5.0-bin.zip)|[Apache.NMS-1.5.0-bin.zip.asc](https://archive.apache.org/dist/activemq/apache-nms/1.5.0/Apache.NMS-1.5.0-bin.zip.asc)|1.5.0.2194|

###### Changelog

For a more detailed view of new features and bug fixes, see the [release notes](https://issues.apache.org/jira/secure/ReleaseNote.jspa?projectId=12311201&styleName=Html&version=12315640)

<br/>


#### NMS API 1.4.0 (09/10/2010)

This release adds some great new features to the NMS API and fixes several bugs found in the 1.3.0 release.  Some highlights for this release.

*   Improved URI handling in all NMS clients.
*   Added a new SetBytes method to IMapMessage.
*   Added a new MessageTransformer API.
*   Many new Unit Tests added to the Test Suite.
*   Many bug fixes.

|Description|Download Link|PGP Signature File|Version|
|---|---|---|---|
|Apache.NMS Source code|[Apache.NMS-1.4.0-src.zip](https://archive.apache.org/dist/activemq/apache-nms/1.4.0/Apache.NMS-1.4.0-src.zip)|[Apache.NMS-1.4.0-src.zip.asc](https://archive.apache.org/dist/activemq/apache-nms/1.4.0/Apache.NMS-1.4.0-src.zip.asc)|1.4.0.2075|
|Apache.NMS Binary Assemblies|[Apache.NMS-1.4.0-bin.zip](https://archive.apache.org/dist/activemq/apache-nms/1.4.0/Apache.NMS-1.4.0-bin.zip)|[Apache.NMS-1.4.0-bin.zip.asc](https://archive.apache.org/dist/activemq/apache-nms/1.4.0/Apache.NMS-1.4.0-bin.zip.asc)|1.4.0.2075|

###### Changelog

For a more detailed view of new features and bug fixes, see the [release notes](https://issues.apache.org/activemq/secure/ReleaseNote.jspa?projectId=11010&styleName=Html&version=12188)

<br/>


#### NMS API 1.3.0 (05/14/2010)

This release adds some great new features to the NMS API and fixes several bugs found in the 1.2.0 release.  Some highlights for this release.

*   Improved API Documentation.
*   Many new Unit Tests added to the Test Suite.
*   Many bug fixes.

|Description|Download Link|PGP Signature File|Version|
|---|---|---|---|
|Apache.NMS Source code|[Apache.NMS-1.3.0-src.zip](https://archive.apache.org/dist/activemq/apache-nms/1.3.0/Apache.NMS-1.3.0-src.zip)|[Apache.NMS-1.3.0-src.zip.asc](https://archive.apache.org/dist/activemq/apache-nms/1.3.0/Apache.NMS-1.3.0-src.zip.asc)|1.3.0.1959|
|Apache.NMS Binary Assemblies|[Apache.NMS-1.3.0-bin.zip](https://archive.apache.org/dist/activemq/apache-nms/1.3.0/Apache.NMS-1.3.0-bin.zip)|[Apache.NMS-1.3.0-bin.zip.asc](https://archive.apache.org/dist/activemq/apache-nms/1.3.0/Apache.NMS-1.3.0-bin.zip.asc)|1.3.0.1959|

###### Changelog

For a more detailed view of new features and bug fixes, see the [release notes](https://issues.apache.org/activemq/secure/ReleaseNote.jspa?projectId=11010&styleName=Html&version=12150)

<br/>


#### 1.2.0 (01/15/2010)

This release adds some great new features to the NMS API and fixes several bugs found in the 1.1.0 release.  Some highlights for this release.

*   Addition of IConnectionMeteData to the Connection API.
*   Addition of IQueueBrowser to the Session API.
*   Improved API Documentation.
*   New IStreamMessage interface.
*   New IRedeliveryPolicy interface.
*   Expanded IByteMessage interface to read/write primitive types.
*   Many new Unit Tests added to the Test Suite.
*   Many bug fixes.

|Description|Download Link|PGP Signature File|Version|
|---|---|---|---|
|Apache.NMS Source code|[Apache.NMS-1.2.0-src.zip](https://archive.apache.org/dist/activemq/apache-nms/1.2.0/Apache.NMS-1.2.0-src.zip)|[Apache.NMS-1.2.0-src.zip.asc](https://archive.apache.org/dist/activemq/apache-nms/1.2.0/Apache.NMS-1.2.0-src.zip.asc)|1.2.0.1836|
|Apache.NMS Binary Assemblies|[Apache.NMS-1.2.0-bin.zip](https://archive.apache.org/dist/activemq/apache-nms/1.2.0/Apache.NMS-1.2.0-bin.zip)|[Apache.NMS-1.2.0-bin.zip.asc](https://archive.apache.org/dist/activemq/apache-nms/1.2.0/Apache.NMS-1.2.0-bin.zip.asc)|1.2.0.1836|

###### Changelog

For a more detailed view of new features and bug fixes, see the [release notes](https://issues.apache.org/activemq/secure/ReleaseNote.jspa?projectId=11010&styleName=Html&version=11815)

<br/>


#### NMS API 1.1.0 (07/12/2009)

The 1.1.0 release is a major milestone for the Apache NMS project. It is the first official release of the main Apache.NMS project, and all provider implementation projects. Following are some highlights of this release:

*   Improved API Documentation.
*   Many bug fixes.

|Description|Download Link|PGP Signature File|Version|
|---|---|---|---|
|Apache.NMS Source code|[Apache.NMS-1.1.0-src.zip](https://archive.apache.org/dist/activemq/apache-nms/1.1.0/Apache.NMS-1.1.0-src.zip)|[Apache.NMS-1.1.0-src.zip.asc](https://archive.apache.org/dist/activemq/apache-nms/1.1.0/Apache.NMS-1.1.0-src.zip.asc)|1.1.0.1642|
|Apache.NMS Binary Assemblies|[Apache.NMS-1.1.0-bin.zip](https://archive.apache.org/dist/activemq/apache-nms/1.1.0/Apache.NMS-1.1.0-bin.zip)|[Apache.NMS-1.1.0-bin.zip.asc](https://archive.apache.org/dist/activemq/apache-nms/1.1.0/Apache.NMS-1.1.0-bin.zip.asc)|1.1.0.1642|

###### Changelog

For a more detailed view of new features and bug fixes, see the [release notes](https://issues.apache.org/activemq/secure/ReleaseNote.jspa?projectId=11010&styleName=Html&version=11814)


