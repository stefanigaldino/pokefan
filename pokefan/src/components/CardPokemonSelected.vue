<script setup>

const pokemon = defineProps(["name", "xp", "id", "height", "img", "loading", "weight", "moves"])

</script>

<template>
    <div 
    class="card CardPokemonSelected"
    :class="loading ? '' : 'animate__animated animate__flipInY'"
    >
        <img 
        v-if="pokemon.name"
        :src="pokemon.img" 
        class="card-img-top pt-2"
        :alt="pokemon.name"
        >
        <img 
        v-else
        src="../assets/egg_pokemon.svg"
        class="card-img-top pt-2"
        alt="???"
        >

        <div class="card-body">
              <!-- StefaniGaldino -->
            <h5 class="card-title text-center">{{ pokemon.name ? pokemon.name.toUpperCase() : '???' }}</h5>
            <hr>
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
.CardPokemonSelected{
    height: 75vh;
    background: rgb(72,63,251);
    background: radial-gradient(circle, rgba(239, 88, 159, 0.8) 0%, rgba(27, 97, 196, 0.8) 100%);
}
.CardPokemonSelected img{
    height: 250px;
}

@media (max-width: 768px) {
    .CardPokemonSelected{
        height: 30vh;
        width: 50%;
        margin: 0 auto 10px auto;
    }
    .CardPokemonSelected img{
        height: 100px;
    }
}
</style>