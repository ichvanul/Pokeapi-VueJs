<template>
  <div class="home">
    <PokeSearch :apiUrl="apiUrl" @setPokemonUrl="setPokemonUrl"/>
    <PokeCard :apiUrl="apiUrl" :imageUrl="imageUrl"/>
    <PokeDetail  v-if="showDetail" :pokemonUrl="pokemonUrl" :imageUrl="imageUrl" @closeDetail="closeDetail"/>
  </div>
</template>

<script>
import PokeSearch from '../components/_module/PokeSearch.vue'
import PokeCard from '../components/_module/PokeCard.vue'
import PokeDetail from '../components/_module/PokeDetail.vue'

export default {
  name: 'Home',
  components: {
    PokeSearch,
    PokeCard,
    PokeDetail
  },
  data () {
    return {
      imageUrl: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/',
      apiUrl: 'https://pokeapi.co/api/v2/pokemon/',
      pokemonUrl: '',
      showDetail: false
    }
  },
  methods: {
    setPokemonUrl (url) {
      this.pokemonUrl = url
      this.showDetail = true
    },
    closeDetail () {
      this.pokemonUrl = ''
      this.showDetail = false
    }
  }
}
</script>
