<template >
 <div>
   <div>
   <div v-for="item in meta">
     <label>{{item.name}}:</label>
     <sk-edit-scalar v-model="fieldSchema[item.code]"></sk-edit-scalar>
   </div>
   </div>
   <button @click="submit">submit</button>
 </div>
</template>

<script>
import SkEditScalar from './skEditScalar'
export default {
  components: {SkEditScalar},
  name: 'SkForm',
  props: [
    'meta'
  ],
  data () {
    return {
      fieldSchema: { }
    }
  },
  methods: {
    submit: function () {
      this.$emit('submit', this.fieldSchema)
      this.fieldSchema = {}
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
