Introduction
============

Managing the lifecycle of the virtual infrastructure and software components of
virtual network functions in a highly automated way requires a **standardized
description of the structure and behavior** of its components.

VNF Model
---------

This descriptor needs to be based on an **abstract model** which allows to decouple the dependencies related to changes on both the infrastructure and VNF level.

This model needs to account for the specific requirements which DTAG has raised e.g. related to security considerations and in addition follow a generic structure, so that the introduction of new VNFs would not require the adaptation of the model.

The VNF Model can reflect both a desired target state as well as the
current state of the resources. These VNF Models allow to calculate required
changes towards a target state.

[Further details...](model.md)

VNF Descriptor (VNFD)
---------------------

A descriptor for virtualized network functions is described with the help of TOSCA as a list of various resources which need to be provisioned into a distributed cloud center environment.

These resources can be described individually but may reference one another.

[Further details...](descriptor.md)
