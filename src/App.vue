<template>
    <stored-recources :recources="storedRecources"></stored-recources>
</template>

<script>
import StoredRecources from './components/learning-recources/StoredRecources.vue';
export default {
    components:{
        StoredRecources
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

<style>
    @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>