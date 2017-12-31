# Architecture

The application orchestrator architecture includes several components in order
to manage the runtime lifecycle of applications:




## GitLab

**GitLab** is a web-based Git repository manager with wiki and
issue tracking features, using an open source license, developed by [GitLab Inc](https://about.gitlab.com/).

This components maintains the VNF descriptors and configuration scripts and parameters.

## artifactory

[JFrog](https://jfrog.com) Artifactory is a Universal Repository Manager supporting all major packaging formats, build tools and CI servers.

This component maintains all binary artifacts e.g. images,
software packages, etc. .

## AWX

AWX provides a web-based user interface, REST API, and task engine built on top of Ansible. It is the upstream project for Tower, a commercial derivative of AWX.
