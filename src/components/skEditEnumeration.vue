<template >
  <select v-model="selected" @change="update">
    <option v-for="item in meta.enumerations" :value="item.code" :selected="item.code==value">{{ item.name }}</option>
  </select>
</template>

<script>
export default {
  name: 'SkEditEnumeration',
  props: [
    'meta',
    'value'
  ],
  data: function () {
    return {
      selected: this.value
    }
  },
  methods: {
    update: function () {
      this.$emit('input', this.selected)
    }
  }
}
</script>

