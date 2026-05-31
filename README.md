# AI-200
Coding Exercises found within the Microsoft Learn path of the AI-200 exam

## Exercises
1. Build and run a container image with ACR Tasks

## Az breakdown
```text
az vm/
├── create ............................ Deploy a new virtual machine instance
│   ├── --name (-n) ................... Name of the virtual machine
│   ├── --resource-group (-g) ......... Target resource group container
│   ├── --image ....................... OS template (e.g., Ubuntu2204)
│   └── --generate-ssh-keys ........... Auto-builds and stores secure SSH keys
│
├── list .............................. List all available VMs
│   ├── --output (-o) ................. Format type: table, json, yaml, tsv
│   └── --query ....................... JMESPath filter string for JSON fields
│
└── stop .............................. Power off a running VM
    ├── --name (-n) ................... Name of the target virtual machine
    └── --no-wait ..................... Do not wait for the long action to finish
```


<!-- Copy/Paste to edit ASCII Tree
├──  (Middle item)
└──  (Last item)
│    (Vertical line)
─    (Horizontal line)
-->



