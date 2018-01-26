# HanaOnAzure

> see https://aka.ms/autorest

This is the AutoRest configuration file for HanaOnAzure.



---
## Getting Started 
To build the SDK for HanaOnAzure, simply [Install AutoRest](https://aka.ms/autorest/install) and in this folder, run:

> `autorest`

To see additional help and options, run:

> `autorest --help`
---

## Configuration



### Basic Information
These are the global settings for the HANA on Azure API.

``` yaml
title: HanaManagementClient
description: HANA on Azure Client
openapi-type: arm
tag: package-2017-11
azure-arm: true
```


### Tag: package-2017-11

These settings apply only when `--tag=package-2017-11` is specified on the command line.

``` yaml $(tag) == 'package-2017-11'
input-file:
- Microsoft.HanaOnAzure/preview/2017-11-03-preview/hanaonazure.json
```

### Tag: package-2017-06

These settings apply only when `--tag=package-2017-06` is specified on the command line.

``` yaml $(tag) == 'package-2017-06'
input-file:
- Microsoft.HanaOnAzure/preview/2017-06-15-preview/hanaonazure.json
```


# Code Generation


## Swagger to SDK

This section describes what SDK should be generated by the automatic system.
This is not used by Autorest itself.

``` yaml $(swagger-to-sdk)
swagger-to-sdk:
  - repo: azure-sdk-for-python
  - repo: azure-sdk-for-go
```

## Python

These settings apply only when `--python` is specified on the command line.
Please also specify `--python-sdks-folder=<path to the root directory of your azure-sdk-for-python clone>`.
Use `--python-mode=update` if you already have a setup.py and just want to update the code itself.

``` yaml $(python)
python-mode: create
python:
  azure-arm: true
  license-header: MICROSOFT_MIT_NO_VERSION
  payload-flattening-threshold: 2
  namespace: azure.mgmt.hanaonazure
  package-name: azure-mgmt-hanaonazure
  clear-output-folder: true
  package-version: 0.1.0
```
``` yaml $(python) && $(python-mode) == 'update'
python:
  no-namespace-folders: true
  output-folder: $(python-sdks-folder)/azure-mgmt-hanaonazure/azure/mgmt/hanaonazure
```
``` yaml $(python) && $(python-mode) == 'create'
python:
  basic-setup-py: true
  output-folder: $(python-sdks-folder)/azure-mgmt-hanaonazure
```

## Go

These settings apply only when `--go` is specified on the command line.

``` yaml $(go)
  license-header: MICROSOFT_APACHE_NO_VERSION
  namespace: hanaonazure
  clear-output-folder: true
```

### Go multi-api

``` yaml $(go) && $(multiapi)
batch:
  - tag: package-2017-06
  - tag: package-2017-11
```

### Tag: package-2017-11

These settings apply only when `--tag=package-2017-11 --go` is specified on the command line.
Please also specify `--go-sdk-folder=<path to the root directory of your azure-sdk-for-go clone>`.

``` yaml $(go) && $(tag) == 'package-2017-11'
output-folder: $(go-sdk-folder)/services/hanaonazure/mgmt/2017-11-03-preview/hanaonazure
```

### Tag: package-2017-06

These settings apply only when `--tag=package-2017-06 --go` is specified on the command line.
Please also specify `--go-sdk-folder=<path to the root directory of your azure-sdk-for-go clone>`.

``` yaml $(go) && $(tag) == 'package-2017-06'
output-folder: $(go-sdk-folder)/services/hanaonazure/mgmt/2017-06-15-preview/hanaonazure
```