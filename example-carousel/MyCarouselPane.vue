<script setup>
import {onBeforeUnmount, inject, getCurrentInstance} from 'vue'

const { registerChild, unregisterChild } = inject('TheParent');
const instance = getCurrentInstance();

const childInfo = {

  // since ctx.slots.default is a render fn,
  // we pass slot content from here to the parent component
  // then render it in the parent using <component :is=""/>
  content: instance.slots.default
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
