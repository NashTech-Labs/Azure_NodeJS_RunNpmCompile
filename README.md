# Azure_NodeJS_RunNpmCompile
It lets you perform any necessary building/prep tasks for your project, prior to it being used in another project. This Template used for the build stage of nodeJS, which performs building tasks.

## Parameters:

The pipeline requires the following parameters to be defined:

| Name | type | Default | Required/Optional | Comments |
| :-------------: | :-------------: | ------------- | :-------------: | :-------------: |
| filePath | String | $(Build.SourcesDirectory) | Required | define the filepath or working directory for package.json. Youc can also pass arguements  if required |
| npmBuild | String | build  | Optional | The value depends on command specified in package.json. Youc can also pass arguements  if required |

These parameters provide multiple use case options for the template, enable/disable flags for the utilization of different templates as per the requirements.


## Use Cases

You can directly call a particular template as per the requirement. for example: 

  ```yaml
  # azure-pipeline.yml
  resources:
  repositories:
    - repository: Template
      type: github
      name: your_username/Azure_NodeJS_RunNpmCompile
      ref: <respective branch name>
      endpoint: 'githubServiceConnectioNname'

  steps:
  # passing the parameters
  - template: Azure_NodeJS_RunNpmCompile.yml
    parameters:
        filePath: ${{ parameters.filePath }} 
        npmBuild: ${{ parameters.npmBuild }}
        
Make sure to adjust the repository name, branch name, and parameter values according to your project's requirements.

  ```
