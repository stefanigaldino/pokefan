<script setup>
const pokemon = defineProps(["name", "urlBaseSvg", "id"]);
</script>

<template>
  <div class="col-4">
    <div class="card pd-2 mb-3 cardListPokemon">
      <p class="text-center">{{pokemon.name.toUpperCase()}}</p>           
      <img       
        :src="`https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/${pokemon.id}.svg`"  
        height="250"
        class="card-img-top pd-2"
      >
    </div>
  </div>
</template>

<style scoped>
.cardListPokemon {
    cursor: pointer;
    background: rgb(27,165,240);
    background: radial-gradient(circle, rgba(27,165,240,1) 0%, rgba(69,222,190,0.5186915887850467) 100%);
}
.cardListPokemon:hover {
    cursor: pointer;
    background: rgb(27,165,240);
    background: radial-gradient(circle, rgb(132, 106, 192) 0%, rgba(37, 113, 97, 0.519) 100%);
}
.cardListPokemon img:hover {
   padding: 1rem;
}
</style>
