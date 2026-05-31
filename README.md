# AI-200
Coding Exercises found within the Microsoft Learn path of the AI-200 exam

## Exercises
1. Build and run a container image with ACR Tasks

## Az breakdown
```mermaid
graph LR
    %% Styles for easy scanning
    classDef core fill:#0078d4,stroke:#fff,stroke-width:2px,color:#fff;
    classDef cmd fill:#1f2937,stroke:#0078d4,stroke-width:1px,color:#38bdf8,font-family:monospace;
    classDef desc fill:#f8fafc,stroke:#e2e8f0,stroke-dasharray: 5 5,color:#475569,font-size:12px;

    %% Core CLI Root
    AZ[az CLI]:::core

    %% --- LOGIN & CONFIG ---
    AZ --> LoginConfig[login / config]:::core
    
    LoginConfig --> c_login["az login"]:::cmd
    c_login -.-> d_login["Log in interactively to Azure"]:::desc
    
    LoginConfig --> c_account["az account set --sub"]:::cmd
    c_account -.-> d_account["Switch active subscription context"]:::desc

    %% --- RESOURCE GROUPS ---
    AZ --> RG[group]:::core
    
    RG --> c_rg_create["az group create"]:::cmd
    c_rg_create -.-> d_rg_create["Create a resource group container (-n -l)"]:::desc
    
    RG --> c_rg_list["az group list -o table"]:::cmd
    c_rg_list -.-> d_rg_list["List all groups in a clean text table"]:::desc

    %% --- VIRTUAL MACHINES ---
    AZ --> VM[vm]:::core
    
    VM --> c_vm_create["az vm create"]:::cmd
    c_vm_create -.-> d_vm_create["Deploy a new virtual machine instance"]:::desc
    
    VM --> c_vm_stop["az vm stop"]:::cmd
    c_vm_stop -.-> d_vm_stop["Power off a VM without deallocating it"]:::desc
```


