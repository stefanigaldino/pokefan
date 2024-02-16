<script>
</script>

<template>
  <nav class="navbar navbar-expand-md navbar-dark navbar">
    <div class="container-fluid">
      <router-link class="navbar-brand" to="/">
        <img src="./assets/pikachu2.svg" alt="" height="40" class="d-inline-block align-text-center">
        PokeFan
      </router-link>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <li class="nav-item">
            <router-link class="nav-link" to="/home">Home</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" to="/about">Sobre</router-link>
          </li>
        </ul>
      </div>
    </div>
  </nav>

<div class="main">
  <router-view></router-view>
</div>

<footer class="bg-secondary text-light footer">
  <div>Create by Stefani Galdino - {{ new Date().getFullYear() }}</div>
</footer>

</template>

<style>

.navbar {
  background-color:#ff3445;
}

body {
  height: 100vh;
  background: rgb(2,0,36);
  background: linear-gradient(90deg, rgba(2,0,36,1) 0%, rgba(9,9,121,1) 35%, rgba(0,212,255,1) 100%);
}

footer {
  position: fixed;
  bottom: 0;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 40px;
}

</style>