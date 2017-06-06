<template lang="pug" >
  div
    h1 Dynamic Form Editor
      sub Demo by
        a(href="www.skight.ca") Skight I-Tech Inc.
    div
      div(style="width:30%; display:inline-block")
        h3 Add Field
        sk-form(:meta="enumSchema" v-on:submit="addField")
      div(style="width:70%; display:inline-block; ")
        h3 Schema
        sk-list(v-bind:schema="enumSchema" v-bind:value="meta")
    hr
    div
      div(style="width:30%; display:inline-block")
        h3 Add Record
        sk-form(:meta="meta" v-on:submit="addRecord")
      div(style="width:70%; display:inline-block;")
        h3 Data
        sk-grid(v-bind:schema="meta" v-bind:value="data" v-on:submit="addRecord")
</template>

<script>
  import SkForm from './skForm'
  import SkList from './skList'
  import SkGrid from './skGrid'
  var meta = []
  var data = []
  export default {
    name: 'Dashboard',
    components: {
      SkGrid,
      SkList,
      SkForm
    },
    data () {
      return {
        metaSchema: [
          {
            code: 'code',
            name: 'Code',
            type: 'scalar'
          },
          {
            code: 'name',
            name: 'Name',
            type: 'scalar'
          },
          {
            code: 'type',
            name: 'Type',
            type: 'enumeration',
            enumerations: [
              {
                code: 'scalar',
                name: 'Scalar Type'
              },
              {
                code: 'enumeration',
                name: 'Enumeration Type'
              }
            ]
          }
        ],
        enumSchema: [
          {
            code: 'code',
            name: 'Code',
            type: 'scalar'
          },
          {
            code: 'name',
            name: 'Name',
            type: 'scalar'
          },
          {
            code: 'type',
            name: 'Type',
            type: 'enumeration',
            enumerations: [
              {
                code: 'scalar',
                name: 'Scalar Type'
              },
              {
                code: 'enumeration',
                name: 'Enumeration Type'
              }
            ]
          },
          {
            code: 'enumerations',
            name: 'Enumerations',
            type: 'list',
            ofType: [
              {
                code: 'code',
                name: 'Code',
                type: 'scalar'
              },
              {
                code: 'name',
                name: 'Name',
                type: 'scalar'
              }
            ]
          }
        ],
        meta: meta,
        data: data
      }
    },
    methods: {
      addField: function (fieldMeta) {
        meta.push(fieldMeta)
      },
      addRecord: function (record) {
        data.push(record)
      }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1, h2 {
    font-weight: normal;
  }
</style>
