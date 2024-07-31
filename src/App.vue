<script lang="">
import { cards } from "./store.js";
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";

export default{
  components: {
    cards,
    AppHeader,
    AppMain,
  }
}

</script>

<template>
  <div>
    <AppHeader />
    <AppMain />
  </div>
</template>

<style>

</style>
