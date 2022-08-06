<template>
  <ul>
    <!-- * v-bind="resources" passed in props to the component,this equivalent to :title="resources.title" :description="resources.description" :link="resources.link" -->
    <learning-resources
      v-for="resources in importedResources"
      :key="resources.id"
      v-bind="resources"
    ></learning-resources>
  </ul>
</template>

<script>
import LearningResources from './LearningResource.vue';
export default {
  props: {
    importedResources: {
      type: Object,
      required: true,
    },
  },
  components: {
    'learning-resources': LearningResources,
  },
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>
