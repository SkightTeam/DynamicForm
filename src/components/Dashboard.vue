<template lang="pug" >
  div
    h1 动态表单编辑器
    h2 Skight I-Tech Inc.
    div
      div(style="width:30%; display:inline-block")
        h3 增加字段
        sk-form(:meta="metaSchema" v-on:submit="addField")
      div(style="width:70%; display:inline-block; ")
        h3 数据结构
        sk-list(v-bind:schema="metaSchema" v-bind:value="meta")
    hr
    div
      div(style="width:30%; display:inline-block")
        h3 增加数据
        sk-form(:meta="meta" v-on:submit="addRecord")
      div(style="width:70%; display:inline-block;")
        h3 数据
        sk-list(v-bind:schema="meta" v-bind:value="data")
</template>

<script>
  import SkForm from './skForm'
  import SkList from './skList'
  var meta = []
  var data = []
  export default {
    name: 'Dashboard',
    components: {
      SkList, SkForm
    },
    data () {
      return {
        metaSchema: [
          {
            code: 'code',
            name: '编码',
            type: 'string'
          },
          {
            code: 'name',
            name: '名称',
            type: 'string'
          },
          {
            code: 'type',
            name: '类型',
            type: 'string'
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
