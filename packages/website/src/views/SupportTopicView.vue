<template>
  <div>
    <h1>{{ topic }}</h1>
    <p>{{ answer }}</p>
  </div>
</template>

<script>
export default {
  props: ['topicId', 'filteredAccountHelp'],
  computed: {
    topic() {
      const topicItem = this.filteredAccountHelp.accountHelp.find(
        (item, index) => index === Number(this.topicId)
      );
      return topicItem ? topicItem.topic : '';
    },
    answer() {
      const topicItem = this.filteredAccountHelp.accountHelp.find(
        (item, index) => index === Number(this.topicId)
      );
      return topicItem ? topicItem.answer : '';
    }
  }
};
</script>

<style scoped>
/* Component-specific styles */
</style>
