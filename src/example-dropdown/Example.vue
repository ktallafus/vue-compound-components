<template>
  <MySelect v-model="selectValue">
    <MyOption value="1"/>
    <MyOption value="2"/>
    <MyOption value="3"/>
  </MySelect>
</template>

<script setup>
import { ref } from 'vue'
import MySelect from './MySelect.vue'
import MyOption from './MyOption.vue'

const selectValue = ref('1')

</script>
