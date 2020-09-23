<template>
  <div>
    <link
      rel="stylesheet"
      href="https://use.fontawesome.com/releases/v5.2.0/css/all.css"
      integrity="sha384-hWVjflwFxL6sNzntih27bfxkr27PmbbK/iSvJ+a4+0owXq79v+lsFkW54bOGbiDQ"
      crossorigin="anonymous"
    />
    <b-navbar toggleable="lg" type="dark" variant="dark" fixed="top">
      <b-navbar-brand>
        <b-row>
          <b-col cols="4" id="brand">
            <a href="https://github.com/abspen1"><i class="fab fa-github"></i>&emsp;</a>
            <span>&emsp;</span>
          </b-col>
          <b-col cols="4" id="brand">
            <a href="https://www.linkedin.com/in/austin-spencer-b56a25177/"><i class="fab fa-linkedin-in"></i>&emsp;</a>
          </b-col>
        </b-row>
      </b-navbar-brand>
      <!-- <b-navbar-brand id="brand" href="https://www.linkedin.com/in/austin-spencer-b56a25177/">
        
      </b-navbar-brand> -->

      <b-navbar-toggle target="nav-collapse">
        <template v-slot:default="{ expanded }">
          <span v-if="expanded">
            <i class="fas fa-chevron-circle-down"></i
          ></span>
          <span v-else> <i class="fas fa-chevron-circle-up"></i></span>
        </template>
      </b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item to="/">Home</b-nav-item>
          <b-nav-item to="/projects">Projects</b-nav-item>
          <b-nav-item to="/about">About</b-nav-item>
          <!-- <b-nav-item to="/todo">Todo</b-nav-item> -->
        </b-navbar-nav>

        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
          <b-nav-item href="https://austinspencer.works/about/contact/"
            right><i class="fas fa-envelope"></i></b-nav-item
          >
          <b-nav-item-dropdown text="Social" right>
            <b-dropdown-item href="https://twitter.com/austinnspencer"
              ><i class="fab fa-twitter"></i></b-dropdown-item
            >
            <b-dropdown-item href="https://www.facebook.com/austin.spencer.129/"
              ><i class="fab fa-facebook"></i></b-dropdown-item
            >
            <b-dropdown-item href="https://instagram.com/austinspencer"
              ><i class="fab fa-instagram"></i></b-dropdown-item
            >
          </b-nav-item-dropdown>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script></script>

<style lang="scss" scoped>
#brand a{
  color: #8E9195;
}
#brand a:hover {
  color: #c0c3c7;
}
</style>
