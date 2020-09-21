<template>
  <div>
    <b-navbar toggleable="lg" type="light" variant="info" fixed="top">
      <b-navbar-brand>Austin's Website</b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item to="/">Home</b-nav-item>
          <b-nav-item to="/projects">Projects</b-nav-item>
          <b-nav-item to="/about">About</b-nav-item>
          <b-nav-item to="/todos">Todo</b-nav-item>
        </b-navbar-nav>

        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
          <!-- <b-nav-form>
            <b-form-input
              size="sm"
              class="mr-sm-2"
              placeholder="Search"
            ></b-form-input>
            <b-button size="sm" class="my-2 my-sm-0" type="submit"
              >Search</b-button
            >
          </b-nav-form> -->

          <b-nav-item-dropdown text="Lang" right>
            <template v-slot:button-content>
              <em aria-hidden="true"></em> Links
            </template>
            <b-dropdown-item href="https://github.com/abspen1"
              >GitHub</b-dropdown-item
            >
            <b-dropdown-item
              href="https://www.linkedin.com/in/austin-spencer-b56a25177/"
              >LinkedIn</b-dropdown-item
            >
            <b-dropdown-item href="https://twitter.com/austinnspencer"
              >Twitter</b-dropdown-item
            >
            <b-dropdown-item href="https://www.facebook.com/austin.spencer.129/"
              >Facebook</b-dropdown-item
            >
            <b-dropdown-item href="https://instagram.com/austinspencer"
              >Instagram</b-dropdown-item
            >
          </b-nav-item-dropdown>

          <!-- Using 'button-content' slot -->
          <!-- <b-nav-item-dropdown right>
            <template v-slot:button-content>
              <em>User</em>
            </template>
            <b-dropdown-item href="#">Profile</b-dropdown-item>
            <b-dropdown-item href="#">Sign Out</b-dropdown-item>
          </b-nav-item-dropdown> -->
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script></script>

<style lang="scss" scoped>
#nav a:hover {
  color: #f4f4f4;
}
#nav a.router-link-exact-active {
  color: #f4f4f4;
}
</style>
