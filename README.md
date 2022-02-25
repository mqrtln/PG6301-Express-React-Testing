Communication between frontend and backend
==========================================

* [x] Create frontend and backend
  * [x] root project with concurrently, prettier and husky
  * [x] client project with parcel, react, react-dom and react-router-dom
  * [x] server project with nodemon, express, body-parser, cookie-parser and dotenv
* [x] get endpoint in express
* [x] husky + prettier 
* [x] deploy to heroku 
  * [x] npm build => client npm install --include-dev && parcel && server npm install
  * [x] npm start => node server.js
* [x] Serve react app from Express
* [x] GET /api/login from front page
  * [x] Fetch data from server
  * [x] Loading time
  * [x] Handle error
* [ ] POST /api/login from login form
  * [ ] Loading time
  * [ ] Handle error
* [ ] Refactor and polish fetch and error handling
  * [ ] Custom React hook 'useLoader'

## Commands to get this up and running
### Root
```
npm init -y
npm install -D concurrently prettier husky
```

### Server
```
mkdir server
cd server
npm init -y
npm install -D nodemon
npm install -P express body-parser cookie-parser dotenv

```
### Client
```
mkdir client
cd client
npm init -y
npm install -D parcel
npm install -P react react-dom react-router-dom

```



## root package.json example
```
{
  "name": "pg6301-express-react-testing",
  "version": "1.0.0",
  "main": "index.js",
  "scripts": {
    "dev": "concurrently npm:dev:client npm:dev:server",
    "dev:client": "cd client && npm run dev",
    "dev:server": "cd server && npm run dev",
    "test": "echo \"Error: no test specified\" && exit 1",
    "prepare": "husky install",
    "pre-commit": "npm run prettier:check",
    "prettier:check": "prettier --check **/*.{js,jsx,ts,tsx}",
    "build": "npm run build:server && npm run build:client",
    "build:client": "cd client && npm run build",
    "build:server": "cd server && npm run build",
    "start": "cd server && npm start"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "concurrently": "^7.0.0",
    "husky": "^7.0.4",
    "prettier": "^2.5.1"
  }
}
{
  "name": "pg6301-express-react-testing",
  "version": "1.0.0",
  "main": "index.js",
  "scripts": {
    "dev": "concurrently npm:dev:client npm:dev:server",
    "dev:client": "cd client && npm run dev",
    "dev:server": "cd server && npm run dev",
    "test": "echo \"Error: no test specified\" && exit 1",
    "prepare": "husky install",
    "pre-commit": "npm run prettier:check",
    "prettier:check": "prettier --check **/*.{js,jsx,ts,tsx}",
    "build": "npm run build:server && npm run build:client",
    "build:client": "cd client && npm run build",
    "build:server": "cd server && npm run build",
    "start": "cd server && npm start"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "concurrently": "^7.0.0",
    "husky": "^7.0.4",
    "prettier": "^2.5.1"
  }
}
```

## client package.json example
```
{                                                                           
  "name": "client",                                                         
  "version": "1.0.0",                                                       
  "description": "",                                                        
  "scripts": {                                                              
    "dev": "parcel index.html",                                             
    "build": "npm install --include=dev && parcel build index.html",        
    "test": "echo \"Error: no test specified\" && exit 1"                   
  },                                                                        
  "keywords": [],                                                           
  "author": "",                                                             
  "license": "ISC",                                                         
  "devDependencies": {                                                      
    "parcel": "^2.3.2"                                                      
  },                                                                        
  "dependencies": {                                                         
    "react": "^17.0.2",                                                     
    "react-dom": "^17.0.2",                                                 
    "react-router-dom": "^6.2.1"                                            
  }                                                                         
}                                                                           
                                                                            
```


## server package.json example
```
{
  "name": "server",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "type": "module",
  "scripts": {
    "dev": "nodemon server.js",
    "start": "node server.js",
    "build": "npm install",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "nodemon": "^2.0.15"
  },
  "dependencies": {
    "body-parser": "^1.19.2",
    "cookie-parser": "^1.4.6",
    "dotenv": "^16.0.0",
    "express": "^4.17.3"
  }
}
```