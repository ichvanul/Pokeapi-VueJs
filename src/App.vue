<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@500&family=Rubik:wght@500&display=swap');

  *{
    margin: 0;
    padding: 0;
  }
  #app {
    min-height: 100vh;
  }
  .evn-primary{
    background-color: #2c3e50;
  }
  .evn-secondary{
    background-color: #34495e;
  }
  .evn-title{
    font-family: 'Rubik', sans-serif;
  }
  .evn-desc{
    font-family: 'Poppins', sans-serif;
  }
  .evn-shadow{
    box-shadow: 0 0px 10px 0 #000000, 0 0px 5px 0 #000000;
  }
  .evn-rounded{
    border-radius: 10px;
  }
</style>
