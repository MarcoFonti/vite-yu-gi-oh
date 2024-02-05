<!-- JS -->
<script>

//IMPORTO HEADER
import AppHeader from './components/Appheader.vue'
// IMPORTO MAIN
import AppMain from './components/Appmain.vue';
// IMPORTO FOOTER
import AppFooter from './components/AppFooter.vue';
// IMPORTO STORE
import { store } from './data/store';
// IMPORTO AXIOS
import axios from 'axios';
// VARIBILE API
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';

export default {
    // NOME
    name: 'MyApp',
    // COMPONENTI
    components: { AppHeader, AppMain, AppFooter },
    // ALL'AVVIO DELLA PAGINA
    created() {
        axios.get(endpoint).then(res => {
            store.pokemons = res.data.docs
        })
    }
   
};

</script>

<!-- HTML -->
<template>
    <!-- HEADER -->
    <AppHeader/>
    <!-- MAIN -->
    <AppMain/>
    <!-- FOOTER -->
    <AppFooter/>
</template>

<!-- CSS -->
<style>

/* BODY */
body {
    height: 100vh;
}

</style>
