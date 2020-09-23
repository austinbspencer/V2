<template>
  <div>
    <link
      rel="stylesheet"
      href="https://use.fontawesome.com/releases/v5.2.0/css/all.css"
      integrity="sha384-hWVjflwFxL6sNzntih27bfxkr27PmbbK/iSvJ+a4+0owXq79v+lsFkW54bOGbiDQ"
      crossorigin="anonymous"
    />
    <b-navbar toggleable="lg" type="dark" variant="dark" fixed="top">
      <b-navbar-brand>Austin's Website</b-navbar-brand>

      <b-navbar-toggle target="nav-collapse">
        <template v-slot:default="{ expanded }">
          <b-icon v-if="expanded">
            <i class="fas fa-chevron-circle-down"></i
          ></b-icon>
          <b-icon v-else> <i class="fas fa-chevron-circle-up"></i></b-icon>
        </template>
      </b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item to="/">Home</b-nav-item>
          <b-nav-item to="/projects">Projects</b-nav-item>
          <b-nav-item to="/about">About</b-nav-item>
          <b-nav-item href="https://austinspencer.works/about/contact/"
            >Contact</b-nav-item
          >
          <!-- <b-nav-item to="/todo">Todo</b-nav-item> -->
        </b-navbar-nav>

        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
          <b-nav-item-dropdown text="Links" right>
            <b-dropdown-item href="https://github.com/abspen1"
              ><i class="fab fa-github"></i> GitHub</b-dropdown-item
            >
            <b-dropdown-item
              href="https://www.linkedin.com/in/austin-spencer-b56a25177/"
              ><i class="fab fa-linkedin"></i> LinkedIn</b-dropdown-item
            >
            <b-dropdown-item href="https://twitter.com/austinnspencer"
              ><i class="fab fa-twitter"></i> Twitter</b-dropdown-item
            >
            <b-dropdown-item href="https://www.facebook.com/austin.spencer.129/"
              ><i class="fab fa-facebook"></i> Facebook</b-dropdown-item
            >
            <b-dropdown-item href="https://instagram.com/austinspencer"
              ><i class="fab fa-instagram"></i> Instagram</b-dropdown-item
            >
          </b-nav-item-dropdown>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script></script>

<style lang="scss" scoped></style>
