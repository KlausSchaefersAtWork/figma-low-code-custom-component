<template>
  <div class="home">
    <Figma :figma="figmaJSON" v-model="viewModel" :config="config"/>
<pre>{{viewModel}}</pre>

  </div>


</template>

<style>
  pre {
    position: fixed;
    right:0px;
    top:0px;
    background: orange;
    width: 200px;
    color:#fff;
  }
</style>

<script>
import Vue from "vue";
import Figma from "vue-low-code";
Vue.use(Figma);

// import JSON file for deployment
import app from './app.json'
import MyComponent from './MyComponent'

export default {
  name: "Home",
  data: function () {
    return {
      figmaJSON: app,
      figmaConfig: {
        figmaFile: "",
        figmaAccessKey: "",
      },
      viewModel: {
        tags: ['Klaus', 'was', 'here']
      },
      config: {
        responsive: [
          { value: "Desktop", label: "Desktop", types: ["desktop"] },
          { value: "Mobile", label: "Mobile", types: ["tablet", "mobile"] },
        ],
        components: {
          'MyComponent': MyComponent
        },
      },
    };
  },
  components: {},
  methods: {
    /**
     * Place your methods here
     */
  },
};
</script>
