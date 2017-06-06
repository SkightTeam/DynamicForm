<template >
  <sk-grid v-bind:schema="meta.ofType" v-bind:value="value" v-on:submit="addRecord"> </sk-grid>
</template>

<script>
import SkGrid from './skGrid'
export default {
  components: {SkGrid},
  name: 'SkEditFieldOfList',
  props: [
    'meta',
    'value'
  ],
  methods: {
    addRecord: function (fields) {
      this.value.push(fields)
    }
  }
}
</script>

