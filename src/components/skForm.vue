<template >
 <div>
   <div v-for="item in meta">{{item.name}}</div>
 </div>
</template>

<script>
export default {
  name: 'SkForm',
  props: [
    'meta'
  ]
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1, h2 {
    font-weight: normal;
  }
</style>
