Container interface
===================

This document describes a common interface for dependency injection containers.

The goal set by `ContainerInterface` is to standardize how frameworks and libraries make use of a
container to obtain objects and parameters (called *entries* in the rest of this document).

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD",
"SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be
interpreted as described in [RFC 2119][].

The word `implementor` in this document is to be interpreted as someone
implementing the `ContainerInterface` in a dependency injection-related library or framework.
Users of dependency injections containers (DIC) are referred to as `user`.

[RFC 2119]: http://tools.ietf.org/html/rfc2119

1. Specification
-----------------

### 1.1 Basics

- The `Interop\Container\ContainerInterface` exposes two methods : `get` and `has`.

- `get` takes one mandatory parameter: an entry identifier. It MUST be a string.
  A call to `get` can return anything (a *mixed* value), or throws an exception if the identifier
  is not known to the container. Two successive calls to `get` with the same
  identifier SHOULD return the same value. However, depending on the `implementor`
  design and/or `user` configuration, different values might be returned, so
  `user` SHOULD NOT rely on getting the same value on 2 successive calls.
  While `ContainerInterface` only defines one mandatory parameter in `get()`, implementations
  MAY accept additional optional parameters.

- `has` takes one unique parameter: an entry identifier. It MUST return `true`
  if an entry identifier is known to the container and `false` if it is not.
  `has($id)` returning true does not mean that `get($id)` will not throw an exception.
  It does however mean that `get($id)` will not throw a `NotFoundException`.

### 1.2 Exceptions

Exceptions directly thrown by the container MUST implement the
[`Interop\Container\Exception\ContainerException`](../src/Interop/Container/Exception/ContainerException.php).

