<script setup>
import { defineProps, computed, inject } from 'vue'

const props = defineProps(['value'])

const {emitValue, currentValue} = inject('select-control');
const isActive = computed(() => currentValue.value === props.value)
</script>

<template>
  <button 
    @click="emitValue(props.value) /* emitValue from <MySelect>, not <MyOption> */" 
    :class="{active: isActive}"
  >
    I'm an option <template v-if="isActive">(active)</template>
  </button>
</template>

<style>
.active {
  color: red;
}
</style>
