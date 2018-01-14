# This Document

This document describes the concepts and a corresponding reference solution
architecture capable of automating the runtime lifecycle of applications and
application components belonging to virtualised network functions (VNFs).

A virtualised network function descriptor (VNFD) serves as the
foundation for the automation procedures and is used as a data source to
configure standardised lifecycle management workflows.

These standardised lifecycle management workflows allow to embed application
specific scripts in a well defined manner in order to address the application
specific configuration requirements without disrupting end-to-end control of
the lifecycle management process.

In this way different VNFs can be managed consistently without having to write
custom workflows for each version of VNFs which needs to be deployed, upgraded
or modified in any other manner.

The first chapter "Quick Start" provides instructions of how to setup the
application orchestrator and manage the lifecycle of a simple VNF.

The chapter "Application Model" explains the basic concepts behind the
standardised runtime lifecycle management of applications and application
components.

The following chapter "Application Orchestrator" then describes the structure of
the reference solution implementing these basic automation concepts.

After that the chapters deal with how to administrate the reference solution,
how to manage the lifecycle of VNFs as a user and finally how to make use of the
code to support the further development of the application orchestrator.
