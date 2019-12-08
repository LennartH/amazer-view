<template>
  <div id="app" class="amazer-root">
    <b-navbar toggleable="lg" type="dark" variant="dark" class="amazer-navbar">
      <b-container>
        <b-navbar-brand href="#">Amazer</b-navbar-brand>

        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav>
            <b-nav-item to="/">Home</b-nav-item>
            <b-nav-item to="/about">About</b-nav-item>
          </b-navbar-nav>
        </b-collapse>
      </b-container>
    </b-navbar>
    
    <router-view/>
  </div>
</template>

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