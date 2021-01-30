<template>
  <nav
    :class="`navbar ` + color"
    role="navigation"
    aria-label="main navigation"
  >
    <div class="navbar-brand">
      <a class="navbar-item" href="https://bulma.io">
        <img
          src="https://bulma.io/images/bulma-logo.png"
          width="112"
          height="28"
        />
      </a>
      <Menubar @toggle="$emit('display')" />
    </div>
    <section class="navbar-menu">
      <div class="navbar-start">
        <router-link class="navbar-item" to="/">Home</router-link>
        <router-link class="navbar-item" to="/">Register</router-link>
        <router-link class="navbar-item" to="/">Store</router-link>
        <div class="navbar-item is-hoverable">
          <a class="navbar-link">
            More
          </a>
          <div class="navbar-dropdown">
            <a href="#" class="navbar-item">Location</a>
            <a href="#" class="navbar-item">Contact</a>
            <a href="#" class="navbar-item">About</a>
            <hr class="navbar-divider" />
            <a href="#" class="navbar-item">Issues</a>
          </div>
        </div>
      </div>
      <div class="navbar-end">
        <div class="navbar-item">
          <div class="buttons">
            <a class="button is-primary">
              <strong>Sign up</strong>
            </a>
            <a class="button is-light">
              Log in
            </a>
          </div>
        </div>
      </div>
    </section>
  </nav>
</template>

<script>
import Menubar from "@/components/global/Menubar.vue";
export default {
  name: "Navbar",
  components: { Menubar },
  props: ["color"],
};
</script>

<style></style>
