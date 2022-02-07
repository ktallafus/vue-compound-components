<template>
  <MyTable :items="items">
    <MyTableColumn item-property-name="toyName">
      Toy's name
    </MyTableColumn>
    <MyTableColumn item-property-name="price">
      Some price
    </MyTableColumn>
  </MyTable>
</template>

<script setup>
import MyTable from './MyTable.vue'
import MyTableColumn from './MyTableColumn.vue'

const items = [
  {toyName: 'hotwheels', price: 700},
  {toyName: 'doll', price: 500},
]
</script>
