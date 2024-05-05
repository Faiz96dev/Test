<template>
  <RecycleScroller
    class="vertical-list"
    :items="items"
    :buffer="100"
    :itemSize="20"
    @update="updateIndex"
    v-slot="{ item }"
  >
    <VerticalListItem :item="item.value" />
  </RecycleScroller>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import { RecycleScroller } from 'vue3-virtual-scroller';
import VerticalListItem from './VerticalListItem.vue';

const items = ref([]);

onMounted(() => {
  generateVerticalItems();
});


function  updateIndex(sIndex, eIndex) {
    console.log('updateIndex')
    }

function generateRandomItem() {
  return {
    id: Math.random().toString(36).substr(2, 9),
    value: Math.floor(Math.random() * 100)  
  }
}

function generateRandomItems(count) {
  const items = [];
  for (let i = 0; i < count; i++) {
    items.push(generateRandomItem());
  }
  return items;
}

function generateVerticalItems() {
  const count = Math.floor(Math.random() * 100) + 100; 
  const verticalItems = [];
  for (let i = 0; i < count; i++) {
    verticalItems.push({value: generateRandomItems(Math.floor(Math.random() * 10) + 10), id: Math.random().toString(36).substr(2, 9)}); 

  }
  items.value = verticalItems;
}




</script>

<style scoped>
.vertical-list {
  border-radius: 2px solid black;
  height: 30vh;
  overflow-y: auto; 
}
</style>
