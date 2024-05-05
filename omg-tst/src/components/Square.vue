<template>
  <div
    class="square"
    :style="{
      border: '1px solid black'
    }"
  >
    <p>{{ number.value }}</p>
  </div>
</template>

<script setup>
const props = defineProps({
  number: Object
})
</script>

<style scoped>
.square {
  display: flex;
  border-radius: 10px;
  justify-content: center;
  width: 50px;
  margin: 10px;
  cursor: pointer;
  height: 50px;
  align-items: center;
  transition: transform 0.3s ease;
}

.square:hover {
  transform: scale(0.8);
}
</style>
