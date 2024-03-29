<template>

</template>
<script>
  import axios from 'axios'

  export default {
    data() {
      return {
        city:'',
        err : '',
        info:null
      }
    },
    computed : {
      cityName () {
        return "'" + this.city + "'"
      }
    },
    methods : {
      getWeather () {
        if(this.city.trim().length < 3) {
          this.err = "City consists at least 3 characters"
          return false
        }
          this.err = ''

          axios.get(`https://api.openweathermap.org/data/2.5/weather?q=${this.city}&units=metric&appid=10cdd5e70108c087661ce63737780047`)
          .then((res) => this.info = res.data)
      }
    }
  }
</script>

<style scoped>


</style>