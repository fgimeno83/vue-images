<template>
    <div class="ui secondary pointing menu">
        <router-link to="/" class="active item">
            Image Storage        
        </router-link>
        
        <div class="right menu">
            <div v-if="isLoggedIn" class="horizontally">
                <router-link to="/" class="item">Gallery</router-link>
                <router-link to="/upload"  class="item" @click="logout">Upload</router-link>
                <a class="item" @click="logout">Logout</a>
            </div>
            <a v-else href="#" class="ui item" @click="login" >
                Login
            </a>
        </div>
    </div>
</template>

<script>
import { mapActions, mapGetters } from 'vuex'; // Conecta diferentes acciones de diferentes módulos con  una instancia de un componente

export default {
    name: 'AppHeader',
    methods: mapActions(['login', 'logout']), //...mapActions(['login']) de esta forma te permitiría añadir otros métodos a mayores de los map actions
    computed: mapGetters(['isLoggedIn'])
};

</script>

<style scoped>
    .horizontally {
        display: inherit;
    }
</style>