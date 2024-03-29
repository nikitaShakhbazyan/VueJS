<script>
  export default {
    data() {
      return {
        city:'',
      }
    }
  }
</script>

<template>
  <div className="wrapper">
    <h1>The Weather App</h1>
    <p>Check the weather {{ city == "" ? "in your city" : "'"+city+"'"}} </p>
    <input type="text" v-model="city" placeholder="Type city">
    <button v-if="city != ''">Get Information</button>
    <button disabled v-else>Type city name</button>
  </div>
</template>

<style scoped>
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
  border: 0px;
  border-bottom: 2px solid #110813;
  color: #fcfcfc;
  font-size: 14px;
  padding:5px 8px;
  outline: none;
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
</style>