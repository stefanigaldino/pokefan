<script setup>

import { onMounted, ref, reactive, computed } from "vue";
import ListPokemons from "@/components/ListPokemons.vue";
import CardPokemonSelected from "@/components/CardPokemonSelected.vue";

let pokemons = reactive(ref());
let urlBaseSgv = ref("https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/");
let searchPokemonField = ref("");
let pokemonSelected = reactive(ref());
let loading = ref(false);

onMounted(() => {
  fetch("https://pokeapi.co/api/v2/pokemon?limit=151&offset=0")
  .then(res => res.json())
  .then(res => pokemons.value = res.results);
});

const pokemonsFiltered = computed(() => {
  if (pokemons.value && searchPokemonField.value) {
    return pokemons.value.filter(pokemon =>
    pokemon.name.toLowerCase().includes(searchPokemonField.value.toLowerCase())
    );
  }
  return pokemons.value;
});

const selectPokemon = async (pokemon) => {
  loading.value = true;
  await fetch(pokemon.url)
    .then(res => res.json())
    .then(res => pokemonSelected.value = res)
    .catch(err => alert(err))
    .finally(() => loading.value = false)
    console.log(pokemonSelected.value)
}

</script>

<template>
  <main>
    <div class="container text-body-secondary">
      <div class="row mt-5">
        <div class="col-sm-12 col-md-6">

          <CardPokemonSelected
            :name="pokemonSelected?.name"
            :id="pokemonSelected?.id"
            :xp="pokemonSelected?.base_experience"
            :height="pokemonSelected?.height"
            :weight="pokemonSelected?.weight"
            :img="pokemonSelected?.sprites?.dream_world?.front_default"
            :moves="pokemonSelected?.moves && pokemonSelected.moves.length > 0 ? pokemonSelected.moves.slice(0, 3).map(move => move.move.name.toUpperCase()).join(', ') : ''"
            :loading="loading"
          />

          </div>

          <div class="col-sm-12 col-md-6">
          <div class="card card-list">
            <div class="card-body row">

              <div class="mb-3">
                <label
                  hidden
                  for="searchPokemonField"
                  type="text"
                  class="form-label"      
                >Pesquisar
                </label>
                <input
                  v-model="searchPokemonField"
                  type="text"
                  class="form-control"
                  id="searchPokemonField"
                  placeholder="Pesquisar"                  
                />
              </div>

              <div class="col-sm-12 col-md-12">                 
                <div class="card card-list">
                  <div class="card-body row">
                  <ListPokemons 
                  v-for="pokemon in pokemonsFiltered"
                  :key="pokemon.name"
                  :name="pokemon.name"
                  :urlBaseSgv="urlBaseSgv + pokemon.url.split('/')[6] + '.svg'"
                  @Click="selectPokemon(pokemon)"
                  />    
                  </div>            
                </div>               
              </div>

             
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>


<style scoped>

.card-list {
  max-height: 75vh;
  overflow-y: auto;
  overflow-x: hidden;
}

::-webkit-scrollbar {
        width: 10px;
    }

    ::-webkit-scrollbar-track {
        background:#2b1468;
    }

    ::-webkit-scrollbar-thumb {
        background: #62bbe8;
        border-radius: 30px;
    }

</style>
