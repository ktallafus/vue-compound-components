<script setup>
import MyCarouselGroup from './MyCarouselGroup.vue'
import MyCarouselPane from './MyCarouselPane.vue'
const images = {
  device: "https://images.unsplash.com/photo-1593643946890-b5b85ade6451?ixid=MnwxMjA3fDF8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1529&q=80",
  dog: "https://images.unsplash.com/photo-1629757257537-62cedbcffbe6?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1349&q=80",
  beach: "https://images.unsplash.com/photo-1629794023788-ebb5f77642c1?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=934&q=80"
}
</script>
<template>
<MyCarouselGroup>
  <MyCarouselPane paneid="1">
    <img :src="images.device"/>
  </MyCarouselPane>
  <MyCarouselPane paneid="2">
    <img :src="images.dog"/>
  </MyCarouselPane>
  <MyCarouselPane paneid="3">
    <img :src="images.beach" />
  </MyCarouselPane>
</MyCarouselGroup>
</template>
