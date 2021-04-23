<script setup>
import {ref, provide, defineProps } from 'vue'

const props = defineProps({
  items: {
    type: Array,
    required: true,
  }
})

const registerChild = (child) => registeredChildren.value.push(child);
const unregisterChild = (child) => {
  registeredChildren.value = 
    registeredChildren.value.filter(
      registeredChild => registeredChild !== child
    );
};
  
const registeredChildren = ref([]);

provide('TheParent', { registerChild, unregisterChild })
  
</script>
<template>
columns: {{ registeredChildren.map(x=>x.itemPropertyName) }}
<table>
  <thead>
    <tr>
      <th v-for="column in registeredChildren" :key="column">
        <component :is="column.content" ref="column"/>
        {{ column.sortable ? 'sortable' : ''}}
      </th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="item, i in items" :key="i">
      <td v-for="column, j in registeredChildren" :key="j">
        {{ item[column.itemPropertyName] }}
      </td>
    </tr>
  </tbody>
</table>

<!-- we want the mounted() lifecycle to fire on the components that are in the slot, but we dont want to show them -->
<div v-show="false">
  <slot/>
</div>
</template>
