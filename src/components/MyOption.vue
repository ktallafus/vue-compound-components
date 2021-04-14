<template>
  <button 
    @click="emitValue(props.value) /* emitValue from <Select>, not <Option> */" 
    style="color: red;">
    I'm an option {{ currentValue === value ? 'active' : '' }}
  </button>
</template>

<script setup>
import { defineProps, inject } from 'vue'

const props = defineProps(['value'])

const {emitValue, currentValue} = inject('select-control');
</script>
