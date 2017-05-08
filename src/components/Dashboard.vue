<template >

 <div>
   <h1>动态表单编辑器</h1>
   <sk-form :meta="schema"></sk-form>
 </div>
</template>

<script>
  import SkForm from './skForm'
  export default {
    name: 'Dashboard',
    components: {
      SkForm
    },
    data () {
      return {
        schema: [
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
</style>
