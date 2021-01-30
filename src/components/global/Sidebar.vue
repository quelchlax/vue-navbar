<template>
  <aside class="menu-wrapper">
    <div class="menu-backdrop" v-if="show" @click="$emit('close')">
      <!-- backdrop (empty) -->
    </div>

    <transition name="slide-side">
      <div v-if="show" class="menu-navbar">
        <h2 class="title is-3">Brand</h2>
        <ul class="menu-list" @click="$emit('close')">
          <p class="menu-label">Welcome</p>
          <li>
            <router-link class="navbar-item" to="/">Home</router-link>
          </li>
          <li>
            <router-link class="navbar-item" to="/about">About</router-link>
          </li>
        </ul>
      </div>
    </transition>
  </aside>
</template>

<script>
export default {
  name: "Sidebar",
  props: {
    show: { type: Boolean, default: false },
  },
};
</script>

<style lang="scss" scoped>
.menu-label {
  font-weight: bold;
}
.is-switch {
  cursor: pointer;
}
.is-toggler {
  outline: none;
  border: none;
  background-color: inherit;
}
@mixin fillout() {
  height: 100%;
  width: 100%;
}
@mixin topleft() {
  top: 0;
  left: 0;
}
.menu-wrapper {
  @include fillout();
  font-size: 20px;

  .menu-backdrop {
    @include fillout();
    @include topleft();
    z-index: 100;
    position: fixed;
    background-color: rgba(12, 17, 23, 0.9);
  }

  .menu-navbar {
    @include topleft();
    height: 100%;
    width: 240px;
    position: fixed;
    background-color: white;
    z-index: 200;
    box-sizing: border-box;
    padding: 2rem;
  }

  .end {
    margin-top: auto;
  }

  .slide-side-enter-active,
  .slide-side-leave-active {
    transition: all 0.2s ease-in-out;
  }
  .slide-side-enter,
  .slide-side-leave-to {
    transform: translateX(-100%);
  }
}
</style>
