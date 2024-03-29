<template>

<div>
  <h3>{{ user.name }}</h3>
  <p>{{ user.pass }}, {{ user.email }}</p>
  <button @click="deleteUser">Delete</button>
</div>

</template>

<script>
export default  {
    props:{
        user : {
            type: Object,
            required:true
        },
        deleteUser : {
            type:Function,
            required:true
        },
        index: {
            type: Number,
            required: true
        }
    }
}

</script>

<style scoped>

</style>