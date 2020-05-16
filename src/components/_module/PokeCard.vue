<template>
<div class="row mr-0 ml-0">
     <div class="card evn-secondary my-4 mx-3" v-for="pokemon in pokemons" :key="pokemon.id"
     @click="setPokemonUrl(pokemon.url)">
        <img :src="imageUrl + pokemon.id +'.png'" alt="pokemon"
        style="height: 200px; object-fit: cover;">
        <div class="card-body">
          <p class="card-text text-light evn-title">
          <i class="fas fa-campground mr-2"></i> {{pokemon.name}} </p>
        </div>
    </div>
</div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'Card',
  props: [
    'imageUrl',
    'apiUrl'
  ],
  data () {
    return {
      pokemons: [],
      urlPokemon: [],
      newUrl: ''
    }
  },
  methods: {
    fetchdata (newUrl) {
      axios.get(newUrl)
        .then(res => {
          this.urlPokemon = res.data.results
          res.data.results.forEach(urlPokemon => {
            axios.get(urlPokemon.url)
              .then(res => {
                this.pokemons.push(res.data)
              })
              .catch(error => {
                console.error(error)
              })
          })
        })
        .catch(error => {
          /* eslint-disable no-console */
          console.log(error)
          /* eslint-enable no-console */
        })
    }
  },
  mounted () {
    this.fetchdata(this.newUrl)
  },
  created () {
    this.newUrl = this.apiUrl
  }
}
</script>

<style lang="scss" scoped>
.card{
  width: 235px;
}
</style>
