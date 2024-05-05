<template>
    <div class="vertical-list-item">
      <HorizontalList :item="props.item"></HorizontalList>
    </div>
  </template>
  
  <script setup>
  import HorizontalList from './HorizontalList.vue';
  
  const props = defineProps({
    item: Object
  });
  </script>
  
  <style>
  .vertical-list-item {
    margin-bottom: 10px;
    border: 1px solid black;
    width: auto;
    height: auto;
  }
  </style>
  