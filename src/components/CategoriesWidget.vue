<template>
  <div class="categories-widget">
    <span
      class="badge-category"
      :class="{ 'badge-category--active': cat.toUpperCase() ===  props.selectedCategory }"
      v-for="cat, index in categories"
      :key="index"
      @click="$emit('applyCategoryFilter', cat.toUpperCase())"
    >{{ cat }}</span>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

defineEmits(['applyCategoryFilter',])
const props = defineProps({
  selectedCategory: {
    type: String,
    required: true,
  },
})

const categories = ref(
  [
    "All",
    "UI",
    "UX",
    "Enhancement",
    "Bug",
    "Feature",
  ]
)
</script>

<style lang="css" scoped>
.categories-widget {
  background-color: white;
  border-radius: 12px;
  padding: 1rem;
  margin: 1rem;
  display: flex;
  align-items: center;
  justify-content: flex-start;
  gap: 10px;
  flex-wrap: wrap;
}
.badge-category {
  border-radius: 8px;
  padding: 4px 14px;
  font-size: 12px;
  font-weight: bold;
  cursor: pointer;
  background-color: rgb(242, 244, 254);
  color: rgb(121, 137, 230);
}
.badge-category--active {
  background-color: rgb(76, 96, 222);
  color: rgb(255, 255, 255);
}
</style>
