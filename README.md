# Getting Started

Welcome to your new project.

It contains these folders and files, following our recommended project layout:

File or Folder | Purpose
---------|----------
`app/` | content for UI frontends goes here
`db/` | your domain models and data go here
`srv/` | your service models and code go here
`package.json` | project metadata and configuration
`readme.md` | this getting started guide


## Next Steps

- Open a new terminal and run `cds watch` 
- (in VS Code simply choose _**Terminal** > Run Task > cds watch_)
- Start adding content, for example, a [db/schema.cds](db/schema.cds).


## Steps to create the app

cds init bookstore
cds add samples
cds add data
npm add --save-dev cds-swagger-ui-express

You need a server.js file to integrate it in the bootstrap process:

```const cds = require ('@sap/cds')
module.exports = cds.server

if (process.env.NODE_ENV !== 'production') {
  const cds_swagger = require ('cds-swagger-ui-express')
  cds.on ('bootstrap', app => app.use (cds_swagger()) )
} 
```

Adjust package.json
```
,
  "cds": {
    "swagger": {
      "basePath": "/$api-docs", 
      "apiPath": "", 
      "diagram": true,
      "odataVersion": "4.0" 
    }
```


## Test with API Swagger 

http://localhost:4004/$api-docs/odata/v4/catalog/Books


## Test with API Directly .

http://localhost:4004/odata/v4/catalog/Books#/Books