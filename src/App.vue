<template>
    <the-header title="Rmember Me"></the-header>
    <!-- <stored-recources :recources="storedRecources"></stored-recources> -->
    <the-recources></the-recources>
</template>

<script>
import TheRecources from './components/learning-recources/TheRecources.vue';
import TheHeader from './components/leyouts/TheHeader.vue';
export default {
    components:{
        TheRecources,
        TheHeader
    } ,
  
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