<template>
  <div id="app" class="text-dark">
    <Header />
    <router-view />
  </div>
</template>

<script>
import Header from "./layout/Header.vue";

export default {
  name: "App",
  components: {
    Header,
  },
};
</script>
