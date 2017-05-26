<template >
  <input ref="input" v-bind:value="value" v-on:input="update($event.target.value)"/>
</template>

<script>
export default {
  name: 'SkEditScalar',
  props: [
    'value'
  ],
  methods: {
    update: function (value) {
      this.$emit('input', value)
    }
  }
}
</script>

