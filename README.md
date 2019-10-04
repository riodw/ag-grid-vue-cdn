# ag-grid-vue-cdn

how to:

## start
```
npm install -g @vue/cli
vue create my-project
```

```
enter
enter
y
```

## Install ag-grid
```
npm install --save ag-grid-community ag-grid-vue vue-property-decorator
```

## Go to the ag-grid-vue package
```
cd node_modules/ag-grid-vue/
```

## install ag-grid-vue's dependencies
```
npm install
```

## Create `tsconfig-lib.json`
```
nano tsconfig-lib.json
```

## past in json
```
// from here https://www.ag-grid.com/ag-grid-angular-webpack/#tsconfig-json
{
  "compilerOptions": {
    "target": "es5",
    "module": "commonjs",
    "moduleResolution": "node",
    "sourceMap": true,
    "emitDecoratorMetadata": true,
    "experimentalDecorators": true,
    "removeComments": false,
    "noImplicitAny": false,
    "lib": ["dom","es2015"]
  },
  "compileOnSave": true,
  "exclude": [
    "node_modules/*"
  ]
}
```

## clone ag-grid src
```
svn checkout https://github.com/ag-grid/ag-grid/trunk/packages/ag-grid-vue/src
```

## create `tsconfig.json`
```
nano tsconfig.json
```

## paste in json
```
// tsconfig.json
{
  "compilerOptions": {
    "target": "es5",
    "module": "commonjs",
    "moduleResolution": "node",
    "sourceMap": true,
    "emitDecoratorMetadata": true,
    "experimentalDecorators": true,
    "removeComments": false,
    "noImplicitAny": false,
    "lib": ["dom","es2015"]
  },
  "compileOnSave": true,
  "exclude": [
    "node_modules/*"
  ]
}
```

## DONE.
You should have these files in the `dist/` folder
```
ag-grid-vue.common.js		ag-grid-vue.umd.js		ag-grid-vue.umd.min.js		demo.html
ag-grid-vue.common.js.map	ag-grid-vue.umd.js.map		ag-grid-vue.umd.min.js.map
```

## will need to modify the `ag-grid-vue.umd.min.js` file


-------------------------------------------
#### Notes
https://stackoverflow.com/questions/7106012/download-a-single-folder-or-directory-from-a-github-repo
