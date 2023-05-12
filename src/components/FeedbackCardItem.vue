<template>
  <div class="feedback-card-item">
    <div class="feedback-main">
      <div class="feedback-upvotes-wrapper">
        <div class="feedback-upvotes-container">
          <span>▲</span>
          <span>{{ props.feedbackItem.upvotes }}</span>
        </div>
      </div>
      <div>
        <p class="feedback-title">{{ props.feedbackItem.title }}</p>
        <p>{{ props.feedbackItem.description }}</p>
        <p class="feedback-category">{{ props.feedbackItem.category }}</p>
      </div>
    </div>
    <div class="comment-section">
      <span>⚑</span>
      <span>{{ props.feedbackItem.comments }}</span>
    </div>
  </div>
</template>

<script setup lang="ts">
interface Feedback {
  title: string
  description: string
  category: string
  comments: Number
  upvotes: Number
}

const props = defineProps<{
  feedbackItem: Feedback
}>()
</script>

<style lang="css">
.feedback-card-item {
  border-radius: 12px;
  margin: 1rem;
  padding: 1.5rem;
  background-color: rgb(255, 255, 255);
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.feedback-main {
  display: flex;
  justify-content: flex-start;
  gap: 2rem;
}
.feedback-upvotes-container {
  display: flex;
  flex-direction: column;
  place-items: center;
  font-weight: bold;
  background-color: rgb(242, 244, 254);
  border-radius: 8px;
  width: fit-content;
  padding: 8px;
  min-width: 3ch;
}
.feedback-title {
  font-weight: bold;
  margin-top: 0;
}
.feedback-category {
  color: rgb(121, 137, 230);
  background-color: rgb(242, 244, 254);
  border-radius: 8px;
  padding: 4px 14px;
  font-weight: bold;
  font-size: 12px;
  width: fit-content;
  margin-bottom: 0;
}
.comment-section {
  display: flex;
  place-items: center;
  font-weight: bold;
  gap: 10px;
}
</style>
