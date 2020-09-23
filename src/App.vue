<template>
  <div id="app">
    <div id="nav">
      <top-header></top-header>
      <!-- <side-toggle></side-toggle> -->
      <!-- <router-link to="/">Home</router-link> -->
      <!-- <router-link to="/about">About</router-link> -->
    </div>
    <router-view />
    <footer>
      <app-footer></app-footer>
    </footer>
  </div>
</template>

<script>
import TopHeader from "@/components/TopHeader.vue";
import Footer from "@/components/Footer.vue";
window.axios = require("axios");
// import SideToggle from '@/components/SideToggle.vue'

export default {
  components: {
    "top-header": TopHeader,
    "app-footer": Footer
    // 'side-toggle': SideToggle
  }
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    // color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
