<template>
<span>
  currentValue: {{modelValue}}
  <div style="display: flex; flex-direction: column; width: 200px;">
    <slot/>
  </div>
</span>
</template>

<script setup>
import { defineProps, defineEmits, provide, computed } from 'vue'

const props = defineProps(['modelValue'])
const emit = defineEmits(['update:modelValue'])

//this will be made availabale (provided) to child Options
//this means that child Options will be able to emit their value on behalf of Select
const emitValue = (value) => {
  emit('update:modelValue', value)
}

//currentValue needs to be a computed or it's not reactive otherwise
provide('select-control',  { emitValue, currentValue: computed(() => props.modelValue) })

</script>
