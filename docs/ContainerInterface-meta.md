# ContainerInterface Meta Document

## Introduction

This document describes the process and discussions that lead to the `ContainerInterface`.
Its goal is to explain the reasons behind each decision.

## Goal

The goal set by `ContainerInterface` is to standardize how frameworks and libraries make use of a
container to obtain objects and parameters.

By standardizing such a behavior, frameworks and libraries using the `ContainerInterface`
could work with any compatible container.
That would allow end users to choose their own container based on their own preferences.

It is important to distinguish the two usages of a container:

- configuring entries
- fetching entries

Most of the time, those two sides are not used by the same party.
While it is often end users who tend to configure entries, it is generally the framework that fetch
entries to build the application.

This is why this interface focuses only on how entries can be fetched from a container.

## Interface name

The interface name has been thoroughly discussed and was decided by a vote.

The list of options considered with their respective votes are:

- `ContainerInterface`: +8
- `ProviderInterface`: +2
- `LocatorInterface`: 0
- `ReadableContainerInterface`: -5
- `ServiceLocatorInterface`: -6
- `ObjectFactory`: -6
- `ObjectStore`: -8
- `ConsumerInterface`: -9

[Full results of the vote](https://github.com/container-interop/container-interop/wiki/%231-interface-name:-Vote)

The complete discussion can be read in [the issue #1](https://github.com/container-interop/container-interop/issues/1).

## Interface methods

The choice of which methods the interface would contain was made after a statistical analysis of existing containers.
The results of this analysis are available [in this document](https://gist.github.com/mnapoli/6159681).
