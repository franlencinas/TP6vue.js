<template>
  <div id="app">
    <div id="nav">
      <top-nav-bar></top-nav-bar>
    </div>
    <router-view />
  </div>
</template>
<script src="dist/vue-scrollactive.min.js"></script>
<script>
import NavBarTop from "@/components/NavBarTop.vue";
export default {
  components: {
    "top-nav-bar": NavBarTop
  }
};
</script>
