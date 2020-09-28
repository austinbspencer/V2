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
#danger-outline {
  color: #dc3545;
  border: 1px solid #dc3545;
  background-color: transparent;
}
#danger-outline:hover {
  color: white;
  background-color: #dc3545;
  border-color: transparent;
}
#danger {
  color: white;
  background-color: #dc3545;
}
#danger:hover {
  background-color: #ac2633;
}
#dark-outline {
  color: #343a40;
  border: 1px solid #343a40;
  background-color: transparent;
}
#dark-outline:hover {
  color: white;
  background-color: #343a40;
  border-color: transparent;
}
#success-outline {
  color: #28a745;
  background-color: transparent;
  border: 1px solid #28a745;
}
#success-outline:hover {
  color: white;
  background-color: #28a745;
  border-color: transparent;
}
#info-outline {
  color: #17a2b8;
  background-color: transparent;
  border: 1px solid #17a2b8;
}
#info-outline:hover {
  color: white;
  border-color: transparent;
  background-color: #17a2b8;
}
</style>
