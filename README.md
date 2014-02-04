# Continuum Package Scripts

These are the package config scripts we use to build the runtimes available in
Continuum.

Using these definitions can be done through the use of APC:

```console
$ apc package build go-1.1.2.conf
```

This will use the package definition to generate a build script, upload that to
Continuum, and have it generate the package and store the results as the
package's data.

### Operating Systems

Under the `os` directory are the package configurations for various
distributions and versions.

* Busybox (using Buildroot 2013.08.1)
* Ubuntu 12.04
* Ubuntu 13.10

### Packages

Under the `packages` directory are the package configurations for various common
packages that can be pulled into Continuum. Some of them are dependencies of
runtimes within the platform, or become dependencies while staging an
application (ie, might need git to checkout a repository).

* apache 2.2.26
* git 1.8.5.3
* maven 3.1.1
* memcached 1.4.17
* mercurial 2.9
* nginx 1.4.4
* redis 2.8.5
* subversion 1.8.5

### Runtimes

Under the `runtimes` directory are the pacakge configurations for various
runtimes that can be pulled into Continuum.

* go 1.2
* node 0.6.21
* node 0.8.26
* node 0.10.25
* openjdk 1.6.0-b27
* openjdk 1.7.0-u6-b24
* perl 5.14.4
* perl 5.16.3
* perl 5.18.2
* php 5.4.24
* php 5.5.8 (for both `apache/mod_perl` and `nginx/php-fpm`)
* python 2.7.6
* python 3.3.3
* ruby 1.8.7-p371-apc1
* ruby 1.9.3-p484
* ruby 2.0.0-p353
* ruby 2.1.0

### Patches

Under the `patches` directory are various patches carried locally.
