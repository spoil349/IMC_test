# imc-test

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

### Testing
For testing was used JSON-server (https://www.npmjs.com/package/json-server)
1. install json server
```
npm install -g json-server
```
2. create a 'db.json' file in any directory, with data from test-task
3. start json server from this directory
```
json-server --watch db.json
```
