<template>
<nav class="navbar navbar-expand-lg navbar-dark evn-secondary sticky-top">
  <a class="navbar-brand" href="#">Pokemon</a>
  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav mr-auto">
      <li class="nav-item dropdown">
        <a class="nav-link dropdown-toggle"
        href="#" id="navbarDropdown" role="button"
        data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
          Type of Pokemon
        </a>
        <div class="dropdown-menu" aria-labelledby="navbarDropdown">
          <a class="dropdown-item" href="#">Action</a>
        </div>
      </li>
    </ul>
    <form @submit.prevent="setPokemonUrl" class="form-inline my-2 my-lg-0">
      <input v-model="searchValue" class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search">
      <button @click="setPokemonUrl" class="btn btn-outline-warning my-2 my-sm-0" type="submit">Search</button>
    </form>
  </div>
</nav>
</template>

<script>
export default {
  props: [
    'apiUrl'
  ],
  data: () => {
    return {
      searchValue: ''
    }
  },
  methods: {
    setPokemonUrl (url) {
      if (this.searchValue !== '') {
        this.$emit('setPokemonUrl', this.apiUrl + this.searchValue)
      }
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
