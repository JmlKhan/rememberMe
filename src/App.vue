<template>
  <div>
    <the-header :title="title"> </the-header>
    <!-- <StoredResources :resources="storedResources"> </StoredResources> -->
    <the-resource> </the-resource>
  </div>
</template>

<script>
//import modules
import TheHeader from './components/layouts/TheHeader.vue';
import TheResource from './components/learning-resources/TheResource.vue';
export default {
  components: {
    TheHeader,
    TheResource,
  },
  data() {
    return {
      title: 'RememberMe',
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
