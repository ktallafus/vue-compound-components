<template>
  <MySelect v-model="selectValue">
    <MyOption value="1"/>
    <MyOption value="2"/>
    <MyOption value="3"/>
  </MySelect>
</template>

<script>
import MySelect from './MySelect.vue'
import MyOption from './MyOption.vue'
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  components: {
    MyOption,
    MySelect
  },
  data() {
    return {
      count: 0,
      selectValue: '1'
    }
  }
}
</script>
