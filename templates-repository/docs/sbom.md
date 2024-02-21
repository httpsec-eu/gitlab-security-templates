# Documentation for using the sbmo.yml template

## Parameters:

|Name| Default Value| Description |
|-|-|-|
|stage| security-dependency-sbom | The stage where the job will run| 
...


## Usage

```yaml
include:
	- project: 'denis.rendler/templates-test'
	  file: '/templates/sbom.yml'
	  ref: 0.1
	  inputs:
		  stage: testing
```