<template>
 <div id="app">
    <div>POKEMON<img alt="Vue logo" src="https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/70643e0f-c6fc-4b32-8403-8978afd31dc8/d3gallt-a5c09c4f-298c-4f56-855d-bc084f1ce783.gif?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOiIsImlzcyI6InVybjphcHA6Iiwib2JqIjpbW3sicGF0aCI6IlwvZlwvNzA2NDNlMGYtYzZmYy00YjMyLTg0MDMtODk3OGFmZDMxZGM4XC9kM2dhbGx0LWE1YzA5YzRmLTI5OGMtNGY1Ni04NTVkLWJjMDg0ZjFjZTc4My5naWYifV1dLCJhdWQiOlsidXJuOnNlcnZpY2U6ZmlsZS5kb3dubG9hZCJdfQ.zBUosRedanAsko951oSXILBMFci8EODSxFKBmFWFTQs" width="200">BATTLE</div>
    <br>
    <game/>
   </div>
    
</template>

<script>

import game from "./components/game.vue"

export default {
  name: 'App',
  components: {
    game,
    
  },
  
  
}
</script>

<style>
#app {
  background-image: url(https://media.tenor.com/images/7ab5a1ec440ea24126c2541784e1682b/tenor.gif);
  background-size: cover;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  font-size: 70px;
}
</style>
