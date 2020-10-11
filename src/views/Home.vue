<template>
  <div class="home">
    <button @click="logout">Salir</button><br>
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import firebase from 'firebase'

export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  methods:{
    logout:function(){
      firebase.auth().signOut()
      .then(()=>{
        this.$router.push('/')
      })
      .catch(function(error){
        console.log(error)
      })
    }
  },
}
</script>
