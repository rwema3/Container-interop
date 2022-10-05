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

