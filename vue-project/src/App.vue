<template>
  <h2>{{ info }}</h2>
  <p>{{ pTag }}</p>

  <button @click="userData()" type="button">Send</button>
</template>

<script>
  export default {
      data() {
        return {
          info : 'Title',
          pTag : "Lorem, ipsum dolor sit amet consectetur adipisicing elit. A, vel."
        }
      },
      methods : {
        userData() {
          this.info='this inf'
          this.pTag = 'Another p tag'
        }
      }
  }
</script>

<style scoped>
  h2 {
    color: green;
    font-weight: bold;
  }
  p{
    color: rebeccapurple;
  }

</style>