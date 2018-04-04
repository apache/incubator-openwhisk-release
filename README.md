<!--
#
# Licensed to the Apache Software Foundation (ASF) under one or more contributor
# license agreements.  See the NOTICE file distributed with this work for additional
# information regarding copyright ownership.  The ASF licenses this file to you
# under the Apache License, Version 2.0 (the # "License"); you may not use this
# file except in compliance with the License.  You may obtain a copy of the License
# at:
#
# http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software distributed
# under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR
# CONDITIONS OF ANY KIND, either express or implied.  See the License for the
# specific language governing permissions and limitations under the License.
#
-->

# OpenWhisk Graduate and Release Management

[![License](https://img.shields.io/badge/license-Apache--2.0-blue.svg)](http://www.apache.org/licenses/LICENSE-2.0)
[![Build Status](https://travis-ci.org/apache/incubator-openwhisk-release.svg?branch=master)](https://travis-ci.org/apache/incubator-openwhisk-release)

The primary goal of this project is to provide the Apache OpenWhisk project's Release Managers the automation needed to guarantee a release complies with both the Apache Software Foundation's (ASF) [Release Creation Process](http://www.apache.org/dev/release-publishing.html) and [Release Policy](http://www.apache.org/legal/release-policy.html).

Specifically, this repository provides Release Management of all designated Apache OpenWhisk project repositories, by automating:
- Verification of the source code LICENSE and NOTICE files
- Building & deploying the OpenWhisk platform
- Running Build Verification Tests (BVT)
- Generating CHANGELOGs for each project repository (since last release)
- Packaging and signing source code (compressed archives) and binaries
- publishing the artifacts to the approved Apache directories

all in accordance with Apache guidelines.

## Release Process Methodology

This project uses Travis CI as the automated integration build tool to streamline the release process of Apache OpenWhisk. Stages can be applied to build different jobs, which are able to run either in sequential or parallel. Artifacts can be shared across different jobs by using the cache feature in Travis, as different jobs run on different virtual machines.

## Release publishing

Staged candidate releases of Apache OpenWhisk artifacts are published to the approved staging repository path under Apache with all required PGP singatures:
- https://dist.apache.org/repos/dist/dev/incubator/openwhisk/

Once candidates are approved, in accordance with required release processes and policies, their artifacts can be moved from the staging path to the approved release path:
- https://dist.apache.org/repos/dist/release/incubator/openwhisk/.

# Instructions for Release Managers

## Release Manager Tutorial
As a release manger of OpenWhisk, please visit [OpenWhisk Release tutorial](docs/tutorial.md).

## How to release an Apache project

## Release Approval

Apache requires a minimum of three positive votes and more positive than negative votes MUST be cast, in order to release.
Release manager of OpenWhisk sends a release note to the OpenWhisk mailing for votes, and opens the mail for 72 hours.
We can create JIRA issue for this release and close it when the requirement is met and ready for release. This step can
be done manually by the release manager, beyond the scope of this project.

An example of the release note can be found at the following link: [example of release note](https://github.com/apache/cordova-coho/blob/master/docs/coho-release-process.md).

## Artifact requirements
Artifacts for project repository source code and any compiled binaries are packaged separately with each artifact being signed cryptographically.

Source code needs to provide the installation script for users to deploy a full OpenWhisk environment. We target to implement this step in Travis build.

## Licensing requirements

All the source code has to be compliant with Apache Licensing Policy, by adding the LICENSE file, NOTICE file to each
repository and the release package, and adding Licensing headers to each source code file. Please visit [License_Compliance](docs/license_compliance.md) for detailed information.

## Release distribution requirements
We need to upload all artifacts to project’s subdirectory in Apache channel. This step needs to be implemented in Travis build.

# Specifications to implement the above release process

To find the specifications about how to implement the Apache Release process for OpenWhisk project set, please visit the
following page.

- [General Specification](docs/general_spec.md)

# References
[Apache release policy](http://www.apache.org/legal/release-policy.html)

# Notes
This projecy is still "in development" with many steps still in the process of being automated and brought into compliance. We welcome any reviews, comments or contributions to help us complete and improve any part of the process.
