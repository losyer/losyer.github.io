<template>
  <header>
    <nav>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> |
      <router-link to="/publications">Publications</router-link> |
      <router-link to="/contact">Contact</router-link>
    </nav>
  </header>
</template>

<style>
header {
  background: #333;
  padding: 1rem;
}
nav a {
  color: white;
  margin: 0 0.5rem;
  text-decoration: none;
}
nav a.router-link-active {
  font-weight: bold;
}
</style>
