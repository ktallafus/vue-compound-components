# How to write Compound Components in Vue

**Basic** demo of how to write components *like this* in Vue 3:
```html
<MyDropdown v-model="myDropdownValue">
  <MyDropdownOption value="hi"/>
  <MyDropdownOption value="hey"/>
  <MyDropdownOption value="hello"/>
</MyDropdown>
```
In this repository, there are examples for:
* [dropdown](https://github.com/3nuc/vue-compound-components/blob/master/example-dropdown/Example.vue)
* [table](https://github.com/3nuc/vue-compound-components/blob/master/example-table/Example.vue)

The above are called Compound Components (see [Kent Dodds's original React article](https://kentcdodds.com/blog/compound-components-with-react-hooks) about them)

# More Vue examples of compound components
* [Headless UI Dropdown menu](https://headlessui.dev/vue/menu#basic-example) and its [code](https://github.com/tailwindlabs/headlessui/blob/main/packages/%40headlessui-vue/src/components/menu/menu.ts) - make sure to check out the rest of the components too. They're also compound
* [Element Plus table](https://element-plus.org/#/en-US/component/table) and its [code](https://github.com/element-plus/element-plus/blob/27c74347a2b735391eb1fd02e6326510800096c2/packages/table/src/table.vue) - it's crazy

# Misc
Made thanks to [Michael Thiessen's tweet](https://twitter.com/3nuc1/status/1382468056354545666): 
