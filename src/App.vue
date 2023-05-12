<template>
  <div class="main-container">
    <div class="widgets-section">
      <BadgeDashboard />
      <CategoriesWidget
        :selected-category="selectedCategory"
        @apply-category-filter="applyCategoryFilter" />
      <RoadmapWidget />
    </div>
    <div class="suggestions-section">
      <BarWidget
        :selected-upvotes-descendant="selectedUpvotesDescendant"
        :suggestions-amount="suggestionsAmount"
        @toggle-upvotes="toggleUpvotes" />
      <FeedbackList
        :selected-category="selectedCategory"
        :selected-upvotes-descendant="selectedUpvotesDescendant"
        @update-suggestions-amount="(amount) => suggestionsAmount = amount" />
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import BadgeDashboard from './components/BadgeDashboard.vue';
import CategoriesWidget from './components/CategoriesWidget.vue';
import RoadmapWidget from './components/RoadmapWidget.vue'
import BarWidget from './components/BarWidget.vue';
import FeedbackList from './components/FeedbackList.vue';

const selectedCategory = ref('ALL')
function applyCategoryFilter (category: string) {
  selectedCategory.value = category
}

const selectedUpvotesDescendant = ref(false)
function toggleUpvotes () {
  selectedUpvotesDescendant.value = !selectedUpvotesDescendant.value
}

const suggestionsAmount = ref(0)

</script>

<style scoped>
.main-container {
  display: flex;
}
.widgets-section {
  display: flex;
  flex-direction: column;
  max-width: 320px;

}
.suggestions-section {
  max-width: 960px;
  width: 960px;
}
</style>
