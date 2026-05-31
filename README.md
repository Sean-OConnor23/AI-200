# AI-200
Coding Exercises found within the Microsoft Learn path of the AI-200 exam

## Exercises
1. Build and run a container image with ACR Tasks

## Az breakdown
```mermaid
graph TD
    Root[my-app/] --> Src[src/]
    Root --> Public[public/]

    subgraph SrcGroup [Source Files - Core App Logic]
        Src --> Components[components/]
        Src --> App[App.js]
    end

    subgraph PublicGroup [Public Assets - Served Raw to Browser]
        Public --> Index[index.html]
        Public --> Fav[favicon.ico]
    end
```

