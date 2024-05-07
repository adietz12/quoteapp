<template>
  <div class="comment">
    <p>{{ comment.text }}</p>
    <p>- {{ comment.author }}</p>
  </div>
</template>

<script>
export default {
  props: {
    comment: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
/* Add your component styles here */
</style>
