<template>
  <div id="app">
    <b-navbar toggleable="lg" type="dark" variant="success">
      <b-container>
        <b-navbar-brand href="#">Amazer</b-navbar-brand>
        <b-link to="/">Home</b-link> |
        <b-link to="/about">About</b-link>
      </b-container>
    </b-navbar>
    <router-view/>
  </div>
</template>
