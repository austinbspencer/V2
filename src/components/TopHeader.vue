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
          <b-col cols="4" id="brand" v-b-tooltip.hover title="GitHub">
            <a href="https://github.com/austinbspencer"
              ><i class="fab fa-github"></i>&emsp;</a
            >
            <span>&emsp;</span>
          </b-col>
          <b-col cols="4" id="brand" v-b-tooltip.hover title="LinkedIn">
            <a href="https://www.linkedin.com/in/austin-spencer-b56a25177/"
              ><i class="fab fa-linkedin-in"></i>&emsp;</a
            >
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
          <b-nav-item id="mail-icon" right
            ><a href="https://austinspencer.works/about/contact/"
              ><i class="fas fa-envelope"></i></a
          ></b-nav-item>
          <b-nav-item-dropdown text="Social" right>
            <b-dropdown-item
              variant="info"
              href="https://twitter.com/austinbspencer"
              ><i class="fab fa-twitter"> Twitter</i></b-dropdown-item
            >
            <b-dropdown-item
              variant="primary"
              href="https://www.facebook.com/austin.spencer.129/"
              ><i class="fab fa-facebook-f"> Facebook</i></b-dropdown-item
            >
            <b-dropdown-item
              variant="warning"
              href="https://instagram.com/austinspencer"
              ><i class="fab fa-instagram"> Instagram</i></b-dropdown-item
            >
          </b-nav-item-dropdown>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script></script>

<style lang="scss" scoped>
#brand a {
  color: #8e9195;
}
#brand a:hover {
  color: #c0c3c7;
}
#mail-icon a {
  color: #918816;
}
#mail-icon a:hover {
  color: #beb320;
}
</style>
