<template>
  <base-card>
    <base-button @click="setSelectedTab('stored-recources')" :mode="storedResButtonMode"
      >Stored Recources</base-button
    >
    <base-button @click="setSelectedTab('add-recource')" :mode="addResButtonMode"
      >Add Recource</base-button
    >
  </base-card>
  <component :is="selectedTab"></component>
</template>

<script>
import AddRecource from './AddRecource.vue';
import StoredRecources from './StoredRecources.vue';

export default {
  components: {
    AddRecource,
    StoredRecources,
  },
  data() {
    return {
      selectedTab: 'stored-recources',
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
  computed: {
    storedResButtonMode(){
        return this.selectedTab === 'stored-recources' ? null : 'flat'
    },
    addResButtonMode(){
        return this.selectedTab === 'add-recource' ? null : 'flat'
    }
  },    
  provide(){
    return {
        recources: this.storedRecources
    }
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
  },
};
</script>
