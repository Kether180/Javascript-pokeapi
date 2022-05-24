<template>
  <div class="container mx-auto px-4">
    <p class="font-mono text-xl text-white">SEARCH YOUR POKEMON</p>
    <br />
    <SearchBar :apiUrl="apiUrl" @setPokemonUrl="setPokemonUrl" />
    <PokemonList
      :imageUrl="imageUrl"
      :apiUrl="apiUrl"
      @setPokemonUrl="setPokemonUrl"
    />
    <PokemonDetails
      v-if="showDetail"
      :pokemonUrl="pokemonUrl"
      :imageUrl="imageUrl"
      @closeDetail="closeDetail"
    />
  </div>
</template>

<script>
import SearchBar from "./SearchBar.vue";
import PokemonList from "./PokemonList.vue";
import PokemonDetails from "./PokemonDetails.vue";

export default {
  data: () => {
    return {
      imageUrl:
        "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/",
      apiUrl: "https://pokeapi.co/api/v2/pokemon/",
      pokemonUrl: "",
      showDetail: false,
    };
  },
  components: {
    PokemonList,
    SearchBar,
    PokemonDetails,
  },
  methods: {
    setPokemonUrl(url) {
      this.pokemonUrl = url;
      this.showDetail = true;
    },
    closeDetail() {
      this.pokemonUrl = "";
      this.showDetail = false;
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Kanit:wght@200&display=swap");

.container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  padding: 80px;
  width: calc(100% - 30px);
  min-height: calc(100vh - 20px);
  background: radial-gradient(#fa0606, #fc1100);
  border-radius: 0%;
  font-size: rem;
  font-weight: normal;
}

h1 {
  color: #f01111;
}
</style>
