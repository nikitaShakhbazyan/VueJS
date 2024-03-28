<template>
<input type="text" v-model="username" placeholder="Name">
<input type="password" v-model="userPass" placeholder="Pass">
<input type="email" v-model="userEmail" name="email" placeholder="Email">
<p><b> {{ username }} </b> this is name</p>
<p> <b>{{ userPass }}</b> this is pass</p>
<p> <b>{{ userEmail }} </b> this is email</p>
</template>

<script>
  export default {
      data() {
        return {
         username : '',
         userPass : '',
         userEmail : ''
        }
      },methods : {
      }
  }
</script>

<style scoped>


</style>