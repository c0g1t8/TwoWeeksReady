# TwoWeeksReady API

[![Build Status](https://github.com/HTBox/TwoWeeksReady/workflows/Api%20CI%2FCD/badge.svg)](https://github.com/HTBox/TwoWeeksReady/actions?query=workflow%3A"Api+CI%2FCD")

## Prerequisites

[.NET Core SDK 3.1](https://dotnet.microsoft.com/download)

[Azure Functions Core Tools 3](https://docs.microsoft.com/en-us/azure/azure-functions/functions-run-local?tabs=windows%2Ccsharp%2Cbash#install-the-azure-functions-core-tools)

  `npm i -g azure-functions-core-tools@3 --unsafe-perm true`

### Setup Azure CosmosDB
For local development, you can run the [Azure Cosmos DB Emulator](https://docs.microsoft.com/azure/cosmos-db/local-emulator) if you are developing on Windows. If not, you will need to create a CosmosDB instance in your own Azure account. You can use the [Azure ComsoDB Free Tier](https://docs.microsoft.com/azure/cosmos-db/optimize-dev-test#azure-cosmos-db-free-tier)

### Create a local.settings.json

Create a `local.settings.json` file in the TwoWeeksReady project folder. You will need to set the CosmosDbConnection setting to your own CosmosDB instance.

```Javascript
{
  "IsEncrypted": false,
  "Values": {
    "FUNCTIONS_WORKER_RUNTIME": "dotnet",
    "OidcApiAuthorizationSettings:Audience": "https://2wrdev.azurewebsites.net",
    "OidcApiAuthorizationSettings:IssuerUrl": "https://dev-3y6ze-l0.us.auth0.com/"
  },
  "ConnectionStrings": {
    "CosmosDBConnection": "AccountEndpoint=https://localhost:8081/;AccountKey=YOURLOCALACCOUNTKEY"
  },
  "Host":{
    "CORS": "*"
  }
}
```


## Development Workflow

### Compile

``` console
dotnet build
```

### Run from the command line

``` console
func start --build
```

### Debug from VS Code menu

F5
