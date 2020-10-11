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
        
        },
    },
    //components: {},
}
</script>

<style scoped>
    
</style>