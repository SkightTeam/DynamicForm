<template>
  <sk-edit-enumeration v-if="meta.type=='enumeration'"
                       :value="value"
                       :meta="meta"
                       @input="update"
  ></sk-edit-enumeration>
  <sk-edit-field-of-list v-else-if="meta.type=='list'"
                         :value="value"
                         :meta="meta"
                         @input="update"

  ></sk-edit-field-of-list>
  <sk-edit-scalar v-else
                  :value="value"
                  :meta="meta"
                  @input="update"
  ></sk-edit-scalar>
</template>

<script>
import SkEditEnumeration from './skEditEnumeration'
import SkEditScalar from './skEditScalar'
import SkEditFieldOfList from './skEditFieldOfList'

export default {
  components: {
    SkEditFieldOfList,
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

