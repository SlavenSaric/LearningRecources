<template>
  <ul>
    <learning-recource v-for="res in storedRecources" :key="res.id" :title="res.title" :description="res.description" :link="res.link"></learning-recource>
  </ul>
</template>

<script>
import LearningRecource from './components/learning-recources/LearningRecource.vue'

export default {
    components:{
        LearningRecource
    } ,
  data() {
    return {
      storedRecources: [
        {
          id: 'official-guide',
          title: 'Official Guide',
          description: 'The Official Vue.js Documentation',
          link: 'https://vuejs.org',
        },
        {
          id: 'google',
          title: 'Google',
          description: 'Learn how to google',
          link: 'https://www.google.de',
        },
      ],
    };
  },
};
</script>
