<template>
  <div class="">
      <InputTag v-model="tags" @input="onChange"/>
  </div>
</template>


<script>

import InputTag from 'vue-input-tag'

export default {
  name: "MyComponent",
  props: ['value', 'element', 'model', 'config'], // here we get the data passed. The value is the viewModel
  data: function () {
    return {
      tags: ['A']
    };
  },
  components: {
    'InputTag': InputTag
  },
  methods: {
    onChange (e) {
      // write the changes back
      this.value.tags = e
    }
  },
  mounted () {
    // read the tags from the viewModel
    this.tags = this.value.tags
  }

};
</script>
