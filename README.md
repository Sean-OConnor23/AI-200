# AI-200
Coding Exercises found within the Microsoft Learn path of the AI-200 exam

## Exercises
1. Azure Container Registry
   - Build and Run a Container Image With ACR Tasks
2. Azure App Service
   - Deploy a Container to Azure App Service
      * Deploy a Linux container image from ACR to Azure App Service

## Az CLI Breakdown
```text
az
├── login ..................................... Login to Azure account
├── provider .................................. Manage resource providers
│   └── register .............................. Register a provider
│         └── --namespace -n [Required] ....... The resource namespace
├── role .................................. Manage Azure role-based access control (Azure RBAC).
│   └── assignment .............................. Manage role assignments.
│         └── create ....... Create a new role assignment for a user, group, or service principal.
|               ├── --assignee ... Represent a user, group, or service principal. supported format: object id, user sign-in name, or service principal name.
|               ├── --scope [Required] ....  Scope at which the role assignment or definition applies to.
|               └── --role [Required] ..... Role name or id.
├── monitor .................................. Manage the Azure Monitor Service.
│   └── log-analytics .............................. Manage Azure log analytics.
│         └── query ....... Query a Log Analytics workspace.
|               ├── --workspace -w [Required] ... GUID of Log Analytics workspace
|               ├── --analytics-query [Required] .... Query to execute over Log Analytics data.
|               └── --output -o ..... Output format (json [default], jsonc, none, table, tsv, yaml, yamlc)
├── extension .................................. Manage and update CLI extensions.
│   └── add .............................. Add an extension.
│         └── --name ....... Name of extension
├── group ..................................... Manage resource groups and template deployments
│   └── delete ................................ Delete a resource group
│         ├── --name --resource group -g -n [Required] ....... Name of resource group
│         ├── --yes -y ........................ Do not prompt for confirmation (No additional param)
│         └── --no-wait ....................... Do not wait for the long-running operation to finish (No additional param)
├── acr ....................................... Manage private registries with Azure Container Registries
│    ├── show ................................ Gets the details of an ACR
│    │     ├── --resource-group -g ....... Name of resource group.
│    │     ├── --query ....... JMESPath query string.
│    │     ├── --output ....... Output format (json [default], jsonc, none, table, tsv, yaml, yamlc)
│    │     └── --name -n [Required] ..................... Name of the container registry.
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
|    |     └── list-metadata .................. List the metadata of the manifests in the repo in an ACR
|    |          ├── --registry -r ............. Name of container registry
|    |          ├── --output -o ............... Output format (json [default], jsonc, none, table, tsv, yaml, yamlc)
|    |          └── --name -n ................. Name of the repository
│    ├── run .................................. Queues a quick run providing streamed logs for an ACR
|    |    ├── --registry -r [Required] ........ Name of container registry (specified in lower case)
|    |    └── --cmd ........................... Commands to execute. Also supports additional docker run parameters
│    └── task ................................. Manage a collection of steps for building, testing and OS & Framework patching container images using ACR
|          └── list-runs ...................... List all of the executed runs for an ACR, with the ability to filter by a specific Task
|               ├── --registry -r ............. Name of container registry (specified in lower case)
|               └── --output -o ............... Output format (json [default], jsonc, none, table, tsv, yaml, yamlc)
├── webapp ....................................... Manage web apps
│    ├── create ................................ Create a web app
│    │     ├── --resource-group -g [Required] ....... Name of resource group
│    │     ├── --plan -p [Required] ....... Name or resource id of the app service plan. Use 'appservice plan create' to get one.
│    │     ├── --name -n [Required] ....... Name of the new web app.
│    │     └── --container-image-name -c ..................... The container custom image name and optionally the tag name 
│    ├── identity ................................. Manage web app's managed identity.
|    |     ├── assign ...................... Assign managed identity to the web app
|    |     |    ├── --resource-group -g ............. Name of resource group. 
|    |     |    └── --name -n ............... Name of web app
|    |     └── show ...................... Display web app's managed identity.
|    |          ├── --resource-group ............. Name of resource group
|    |          ├── --name ............... Name of web app
|    |          ├── --query ............. JMESPath query string
|    |          └── --output ............... Output format (json [default], jsonc, none, table, tsv, yaml, yamlc)
│    ├── config ................................. Configure a web app.
|    |     ├── set ...................... Set a web app's configuration
|    |     |    ├── --resource-group -g ............. Name of resource group.
|    |     |    ├── --acr-use-identity ............. Enable or disable pull image from acr use managed identity. Allowed values: false, true.
|    |     |    ├── --acr-identity ............. Accept system or user assigned identity which will be set for acr image pull.
|    |     |    ├── --always-on ............. Ensure web app gets loaded all the time, rather unloaded after been idle. Recommended when you have continuous web jobs running.
|    |     |    └── --name -n ............... Name of web app.
|    |     ├── container ...................... Manage an existing web app's container settings
|    |     |    └── set ............. Set an existing web app's container settings.
|    |     |         ├── --resource-group -g ..........Name of a resource group
|    |     |         ├── --name -n ....... Name of the web app
|    |     |         ├── --container-image-name -c -i .........The container custom image name and optionally the tag name
|    |     |         └── --container-registry-url -r ..... The container registry server url.
|    |     └── appsettings ...................... Configure web app settings. Updating or removing application settings will cause an app recycle.
|    |          ├── set ............. Set the web app's settings
|    |          |    ├── --resource-group -g ..... Name of resource group
|    |          |    ├── --name -n ....... Name of the web app
|    |          |    └── --settings ...... Space-separated appsettings in KEY=VALUE format. Use @{file} to load from a file.
|    |          └── list ............. Get the details of a web app's settings
|    |               ├── --resource-group -g [Required] .... Name of resource group
|    |               ├── --name -n [Required] .... Name of the web app
|    |               └── --output -o ..... Output format (json [default], jsonc, none, table, tsv, yaml, yamlc)
│    └── log ................................. Manage web app logs.
|          ├── config ...................... Configure logging for a web app
|          |    ├── --resource-group -g ............. Name of the resource group
|          |    ├── --docker-container-logging ............. Configure gathering STDOUT and STDERR output from container. Allowed values: filesystem, off.
|          |    └── --name -n ............... Name of the web app.
|          └── tail ...................... Start live log tracing for a web app
|               ├── --resource-group -g ............. Name of the resource group
|               └── --name -n ............... Name of the web app
├── containerapp .................................. Manage Azure Container Apps.
│    ├── create .............................. Create a container app.
|    |     ├── --resource-group -g [Required] ............. Name of the resource group
|    |     ├── --environment ............. Name or resource ID of the container app's environment.
|    |     ├── --image ............. Container image
|    |     ├── --ingress ............. The ingress type (external, internal)
|    |     ├── --target-port ............. The application port used for ingress traffic
|    |     ├── --env-vars ............. A list of environment variables for the container
|    |     ├── --registry-server ............. The container registry server hostname.
|    |     ├── --registry-identity ............. The managed identity with which to authenticate to the Azure Container Registry
|    |     └── --name -n [Required] ............... Name of the container app.
│    ├── secret ................................. Commands to manage secrets.
|    |     └──  set ...................... Create/update secrets
|    |          ├── --resource-group -g ............. Name of resource group.
|    |          ├── --secrets -s [Required] ............. A list of secrets for the container app.  
|    |          └── --name -n ............... Name of container app.
│    ├── update .............................. Update a container app. In multiple revisions mode, create a new revision based on the latest revision.
|    |     ├── --resource-group -g ............. Name of the resource group
|    |     ├── --set-env-vars ............. Add or update environment variable(s) in container. Existing environment variables are not modified.
|    |     ├── --remove-env-vars ............. Remove environment variable(s) from container.
|    |     ├── --min-replicas ............. The minimum number of replicas
|    |     ├── --max-replicas ............. The maximum number of replicas
|    |     ├── --scale-rule-name --srn ............. The name of the scale rule
|    |     ├── --scale-rule-type --srt ............. The type of the scale rule
|    |     ├── --scale-rule-http-concurrency --srhc ............. Maximum number of concurrent requests before scale out
|    |     ├── --yaml ............. Path to a .yaml file with the configuration of a container app.
|    |     └── --name -n ............... Name of container app.
│    ├── revision ................................. Commands to manage revisions.
|    |     └──  list ...................... List a container app's revisions.
|    |          ├── --resource-group -g [Required] ............. Name of resource group.
|    |          ├── --ouput -o ............. Output format (json [default], jsonc, none, table, tsv, yaml, yamlc). 
|    |          └── --name -n [Required] ............... Name of container app.
│    ├── show .............................. Show details of container app.
|    |     ├── --resource-group -g ............. Name of the resource group
|    |     ├── --output -o ............. Output format (json [default], jsonc, none, table, tsv, yaml, yamlc)
|    |     ├── --query ............. JMESPath query string.
|    |     └── --name -n ............... Name of container app
│    ├── logs ................................. Show container app logs.
|    |     └──  show ...................... Show past logs and/or print logs in real time
|    |          ├── --resource-group -g [Required] ............. Name of resource group.
|    |          └── --name -n [Required] ............... Name of container app
│    ├── ingress ................................. Commands to manage ingress and traffic-splitting.
|    |     └──  update ...................... Update ingress for a container app.
|    |          ├── --resource-group -g ............. Name of resource group.
|    |          ├── --target-port ............. The application port used for ingress traffic.
|    |          └── --name -n ............... Name of container app
│    └── env ................................. Commands to manage Container Apps environments.
|          └──  show ...................... Show details of a Container Apps environment.
|               ├── --resource-group -g ............. Name of resource group.
|               ├── --query ............. JMESPath query string.
|               ├── --output ............. Output format (json [default], jsonc, none, table, tsv, yaml, yamlc)
|               └── --name -n ............... Name of container app's environment
├── aks .................................. Azure Kubernetes Service
│    ├── create .............................. Create a new managed Kubernetes cluster
|    |     ├── --resource-group -g [Required] ............. Name of the resource group
|    |     ├── --node-count -c ............. Number of nodes in the Kubernetes node pool.
|    |     ├── --node-vm-size -s ............. Size of Virtual Machines to create as Kubernetes nodes
|    |     ├── --vm-set-type ............. Agent pool vm set type. 
|    |     ├── --load-balancer-sku ............. Azure Load Balance SKU selection for your cluster.
|    |     ├── --enable-managed-identity ............. Using a system-assigned managed identity to manage cluster resource group.
|    |     ├── --network-plugin ............. The kubernetes plugin to use.
|    |     ├── --no-ssh-key -x ............. Do not use or create a local SSH key.
|    |     ├── --attach-acr ............. Grant the 'acrpull' role assignment to the ACR specified by name or resource ID.
|    |     └── --name -n [Required] ............... Name of the managed cluster.
│    ├── wait .............................. Wait for a managed Kubernetes cluster to reach a desired state.
|    |     ├── --resource-group -g [Required] ............. Name of the resource group.
|    |     ├── --updated............. Wait until updated with provisioningState at 'Suceeded'.
|    |     └── --name -n [Required] ............... Name of the managed cluster.
│    ├── get-credentials .............................. Get access credentials for a managed Kubernetes cluster.
|    |     ├── --resource-group -g [Required] ............. Name of the resource group
|    |     ├── --overwrite-existing ............. Overwrite any existing cluster entry with the same name.
|    |     └── --name -n [Required] ............... Name of the managed cluster.
│    ├── show .............................. Show the details for a managed Kubernetes cluster.
|    |     ├── --resource-group -g [Required] ............. Name of the resource group
|    |     ├── --output -o ............. Output format (json [default], jsonc, none, table, tsv, yaml, yamlc)
|    |     ├── --query ............. JMESPath query string.
|    |     └── --name -n [Required] ............... Name of the managed cluster.
```

## Kubectl CLI Breakdown
```text
kubectl
├── get ..................................... Display one or many resources.
├── rollout .................................. Manage the rollout of a resource
│   └── status .............................. Show the status of the rollout
├── apply .................................. Apply a configuration to a resource by file name or stdin
|   ├── --filename -f ...................... The files that contain the configurations to apply.
│   └── --namespace -n .............................. Tells command which specific workspace inside K Cluster to target
```
### "Az provider register --namespace" values used
1. Microsoft.ContainerRegistry
2. Microsoft.Web
3. Microsoft.OperationalInsights
4. Microsoft.App
5. Microsoft.CognitiveServices
6. Microsoft.ContainerService
7. Microsoft.Compute
8. Microsoft.Network
9. Microsoft.Storage

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



