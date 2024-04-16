<!-- JS -->
<script>


/* IMPORTO HEADER */
import AppHeader from './components/AppHeader.vue'
/* IMPORTO MAIN */
import AppMain from './components/AppMain.vue';
/* IMPORTO FOOTER */
import AppFooter from './components/AppFooter.vue';
/* IMPORTO SELECTMENU */
import SelectMenu from './components/SelectMenu.vue';
/* IMPORTO STORE */
import { store } from './date/store';
/* IMPORTO AXIOS */
import axios from 'axios';
/* CHIAMATA API */
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
/* IMPORTO ARRAY DI DATI PER LA SELECT */
import { options } from './assets/dateAPI';


/* ESPORTAZIONE */
export default {


    /* NOME PAGINA */
    name: 'MyApp',


    /* DATI DI BASE DA UTILIZZARE NEL TEMPLATE (UTILIZZANDO LE PROPS) */
    data: () => ({
        options
    }),


    /* COMPONENTI */
    components: { AppHeader, AppMain, AppFooter, SelectMenu },


    /* FUNZIONI */
    methods: {


        /* FNZIONE PER CHIAMARE API E GLI PASSO COME ARGOMENTO ENDOPOINT */
        fetchPokemon(endpoint) {


            /* RECUPERO DA STORE IL LOADING E LO RINOMINO A TRUE */
            store.loading = true


            /* AXIOS */
            axios.get(endpoint).then(res => {


                /* CONTROLLO RISPOSTA */
                console.log(res.data.docs)


                /* RECUPERO DA STORE ARRAY VUOTO E LO RIASSEGNO CON I DATI CHE CI SONO DENTRO RES.DATA.DOCS */
                store.pokemons = res.data.docs


                /* ESEGUI IN OGNI CASO */
            }).then(() => {


                /* RECUPERO STORE E LO RIASSEGNO A FALSE */
                store.loading = false
            })
        },



        /* FUNZIONE PER TIPOLOGIA A CUI PASSO COME PARAMETRO IL VALORE SCELTO DALL'UTENTE (PASSATO TRAMITE EMITS) */
        pokemonChoice(menu) {


            /* CONTROLLO RISPOSTA */
            console.log('scelto', menu)


            /* ASSEGNO A UNA VARIBILE LA UNA STRINGA DI QUERY E GLI PASSO ENDOPOINT E IL VALORE SCELTO DALL'UTENTE */
            const search = `${endpoint}?eq[type1]=${menu}`


            /* RICHIAMTO LA FUNZIONE CHE CHIAMA API E GLI PASSO COME ARGOMENTO LA VARIABILE CREATA */
            this.fetchPokemon(search)

        }
    },


    /* ALL'AVVIO DELLA PAGINA */
    created() {


        /* RICHIAMO LA FUNZIONE E PASSO COME ARGOMENTO ENDPOINT */
        this.fetchPokemon(endpoint)
    }

};

</script>


<!-- HTML -->
<template>

    <!-- HEADER -->
    <AppHeader />
    <!-- SELECTMENU, EVENTO GENERATO E PASSOTO TRAMITE EMITS (SELECTMENU)  -->
    <SelectMenu :options="options" @select-menu="pokemonChoice" />
    <!-- MAIN -->
    <AppMain :options="options" />
    <!-- FOOTER -->
    <AppFooter />

</template>


<!-- CSS -->
<style>

/* BODY */
body {
    height: 100vh;
}

</style>
