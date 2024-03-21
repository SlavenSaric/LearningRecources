<template>
    <ul>
    <learning-recource v-for="res in recources" :key="res.id" :title="res.title" :description="res.description" :link="res.link"></learning-recource>
  </ul>
</template>

<script>
    import LearningRecource from './LearningRecource.vue';

    export default {
        inject: ['recources'],
        components: {
            LearningRecource
        }
    }
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