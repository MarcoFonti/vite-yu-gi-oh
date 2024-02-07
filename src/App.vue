<!-- JS -->
<script>

//IMPORTO HEADER
import AppHeader from './components/AppHeader.vue'
// IMPORTO MAIN
import AppMain from './components/AppMain.vue';
// IMPORTO FOOTER
import AppFooter from './components/AppFooter.vue';
// IMPORTO SELECTMENU
import SelectMenu from './components/SelectMenu.vue';
// IMPORTO STORE
import { store } from './data/store';
// IMPORTO AXIOS
import axios from 'axios';
// VARIBILE API
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
// IMPORTO ARRAYOPTIONS
import { options } from './assets/dataNotAPI';


export default {
    // NOME
    name: 'MyApp',
    data: () => ({
        options
    }),
    // COMPONENTI
    components: { AppHeader, AppMain, AppFooter,  SelectMenu },
    // FUNZIONI
    methods: {
        // FUNZIONE API
        fetchPokemon(endpoint) {
            store.loading = true
            axios.get(endpoint).then(res => {
                store.pokemons = res.data.docs
        
            }).then(()=> {
                store.loading = false
            })
        },
        // FUNZIONE API TIPOLOGIA POKEMON
        pokemonChoice(menu) {
            console.log('scelto', menu )
            const search = `${endpoint}?eq[type1]=${menu}`
            this.fetchPokemon(search)

        }
    },
    // ALL'AVVIO DELLA PAGINA
    created() {
        this.fetchPokemon(endpoint)  
    }
   
};

</script>

<!-- HTML -->
<template>
    <!-- HEADER -->
    <AppHeader/>
    <!-- SELECTMENU -->
    <SelectMenu :options="options" @select-menu="pokemonChoice"/>
    <!-- MAIN -->
    <AppMain :options="options"/>
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
