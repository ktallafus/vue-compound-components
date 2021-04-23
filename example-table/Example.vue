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

<script>
import MyTable from './MyTable.vue'
import MyTableColumn from './MyTableColumn.vue'
export default {
  name: 'HelloWorld',
  components: {
    MyTable,
    MyTableColumn
  },
  data() {
    return {
      items: [
        {toyName: 'hotwheels', price: 700},
        {toyName: 'doll', price: 500},
      ]
    }
  }
}
</script>
