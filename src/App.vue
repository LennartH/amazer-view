<template>
  <div id="app" class="amazer-root">
    <b-navbar toggleable="lg" type="dark" variant="dark" class="amazer-navbar">
      <b-navbar-brand href="#">Amazer</b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item to="/">Home</b-nav-item>
        </b-navbar-nav>
        <b-navbar-nav class="ml-auto">
          <b-nav-item :href="config.docsUrl" target="_blank">Documentation</b-nav-item>
          <b-nav-item-dropdown text="Source" right>
            <b-dropdown-item href="https://github.com/LennartH/amazer-ts" target="_blank">Library</b-dropdown-item>
            <b-dropdown-item href="https://github.com/LennartH/amazer-cli" target="_blank">CLI</b-dropdown-item>
            <b-dropdown-item href="https://github.com/LennartH/amazer-view" target="_blank">Webapp</b-dropdown-item>
          </b-nav-item-dropdown>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
    
    <router-view/>
  </div>
</template>

<script lang="ts">
import config from "./config";

export default {
  data() {
    return {
      config: config
    }
  }
}
</script>

<style scoped>
.amazer-root {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  justify-content: space-between
}

.amazer-navbar {
  flex: 0 1 auto;
}
</style>