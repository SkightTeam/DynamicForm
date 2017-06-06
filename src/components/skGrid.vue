<template lang="pug">
  table
    thead
      tr
        th(v-for="schema_item in schema") {{schema_item.name}}
        th Action
    tbody
      tr(v-for="record in value")
        td(v-for="schema_item in schema") {{record[schema_item.code]}}
        td
         button Delete
      tr
        td(v-for="item in schema")
          sk-edit-scalar(v-model="fields[item.code]" v-bind:meta="item")
        td
          button(@click="submit") Add
</template>

<script>
import SkEditScalar from './skEditScalar'
export default {
  components: {
    SkEditScalar
  },
  name: 'SkGrid',
  props: [
    'schema',
    'value'
  ],
  data: function () {
    var fields = this.initFields()
    return {
      fields: fields
    }
  },
  methods: {
    initFields: function () {
      var fields = {}
      this.schema.forEach(function (item) {
        fields[item.code] = null
      })
      return fields
    },
    submit: function () {
      this.$emit('submit', this.fields)
      this.fields = this.initFields()
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  table {
    width: 100%;
    border-collapse: collapse;
  }
  table {
    border: 1px solid #000;
    border-width: 1px 1px;
  }

   tr > td {
    border: 1px solid #000;
    border-width: 1px 1px;
  }

</style>
