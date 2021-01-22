# Example of Backend using JSON-SERVER lib

json-server is a dependency that allow create an backend with json and expose REST API to request that objects.

### How to create
1- Create a folder of your project and then execute the command cd folder 
```
mkdir backend-json-server-demo && cd backend-json-server-demo
```
2- execute npm init -y to create the package.json
```
$ backend-json-server-demo npm init -y                
Wrote to /backend-json-server-demo/package.json:

{
  "name": "backend-json-server-demo",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}
```
3- npm i json-server to install the json-server. This dependency will be saved in the package.json in the "dependencies": object.
```
$ backend-json-server-demo npm i json-server
npm notice created a lockfile as package-lock.json. You should commit this file.
npm WARN backend-json-server-demo@1.0.0 No repository field.

+ json-server@0.16.3
added 183 packages from 80 contributors in 22.279s

12 packages are looking for funding
  run `npm fund` for details
```
4- Create a json file that will be our "backend". For this demo I created the db.json file with this objects:
```
{
  "products": [
    {
      "id": 1,
      "name": "Iphone 12 pro",
      "price": 1000
    },
    {
      "id": 2,
      "name": "Epson Printer",
      "price": 50.99
    },
    {
      "id": 3,
      "name": "Samsung S20",
      "price": 690
    },
    {
      "id": 4,
      "name": "Headphone Sony",
      "price": 237
    }
  ]
}
```
5 - Add an script in package.json to start the json-server
```
   "scripts": {
    "start": "json-server --watch db.json --port 3001"
  },
```
--watch is a flag to watch the db.json file to know if is changed
--port is a flag to indicate the port that json-server will be use (in this demo 3001)

6 - Execute npm start in a terminal and the json-server starts and show you a REST API created:
```
$ backend-json-server-demo npm start

> backend-json-server-demo@1.0.0 start /backend-json-server-demo
> json-server --watch db.json --port 3001


  \{^_^}/ hi!

  Loading db.json
  Done

  Resources
  http://localhost:3001/products

  Home
  http://localhost:3001

  Type s + enter at any time to create a snapshot of the database
  Watching...
```

If you execute the endpoint: http://localhost:3001/products in the web browser will see all object of products created in the db.json file