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

<template>
  <div class="wrapper">
    <h1>The Weather App</h1>
    <p>Check the weather {{ city == "" ? "in your city" : cityName}} </p>
    <input type="text" v-model="city" placeholder="Type city">
    <button v-if="city != ''" @click="getWeather()">Get Information</button>
    <button disabled v-else>Type city name</button>
    <p class="err">{{ err }}</p>
    <div class="apiDiv">
    <p v-if="info != null">Temperature is : {{ info.main.temp }} ℃</p>
    <p v-if="info != null"> Feels like : {{ info.main.feels_like }} ℃</p>
    <p v-if="info != null"> Temperature min : {{ info.main.temp_min }} ℃</p>
    <p v-if="info != null"> Temperature max : {{ info.main.temp_max }} ℃</p>
    <p v-if="info != null"> Pressure is : {{ info.main.pressure }} hPa</p>
    <p v-if="info != null"> Humidity : {{ info.main.humidity }} %</p>
    <p v-if="info != null"> Wind speed is : {{ info.wind.speed }} m/s and wind direction is {{ info.wind.deg }} deg</p>


  </div>
  </div>
</template>

<style scoped>
.err {
  color: red;
}

.wrapper {
  width: 900px;
  height: 500px;
  border-radius: 50px;
  background-color: #1f0f24;
  color: white;
  padding: 20px;
  text-align: center;
}

.wrapper h1 {
  margin-top: 50px;
}

.wrapper p {
  margin-top: 20px;
}

.wrapper input {
  margin-top: 30px;
  background-color: transparent;
  border: 1px solid gold;
  border-bottom: 2px solid #110813;
  color: #fcfcfc;
  font-size: 14px;
  padding:5px 8px;
  outline: none;
  width: 200px;
}
.wrapper input:focus {
  border-bottom-color: #6e2d7d;
}

.wrapper button {
  background: #e3bc4b;
  color: #fff;
  border-radius: 10px;
  border: 2px solid #b99935;
  padding: 10px 15px;
  margin-left: 20px;
  cursor: pointer;
  transition: 500ms ease;
}

.wrapper button:hover {
  transform: scale(1.1) translateY(-5px)
}

.wrapper button:disabled {
  background: #685725;
  cursor: not-allowed;
}

@media (max-width: 880px) {
  
  .wrapper {
  width: 300px;
  height: 600px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-evenly;
  border-radius: 50px;
  background-color: #1f0f24;
  color: white;
  padding: 20px;
  text-align: center;
}

}

</style>