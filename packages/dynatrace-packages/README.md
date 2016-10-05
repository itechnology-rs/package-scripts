# Dynatrace Package Scripts

This is to serve as a repository for package scripts that support the various applications that Dynatrace can be installed against.
Some packages may need dependencies added or removed, depending on how you are using Apcera to deploy the application in your environment.

## Included Packages

### dynatrace-java package

* This package script is agnostic to the application server being used for your application. Specify your other environment dependencies in your application manifest file.
* Additional packages may need to be created, if one does not already exist for the application server being used in your environment.
* The only dependency included in this package script is 'linux'.
* CATALINA_OPTS is the environment variable this package was initially built against. Make the appropriate change, based on the app server and configuration that is being used in your environment.
* The values for the AGENT_NAME and COLLECTOR_HOST env vars should be updated to reflect the proper collector endpoint/port and agent configuration for your environment.
* The value for the DT_HOME env var does not need to be changed, but it can be if you prefer the Dynatrace libraries to reside in a different folder structure.

## General Documentation

Full documentation on the package build process can be found at http://docs.apcera.com/tutorials/create-package/

## How To Contribute

* Fork the `apcera/package-scripts` directory.
* Make your changes. This could be creating new conf files, or editing existing confs.
* Send us a pull request.
