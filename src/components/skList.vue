<template lang="pug">
  table
    thead
      tr
        th(v-for="schema_item in schema") {{schema_item.name}}
    tbody
      tr(v-for="record in value")
        td(v-for="schema_item in schema") {{record[schema_item.code]}}
</template>

<script>
export default {
  name: 'SkList',
  props: [
    'schema',
    'value'
  ]
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
