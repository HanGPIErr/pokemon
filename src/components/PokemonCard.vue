<template>
    <div class="pokemon-card-container" :style="{ background: background }">
      <h3 class="pokemon-name">{{ pokemonName }}</h3>
      <img :src="pokemonImage" alt="pokemon image" class="pokemon-image" />
      <!-- {{ pokemonType }} -->
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent } from "vue";
  export default defineComponent({
    props: {
      pokemonName: {
        type: String,
        required: true,
      },
      pokemonImage: {
        type: String,
      },
      pokemonType: {
        type: String,
      },
    },
    setup() {
      return {};
    },
    computed: {
      background() {
        if (this.pokemonType === "grass" || this.pokemonType === "bug") {
          return "#00FFAB";
        } else if (this.pokemonType === "fire") {
          return "#F94C66";
        } else if (this.pokemonType === "water") {
          return "#00D7FF";
        }
        return "#fff";
      },
    },
  });
  </script>
  
  <style lang="scss" scoped>
  .pokemon-card-container {
    height: 202;
    width: 133px;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 12px 0;
    border-radius: 16px;
    .pokemon-name {
      background: #00000040;
      color: #fff;
      font-size: 16px;
      padding: 4px 12px;
      border-radius: 16px;
    }
    .pokemon-image {
      max-width: 100px;
    }
  }
  </style>