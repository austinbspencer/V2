<template>
  <div>
    <b-navbar toggleable="lg" type="dark" variant="dark" fixed="top">
      <b-navbar-brand>Austin's Website</b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

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
              >GitHub</b-dropdown-item
            >
            <b-dropdown-item
              id="linkedin"
              href="https://www.linkedin.com/in/austin-spencer-b56a25177/"
              >LinkedIn</b-dropdown-item
            >
            <b-dropdown-item
              id="twitter"
              href="https://twitter.com/austinnspencer"
              >Twitter</b-dropdown-item
            >
            <b-dropdown-item
              id="facebook"
              href="https://www.facebook.com/austin.spencer.129/"
              >Facebook</b-dropdown-item
            >
            <b-dropdown-item
              id="insta"
              href="https://instagram.com/austinspencer"
              >Instagram</b-dropdown-item
            >
          </b-nav-item-dropdown>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script></script>

<style lang="scss" scoped></style>
