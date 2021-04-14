<template>
   currentValue: {{modelValue}}
  <div style="display: flex; flex-direction: column; width: 200px;">
    <slot/>
  </div>
</template>

<script setup>
import { defineProps, defineEmit, provide, computed } from 'vue'

const props = defineProps(['modelValue'])
const emit = defineEmit(['update:modelValue'])

const emitValue = (value) => {
  emit('update:modelValue', value)
}

//currentValue needs to be a computed or it's not reactive otherwise
provide('select-control',  { emitValue, currentValue: computed(() => props.modelValue) })

</script>
