<script setup>
import ExampleDropdown from './example-dropdown/Example.vue'
import ExampleTable from './example-table/Example.vue'
import ExampleCarousel from './example-carousel/Example.vue'
</script>

<template>
<div style="display: flex;">

  <section style="margin-right: 20px;">
    <h2>Compound dropdown</h2>
    <ExampleDropdown/>
  </section>

  <section>
    <h2>Compound table</h2>
    <ExampleTable/>
  </section>

  <section>
    <h2>Compound carousel</h2>
    <ExampleCarousel/>
  </section>

</div>
</template>
