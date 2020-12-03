<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
  <router-link class="navbar-brand" to="/">Главная</router-link>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse" id="navbarNav">
    <ul class="navbar-nav">
      <li class="nav-item active">
        <router-link class="nav-link" to="/price">Цены</router-link>
      </li>
      <li class="nav-item active">
        <router-link class="nav-link" to="/about">О нас</router-link>
      </li>
      
    </ul>
  </div>
</nav>
</template>



<style scoped lang="scss">
  .navbar {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 1;
  }
</style>
