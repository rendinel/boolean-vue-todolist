<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
 
  
     <ToDo/>

</template>

<script>
import ToDo from './components/ToDo.vue'

export default {
  name: 'App',
  components: {
    ToDo
  }
}
</script>

<style lang="scss">
* {
box-sizing: border-box;
margin: 0;
font-family: "Montserrat", sans-serif;
}


</style>
