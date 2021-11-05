<template>
  <div>
    <base-card>
      <base-button
        @click="setSelectedTab('stored-resources')"
        :mode="storedResBtn"
        >StoredResources</base-button
      >
      <base-button @click="setSelectedTab('add-resource')" :mode="addResBtn"
        >Add Resource</base-button
      >
    </base-card>
    <component :is="selectedTab"> </component>
  </div>
</template>

<script>
import BaseButton from '../UI/BaseButton.vue';
import StoredResources from './StoredResources.vue';
import AddResource from './AddResource.vue';

export default {
  components: {
    BaseButton,
    StoredResources,
    AddResource,
  },
  data() {
    return {
      selectedTab: 'stored-resources',
      storedResources: [
        {
          id: 'official-guide',
          title: 'Official Guide',
          description: 'The official Vue,js documentation',
          link: 'https://vuejs.org',
        },
        {
          id: 'google',
          title: 'Google',
          description: 'Learn to google',
          link: 'https://google.com',
        },
      ],
    };
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
  },
  provide() {
    return {
      resources: this.storedResources,
    };
  },
  computed: {
    addResBtn() {
      return this.selectedTab === 'add-resource' ? null : 'flat';
    },
    storedResBtn() {
      return this.selectedTab === 'stored-resources' ? null : 'flat';
    },
  },
};
</script>
