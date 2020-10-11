<template>
    <div>
        <form>
            <h2>Login</h2>
            <label for="user">Usuario</label>
            <input type="text" placeholder="Usuario" v-model="user"><br>
            <label for="user">Contrasena</label>
            <input type="password" v-model="password"><br>
            <button @click.prevent="login">Ingresar</button>
        </form>
    </div>
</template>

<script>
import firebase from 'firebase'
export default {
    name: 'login-component',
    // props: {},
    data: function(){
        return {
            user:"",
            password:"",
        }
    },
    // computed: {},
    methods: {
        login:function(){
        console.log(firebase.auth)
        console.log(firebase.default.auth)
        firebase.auth().signInWithEmailAndPassword(this.user, this.password)
        .then((resp)=>{
            console.log(resp,'result')
            this.$router.push('/home')
        })
        .catch(function(error){
            let errorCode = error.code;
            let errorMessage = error.message;
            console.log(errorCode, errorMessage);
        })
        },
    },
    //components: {},
}
</script>

<style scoped>
    
</style>