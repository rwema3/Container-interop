# Container Interoperability

Container-interop has been the test-bed of PSR-11. From v1.2, container-interop directly extends PSR-11 interfaces.
Therefore, all containers implementing container-interop are now *de-facto* compatible with PSR-11.

- Projects implementing container-interop interfaces are encouraged to directly implement PSR-11 interfaces instead.
- Projects consuming container-interop interfaces are very strongly encouraged to directly type-hint on PSR-11 interfaces, in order to be compatible with PSR-11 containers that are not compatible with container-interop.

Regarding the delegate lookup feature, that is present in container-interop and not in PSR-11, the feature is actually a design pattern. It is therefore not deprecated. Documentation regarding this design pattern will be migrated from this repository into a separate website in the future.

## About

*container-interop* tries to identify and standardize features in *container* objects (service locators,
dependency injection containers, etc.) to achieve interoperability.

Through discussions and trials, we try to create a standard, made of common interfaces but also recommendations.

If PHP projects that provide container implementations begin to adopt these common standards, then PHP
applications and projects that use containers can depend on the common interfaces instead of specific
implementations. This facilitates a high-level of interoperability and flexibility that allows users to consume
*any* container implementation that can be adapted to these interfaces.

The work done in this project is not officially endorsed by the [PHP-FIG](http://www.php-fig.org/), but it is being
worked on by members of PHP-FIG and other good developers. We adhere to the spirit and ideals of PHP-FIG, and hope
this project will pave the way for one or more future PSRs.


## Installation

You can install this package through Composer:

```json
composer require container-interop/container-interop
```

The packages adheres to the [SemVer](http://semver.org/) specification, and there will be full backward compatibility
between minor versions.

