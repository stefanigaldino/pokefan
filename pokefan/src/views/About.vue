<template>
  <div class="about-page">
    <div class="container about">
      <img src="../assets/ash.png" class="imgAsh" alt="">
      <h1 class="text-center">Sobre a Pokefan</h1>
      <p>
        Bem-vindo à nossa Pokédex digital! Aqui, você pode explorar uma coleção incrível de Pokémons, descobrir informações detalhadas sobre cada um deles e até mesmo salvar seus favoritos.
      </p>
      <p>
        Nossa missão é fornecer uma experiência completa para treinadores Pokémon de todos os níveis. Desde os clássicos da região de Kanto até as últimas descobertas em Galar, nossa Pokédex tem tudo.
      </p>
      <h2 class="text-center">Equipe</h2>
      <ul>
        <li><strong>Desenvolvedor:</strong> Stefani Galdino</li>
        <li><strong>Designer:</strong> Stefani Galdino</li>
        <li><strong>Entusiasta Pokémon:</strong> Todos Nós</li>
      </ul>
    </div>    
  </div>
  <div>
    <button type="button" class="btn btn-light btn2">
      <a href="https://www.linkedin.com/in/stefanigaldino/" target="_blank" rel="noopener noreferrer">LinkedIn</a>
    </button>
  </div>
</template>

<style scoped>

.about {
  color: aliceblue;
}

.btn2 {
    position: fixed; /* Manter o botão fixo na tela */
    bottom: 60px; /* Espaço suficiente para o rodapé (ajuste conforme necessário) */
    left: 50%; /* Centralizar na horizontal */
    transform: translateX(-50%); /* Corrigir o deslocamento causado pelo left: 50% */
    z-index: 1000; /* Certificar-se de que o botão está acima de outros elementos */
  }

  /* Estilo adicional para melhorar a aparência */
  .btn2 a {
    color: #333;
    text-decoration: none;
  }

  .imgAsh {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  height: 200px;
  width: 200px;
  z-index: 1; /* Ajuste conforme necessário */
}



</style>
