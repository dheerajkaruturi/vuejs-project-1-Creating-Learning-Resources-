<template>
  <ul>
    <!-- * v-bind="resources" passed in props to the component,this equivalent to :title="resources.title" :description="resources.description" :link="resources.link" -->
    <learning-resources
      v-for="resources in storedResources"
      :key="resources.id"
      v-bind="resources"
    ></learning-resources>
  </ul>
</template>

<script>
import LearningResources from './components/learning-resources/LearningResource.vue';

export default {
  components: {
    'learning-resources': LearningResources,
  },
  data() {
    return {
      storedResources: [
        {
          id: 'official documentation',
          title: 'The Official Guide',
          description: 'The official Vue.js Guide',
          link: 'http://vuejs.org',
        },
        {
          id: 'google',
          title: 'Google',
          description: 'Learn to google',
          link: 'http://www.google.com',
        },
      ],
    };
  },
};
</script>
