<template >
 <div>
   <div>
   <div v-for="item in meta">
     <label>{{item.name}}:</label>
     <sk-edit-scalar v-model="fields[item.code]"></sk-edit-scalar>
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
    var fields = this.initFields()
    return {
      fields: fields
    }
  },
  methods: {
    submit: function () {
      this.$emit('submit', this.fields)
      this.fields = this.initFields()
    },
    initFields: function () {
      var fields = {}
      this.meta.forEach(function (item) {
        fields[item.code] = null
      })
      return fields
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
