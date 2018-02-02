<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div id="vueapp" class="vue-app">
      <kendo-grid :data-source="localDataSource"
                  v-on:databinding="onDataBinding"
                  v-on:databound="onDataBound">
      </kendo-grid>
    </div>
  </div>
</template>

<script>
import { Grid, GridInstaller } from '@progress/kendo-grid-vue-wrapper'

export default {
  name: 'HelloWorld',
  methods: {
        onDataBinding: function (ev) {
            console.log("Grid is about to be bound!");
        },
        onDataBound: function (ev) {
            console.log("Grid is now bound!");
        }
    },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      localDataSource: [{
                "ProductID": 1,
                "ProductName": "Chai",
                "UnitPrice": 18,
                "UnitsInStock": 39,
                "Discontinued": false,
            },
            {
                "ProductID": 2,
                "ProductName": "Chang",
                "UnitPrice": 17,
                "UnitsInStock": 40,
                "Discontinued": false,
            },
            {
                "ProductID": 3,
                "ProductName": "Aniseed Syrup",
                "UnitPrice": 10,
                "UnitsInStock": 13,
                "Discontinued": false,
            }
        ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
