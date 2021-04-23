<script setup>
import {onMounted,onBeforeUnmount,inject, defineProps, h, render, useContext} from 'vue'

const props = defineProps({
  itemPropertyName: {
    type: String,
    required: true,
  },
  sortable: {
    type: Boolean,
    default: false
  }
})
const { registerChild, unregisterChild } = inject('TheParent');
const ctx = useContext();

const childInfo = {
  itemPropertyName: props.itemPropertyName,
  sortable: props.sortable,

  // since ctx.slots.default is a render fn,
  // we pass slot content from here to the parent component
  // then render it in the parent using <component :is=""/>
  content: ctx.slots.default
}

registerChild(childInfo);
onBeforeUnmount(() => {
  unregisterChild(childInfo);
})

</script>
<template>
<div>
  <slot/>
</div>
</template>
