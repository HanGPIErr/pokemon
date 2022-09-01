<template>
  <div>
    <Header />
    <RouterView />
    <BottomButton />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Header from './components/Header.vue';
import BottomButton from './components/BottomButton.vue';

export default defineComponent({
  setup() {

    return {};
  },
  components: { Header, BottomButton },

})
</script>

<style scoped>
</style>