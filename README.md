# ag-grid-vue-cdn

_Link to file to include_

https://github.com/riodw/ag-grid-vue-cdn/blob/master/node_modules/ag-grid-vue/dist/ag-grid-vue.umd.js

## How to:

### Create slut repository

```shell
npm install -g @vue/cli
vue create my-project
```

```shell
enter
enter
y
```

### Install ag-grid

```shell
npm install --save ag-grid-community ag-grid-vue vue-property-decorator
```

### Go to the ag-grid-vue package

```shell
cd node_modules/ag-grid-vue/
```

### Install ag-grid-vue's dependencies

```shell
npm install
```

### Create `tsconfig-lib.json`

```shell
nano tsconfig-lib.json
```

### Paste in json

```json
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
    "lib": ["dom", "es2015"]
  },
  "compileOnSave": true,
  "exclude": ["node_modules/*"]
}
```

### Clone ag-grid src

```shell
svn checkout https://github.com/ag-grid/ag-grid/trunk/packages/ag-grid-vue/src
```

### Create `tsconfig.json`

```shell
nano tsconfig.json
```

### Paste in json

```json
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
    "lib": ["dom", "es2015"]
  },
  "compileOnSave": true,
  "exclude": ["node_modules/*"]
}
```

You should have these files in the `dist/` folder

```shell
ag-grid-vue.common.js
ag-grid-vue.common.js.map
ag-grid-vue.umd.js
ag-grid-vue.umd.js.map
ag-grid-vue.umd.min.js
ag-grid-vue.umd.min.js.map
demo.html
```

## will need to modify the `ag-grid-vue.umd.min.js` file

put `window.AgGridVue = AgGridVue;` above every where it says `return AgGridVue;`

```
window.AgGridVue = AgGridVue;
return AgGridVue;
```

#### include ag-grid-vue.umd.min.js in yo project

You can now use AgGridVue

## EXAMPLE

```html
<div id="app">
  demo
  <vuejs-datepicker
    input-class="form-control"
    placeholder="Start Date"
  ></vuejs-datepicker>
  <div></div>
  <div style="height: 140px; width: 650px;">
    <ag-grid-vue
      class="ag-theme-balham w-100 h-100"
      :columnDefs="columnDefs"
      :rowData="rowData"
    >
    </ag-grid-vue>
  </div>
</div>

<!-- Datepicker -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/vuejs-datepicker/1.6.2/vuejs-datepicker.min.js"></script>
<!-- Ag-Grid -->
<script
  src="https://cdnjs.cloudflare.com/ajax/libs/ag-grid/21.2.1/ag-grid-community.min.js"
  crossorigin="anonymous"
></script>
<script src="path/to/global/js/ag-grid-vue.umd.js"></script>
<script>
  var app = new Vue({
    delimiters: ["[[", "]]"],
    el: "#app",
    components: {
      // Datepicker
      vuejsDatepicker,
      // Table
      AgGridVue
    },
    data: {
      columnDefs: [
        { headerName: "Make", field: "make" },
        { headerName: "Model", field: "model" },
        { headerName: "Price", field: "price" }
      ],
      rowData: [
        { make: "Toyota", model: "Celica", price: 35000 },
        { make: "Ford", model: "Mondeo", price: 32000 },
        { make: "Porsche", model: "Boxter", price: 72000 }
      ]
    },
    mounted: function() {
      var vm = this;
    },
    methods: {},
    watch: {},
    filters: {}
  });
</script>
```

---

#### Notes

https://stackoverflow.com/questions/7106012/download-a-single-folder-or-directory-from-a-github-repo
