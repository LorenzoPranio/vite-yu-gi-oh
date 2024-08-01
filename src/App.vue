<script>
import { cards } from "./store.js";
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import axios from "axios";

export default{
  data(){
    return{
      cards
    }
  },
  components: {
    AppHeader,
    AppMain
  },
  created(){
  this.get_cards(),
  this.get_archetypes()
  },
  methods:{
    get_cards(){
      axios.get(cards.apiUrl).then((result) =>
      {cards.cardsarray = result.data.data})
    },
    get_archetypes(){
      axios.get(cards.apiArchetypes).then((result) =>
      {cards.archetypesarray = result.data})
    }
  }
}
</script>

<template>
  <div>
    <AppHeader />
    <AppMain />
  </div>
</template>

<style lang="scss">
@use './styles/generals.scss';
</style>
