<template>
  <div id="app">
    <Navbar
      id="navbar"
      color='is-dark'
      @display="toggleSidebar = !toggleSidebar"
    />
    <Sidebar :show="toggleSidebar" @close="toggleSidebar = false" />
    <router-view class="container" />
  </div>
</template>

<script>
import Navbar from "@/components/global/Navbar.vue";
import Sidebar from "@/components/global/Sidebar.vue";
export default {
  components: { Navbar, Sidebar },
  data() {
    return { toggleSidebar: false };
  },
};
</script>

<style lang="scss"></style>
