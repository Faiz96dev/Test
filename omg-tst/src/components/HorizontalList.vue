<template>
  <div class="horizontal-list">
    <Square v-for="(item, index) in props.item" :key="index" :number="item"></Square>
  </div>
</template>

<script setup>
import Square from './Square.vue'
import HorizontalList from './HorizontalList.vue'

const props = defineProps({
  item: Array
})
</script>
<style>
.horizontal-list {
  display: flex;
}
</style>
