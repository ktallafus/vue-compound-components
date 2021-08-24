<script setup>
import {ref, provide} from 'vue'
// exactly the same as in example-table folder
const registerChild = (child) => registeredChildren.value.push(child);
const unregisterChild = (child) => {
  registeredChildren.value = 
    registeredChildren.value.filter(
      registeredChild => registeredChild !== child
    );
};
  
const registeredChildren = ref([]);
const activePaneIndex = ref(0);

setInterval(() => {
  const isShowingLastPane =  activePaneIndex.value === registeredChildren.value.length-1;
  activePaneIndex.value = isShowingLastPane ? 0 : activePaneIndex.value+1
}, 2000)

provide('TheParent', { registerChild, unregisterChild })
</script>
<template>
  <div style="height: 500px; width: 500px;">
    <template 
      v-for="(child, index) in registeredChildren"  
    >
      <div 
        v-if="index === activePaneIndex"
        class="image-container"
       >
        <component 
          :is="child.content"
        />
       </div>
    </template>
  </div>
  <div v-show="false">
    <slot/>
  </div>
</template>
<style>
.image-container > img {
  max-width: 100%;
  max-height: 100%;
}
</style>
