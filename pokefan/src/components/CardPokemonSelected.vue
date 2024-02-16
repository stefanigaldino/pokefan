<script setup>

const pokemon = defineProps(["name", "xp", "id", "height", "img", "loading", "weight", "moves"])

</script>

<template>
    <div 
    class="card cardPokemonSelected"
    :class="loading ? '' : 'animate__animated animate__flipInY'"
    >

    <img 
    v-if="pokemon.name"    
    :src="`https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/${pokemon.id}.svg`"  
    height="250"
    class="card-img-top pd-4"
    :alt="pokemon.name">
        
    <img 
    v-else
    src="../assets/egg_pokemon.svg"
        height="200"
        class="card-img-top pd-2"
        :alt="'???'">
  <div class="card-body">
    <h5 class="card-title text-center">{{ pokemon.name ? pokemon.name.toUpperCase() : '???' }}</h5>
      <hr />
    <div class="row">
        <section class="col">
            <strong>Id: </strong>
            <span>{{pokemon.id}}</span>
        </section>
        <section class="col">
            <strong>XP: </strong>
            <span>{{pokemon.xp}}</span>
        </section>     
           
    </div>

    <div class="row">
        <section class="col">
            <strong>Peso: </strong>
            <span>{{pokemon.weight}}</span>
        </section>
        <section class="col">
            <strong>Altura: </strong>
            <span>{{pokemon.height}}</span>
        </section>        
    </div>

    <div class="row">
        <section class="col">
            <strong>Principais Movimentos: </strong>
            <span>{{pokemon.moves}}</span>
        </section>        
    </div>
    
  </div>
</div>

</template>

<style scoped>

.cardPokemonSelected {
    height: 75vh;
    background: rgb(7, 60, 89);
    background: radial-gradient(circle, rgb(102, 212, 224) 0%, rgba(180, 96, 219, 0.397) 100%);
}

</style>