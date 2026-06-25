# AI-200
Coding Exercises found within the Microsoft Learn path of the AI-200 exam

## Exercises
1. Azure Container Registry
   - Build and Run a Container Image With ACR Tasks
2. Azure App Service
   - Deploy a Container to Azure App Service 

## Az CLI Breakdown
```text
az
├── login ..................................... Login to Azure account
├── provider .................................. Manage resource providers
│   └── register .............................. Register a provider
│         └── --namespace -n [Required] ....... The resource namespace
├── group ..................................... Manage resource groups and template deployments
│   └── delete ................................ Delete a resource group
│         ├── --name --resource group -g -n [Required] ....... Name of resource group
│         ├── --yes -y ........................ Do not prompt for confirmation (No additional param)
│         └── --no-wait ....................... Do not wait for the long-running operation to finish (No additional param)
├── acr ....................................... Manage private registries with Azure Container Registries
│    ├── build ................................ Queues a quick build, providing streaming logs for an ACR
│    │     ├── --registry -r [Required] ....... Name of container registry (specified in lower case)
│    │     └── --image -t ..................... Name and tag of image using the format '-t repo/image:tag' (Multiple tags are supported by passing -t multiple times)
│    ├── repository ........................... Manage repositories for ACR
|    |     ├── list ........................... List repos in an ACR
|    |     |    ├── --name -n [Required] ...... Name of container registry (specified in lower case)
|    |     |    └── --output -o ............... Output format (json [default], jsonc, none, table, tsv, yaml, yamlc)
|    |     ├── update ......................... Update the attributes of a repo or image in an ACR
|    |     |    ├── --name -n [Required] ...... Name of container registry (specified in lower case)
|    |     |    ├── --image -t ................ Name of image. Format: 'name:tag' or 'name@digest' 
|    |     |    └── --write-enabled ........... Indicates whether write or delete operation is allowed (true/false)
|    |     ├── show ........................... Get the attributes of a repo or image in an ACR
|    |     |    ├── --name -n [Required] ...... Name of container registry (specified in lower case)
|    |     |    └── --image -t ................ Name of image. Format: 'name:tag' or 'name@digest'
|    |     └── show-tags ...................... Show tags for a repository in an ACR
|    |          ├── --name -n [Required] ...... Name of container registry (specified in lower case)
|    |          ├── --repository -r [Required]. The name of the repository
|    |          └── --output -o ............... Output format (json [default], jsonc, none, table, tsv, yaml, yamlc)
│    ├── manifest ............................. Manage artifact manifests in ACR
|    |     ├── list-metadata .................. List the metadata of the manifests in the repo in an ACR
|    |     |    ├── --registry -r ............. Name of container registry
|    |     |    ├── --output -o ............... Output format (json [default], jsonc, none, table, tsv, yaml, yamlc)
|    |     |    └── --name -n ................. Name of the repository
│    ├── run .................................. Queues a quick run providing streamed logs for an ACR
|    |    ├── --registry -r [Required] ........ Name of container registry (specified in lower case)
|    |    └── --cmd ........................... Commands to execute. Also supports additional docker run parameters
│    ├── task ................................. Manage a collection of steps for building, testing and OS & Framework patching container images using ACR
|    |     ├── list-runs ...................... List all of the executed runs for an ACR, with the ability to filter by a specific Task
|    |     |    ├── --registry -r ............. Name of container registry (specified in lower case)
|    |     |    └──  --output -o ............... Output format (json [default], jsonc, none, table, tsv, yaml, yamlc)
```


<!-- Copy/Paste to edit ASCII Tree
├──  (Middle item)
└──  (Last item)
│    (Vertical line)
─    (Horizontal line)
1. Azure Container Registry
   - Build and Run a Container Image With ACR Tasks
      * **Feature Authentication:** Secure login system.
       This module handles all user sign-ups, password resets, and session management using JWT tokens.
      * **Feature Dashboard:** Main user interface.
2. Azure App Service
   - Deploy a Container to Azure App Service
-->



