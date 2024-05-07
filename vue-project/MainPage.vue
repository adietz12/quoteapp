<template>
  <div>
    <h1>Quotes</h1>
    <div v-for="quote in quotes" :key="quote.id">
      <quote-component :quote="quote" />
      <button v-if="isOwner(quote.owner)" @click="editQuote(quote)">Edit</button>
      <button v-if="isOwner(quote.owner)" @click="deleteQuote(quote.id)">Delete</button>
      <button @click="addComment(quote.id)">Add Comment</button>
      <div v-for="comment in quote.comments" :key="comment.id">
        <comment-component :comment="comment" />
      </div>
    </div>
    <button @click="addQuote">Add Quote</button>
  </div>
</template>

<script>
import QuoteComponent from './QuoteComponent.vue';
import CommentComponent from './CommentComponent.vue';

export default {
  components: {
    QuoteComponent,
    CommentComponent,
  },
  data() {
    return {
      quotes: [], // Populate this with your quotes data
      user: 'current user', // Populate this with the current user's username
    };
  },
  methods: {
    isOwner(owner) {
      return owner === this.user;
    },
    editQuote(quote) {
      // Handle edit quote functionality here
    },
    deleteQuote(quoteId) {
      // Handle delete quote functionality here
    },
    addComment(quoteId) {
      // Handle add comment functionality here
    },
    addQuote() {
      // Handle add quote functionality here
    },
  },
};
</script>

<style scoped>
/* Add your component styles here */
</style>
