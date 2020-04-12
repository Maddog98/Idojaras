<template>
  <div class="hello">
     <div class="app-title"><p>Weather</p></div>
     <div class="notification"></div>
     <div class="weather-container">
       <div class="weather-icon"><p>itt lesznek a képek ,hogy napos felhős stb</p></div>
       <div class="temperature-value"><p>hány fok van konkrétan lesz itt</p></div>
       <div class="temperature-description"></div>
       <div class="location"><p>helység</p></div>
     </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>


<!-- majd a stílusokat kell megírni  -->
<style scoped>

</style>
