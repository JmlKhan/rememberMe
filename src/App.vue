<template>
  <StoredResources :resources="storedResources"> </StoredResources>
</template>

<script>
import StoredResources from './components/learning-resources/StoredResources.vue';
//import modules

export default {
  components: {
    StoredResources,
  },
  data() {
    return {
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
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto+Slab:wght@300&family=Roboto:ital,wght@1,100;1,400&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}
body {
  margin: 0;
}
a {
  color: goldenrod;
  text-decoration: none;
}
</style>
