## Node.js

These settings apply only when `--nodejs` is specified on the command line.
Please also specify `--node-sdks-folder=<path to root folder of your azure-sdk-for-node clone>`.

``` yaml $(nodejs)
nodejs:
  add-credentials: true
  package-name: azure-appinsights
  package-version: 0.9.0-preview
  output-folder: $(node-sdks-folder)/lib/services/appinsights-client
  payload-flattening-threshold: 1
  generate-license-txt: true
  generate-package-json: true
  generate-readme-md: false
```