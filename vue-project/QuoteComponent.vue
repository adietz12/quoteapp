<template>
  <div class="quote">
    <h2>{{ quote.text }}</h2>
    <p>{{ quote.author }}</p>
    <button @click="edit">Edit</button>
    <button @click="delete">Delete</button>
    <button v-if="canComment" @click="addComment">Add Comment</button>
    <div v-for="comment in quote.comments" :key="comment.id">
      <CommentComponent :comment="comment" />
    </div>
  </div>
</template>

<script>
import CommentComponent from './CommentComponent.vue';

export default {
  props: {
    quote: {
      type: Object,
      required: true,
    },
    canComment: {
      type: Boolean,
      default: false,
    },
  },
  components: {
    CommentComponent,
  },
  methods: {
    edit() {
      // Emit an event to notify the parent component to edit this quote
      this.$emit('edit');
    },
    delete() {
      // Emit an event to notify the parent component to delete this quote
      this.$emit('delete');
    },
    addComment() {
      // Emit an event to notify the parent component to add a comment to this quote
      this.$emit('addComment');
    },
  },
};
</script>

<style scoped>
/* Add your component styles here */
</style>
