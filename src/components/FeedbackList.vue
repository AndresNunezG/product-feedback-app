<template>
  <div v-if="feedbackListFiltered.length">
    <div v-for="feedbackObj in feedbackListFiltered" :key="feedbackObj.uuid">
      <FeedbackCardItem :feedback-item="feedbackObj" />
    </div>
  </div>
  <div v-else class="no-results-label">
    <strong>No results found</strong>
  </div>
</template>

<script setup lang="ts">
import { ref, computed, watch } from 'vue'
import FeedbackCardItem from './FeedbackCardItem.vue';

const feedbackList = ref(
  [
    {
      title: "Add tags for solutions",
      description: "Easier to search for solutions based on a specific stack.",
      category: "Enhancement",
      comments: 2,
      upvotes: 122,
      uuid: crypto.randomUUID()
    },
    {
      title: "Add a dark theme option",
      description: "It would help people with light sensitivities and who prefer dark mode.",
      category: "Feature",
      comments: 4,
      upvotes: 99,
      uuid: crypto.randomUUID()
    },
    {
      title: "Q&A within the challenge hubs",
      description: "Challenge-specific Q&A would make for easy reference.",
      category: "Feature",
      comments: 1,
      upvotes: 65,
      uuid: crypto.randomUUID()
    },
    {
      title: "Allow image/video upload to feedback",
      description: "Images and screencasts can enhance comments on solutions.",
      category: "Enhancement",
      comments: 2,
      upvotes: 61,
      uuid: crypto.randomUUID()
    },
    {
      title: "Ability to follow others",
      description: "Stay updated on comments and solutions other people post",
      category: "Feature",
      comments: 3,
      upvotes: 42,
      uuid: crypto.randomUUID()
    },
  ]
)

const emit = defineEmits(['updateSuggestionsAmount',])

const props = defineProps({
  selectedCategory: {
    type: String,
    required: true
  },
  selectedUpvotesDescendant: {
    type: Boolean,
    required: true
  }
})

const feedbackListFiltered = computed(() => {
  const allFeedback = [...feedbackList.value]
  const filteredByCategory = props.selectedCategory === 'ALL' ?
    allFeedback :
    allFeedback.filter((fb) => (
      fb.category.toUpperCase() === props.selectedCategory
    ))
  return filteredByCategory.sort((fbA, fbB) => {
    if (props.selectedUpvotesDescendant) {
      return fbA.upvotes - fbB.upvotes
    }
    return fbB.upvotes - fbA.upvotes
  })
})

watch(
  feedbackListFiltered,
  (newValue) => {emit('updateSuggestionsAmount', newValue.length)},
  { immediate: true }
)
</script>

<style>
.no-results-label {
  padding: 1rem;
}
</style>
