<template>
  <div class="bar-widget">
    <div class="section-sort">
      <div class="suggestions">
        <span class="suggestions-amount">{{ props.suggestionsAmount }} Suggestions</span>
      </div>
      <div class="sorted-container">
        <span>Sort by&nbsp;:&nbsp;</span>
        <div class="sorted-option" @click="$emit('toggleUpvotes')">
          <span>Most Upvotes&nbsp;</span>
          <span v-if="props.selectedUpvotesDescendant">▲</span>
          <span v-else>▼</span>
        </div>
      </div>
    </div>
    <div>
      <button class="btn-add">+ Add Feedback</button>
    </div>
  </div>
</template>

<script setup lang="ts">
const props = defineProps({
  selectedUpvotesDescendant: {
    type: Boolean,
    required: true,
  },
  suggestionsAmount: {
    type: Number,
    required: true,
  }
})
</script>

<style lang="css" scoped>
.bar-widget {
  border-radius: 12px;
  margin: 1rem;
  padding: 1rem;
  background-color: rgb(57, 62, 101);
  display: flex;
  align-items: center;
  justify-content: space-between;
  color: rgb(255, 255, 255);
}
.section-sort {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 400px;
}
.suggestions {
  display: flex;
  align-items: center;
  justify-content: flex-start;
  gap: 10px;
}
.suggestions-amount {
  font-weight: bold; 
}
.sorted-container {
  display: flex;
  place-items: center;
}
.sorted-option {
  font-weight: bold;
  cursor: pointer;
}
.btn-add {
  background-color: rgb(160, 46, 227);
  font-weight: bold;
}
</style>
