<template>
  <div class="container">
    <h1>Pokedex</h1>
    <section v-if="pokemons.length > 0" class="pokemon-section">
      <PokemonCard
        v-for="(pokemon, index) in pokemons"
        :pokemonName="pokemon.name"
        :pokemonImage="pokemon.sprites.other['official-artwork'].front_default"
        :key="pokemon.name"
        :pokemonType="pokemon.types[0].type.name"
      />
      <!-- {{ pokemon.sprites.other["official-artwork"] }} -->
    </section>
    <Paginator :page="page" @nextPage="nextPage" @previousPage="previousPage" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Paginator from "../components/Paginator.vue";
import PokemonCard from "../components/PokemonCard.vue";
import axios from "axios";
export default defineComponent({
  setup() {
    return {};
  },
  components: { Paginator, PokemonCard },
  methods: {
    nextPage() {
      console.log(this.page);
      this.page++;
      this.getPagePokemons();
    },
    previousPage() {
      if (this.page > 1) {
        this.page--;
        this.getPagePokemons();
      }
    },
    async getPokemon(pokemonId: Number) {
      const result = await axios.get(
        "https://pokeapi.co/api/v2/pokemon/" + pokemonId
      );
      return result;
    },
    async getPagePokemons() {
      this.pokemons = [];
      for (
        let i = this.page === 1 ? 1 : this.pokemonsPerPage * (this.page - 1);
        i <= this.page * this.pokemonsPerPage;
        i++
      ) {
        await this.getPokemon(i).then((res) => {
          // console.log(res.data.);
          this.pokemons.push(res.data);
        });
      }
      console.log(this.pokemons);
    },
  },
  data() {
    return {
      pokemons: [],
      pokemonsPerPage: 10,
      page: 1,
    };
  },
  mounted() {
    this.getPagePokemons();
  },
});
</script>

<style lang="scss" scoped>
.pokemon-section {
  width: 100%;
  display: flex;
  gap: 1rem;
}
</style>