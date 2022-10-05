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

