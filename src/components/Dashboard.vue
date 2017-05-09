<template >

 <div>
   <h1>动态表单编辑器</h1>
   <h2>Skight I-Tech Inc.</h2>
   <div>
   <sk-form :meta="metaSchema" v-on:submit="addField"></sk-form>
   </div>
   <div>
     <sk-form :meta="meta" ></sk-form>
   </div>
 </div>
</template>

<script>
  import SkForm from './skForm'
  var meta = []
  var data = {}
  export default {
    name: 'Dashboard',
    components: {
      SkForm
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
