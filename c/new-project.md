# New Project

## Starting a new project

```bash
# creates a new console project inside opened directory
dotnet new console

# restores any dependencies needed to run the project
dotnet restore

# run project in console(terminal)
dotnet run
```

## 

In the **terminal** cd into desired directory. Type following code to start a new project.

```bash
# First make new directory for application
mkdir <appName>

# dotnet new - Starts new .net project
# mvc - Model, View, Controller
# --auth - The type of authentication to use
# Individual - Individual authentication
dotnet new mvc --auth Individual
```

