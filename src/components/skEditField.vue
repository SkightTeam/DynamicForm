<template >
  <sk-edit-enumeration v-if="meta.type=='enumeration'"
                       :value="value"
                       :meta="meta"
                       @input="update"
  ></sk-edit-enumeration>
  <sk-edit-scalar v-else
                  :value="value"
                  :meta="meta"
                  @input="update"
  ></sk-edit-scalar>
</template>

<script>
import SkEditEnumeration from './skEditEnumeration'
import SkEditScalar from './skEditScalar'

export default {
  components: {
    SkEditScalar,
    SkEditEnumeration},
  name: 'SkEditField',
  props: [
    'meta',
    'value'
  ],
  methods: {
    update: function (value) {
      this.$emit('input', value)
    }
  }
}
</script>

