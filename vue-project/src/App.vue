<template>
<input type="text" v-model="username" placeholder="Name">
<input type="password" v-model="userPass" placeholder="Pass">
<input type="email" v-model="userEmail" name="email" placeholder="Email">
<button @click="sendData()">Send</button>
<p className="err">{{ err }}</p>

<div v-for="(e,index) in users" :key="index">
  <h3>{{ e.name }}</h3>
  <p>{{ e.pass }}, {{ e.email }}</p>
</div>
<div v-if="users.length == 0">
  there are no users
</div>
<div v-else-if="users.length == 1">
  There is only 1 user
</div>

<div v-else>
There are users
</div>

</template>

<script>
  export default {
      data() {
        return {
         users : [],
         err:'',
         username : '',
         userPass : '',
         userEmail : ''
        }
      },methods : {
        sendData() {
          if(this.username === '' || this.userPass === '' || this.userEmail === '') {
           this.err = 'Fill every'
            return
          }
          this.err = ''

          this.users.push({
            name : this.username,
            pass : this.userPass,
            email : this.userEmail,
          })
        }
      }
  }
</script>

<style scoped>


</style>