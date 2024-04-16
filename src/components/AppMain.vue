<!-- JS -->
<script>


/* IMPORTO POKEDEX */
import Pokédex from './Pokédex.vue'
/* IMPORTO STORE */
import { store } from '../date/store';


/* ESPORTAZIONE */
export default {


    /* NOME PAGINA */
    name: 'AppMain',


    /* COMPONENTI */
    components: { Pokédex },


    /* DATI DI BASE DA UTILIZZARE NEL TEMPLATE */
    data: () => ({


        /* RECUPERO STORE */
        store,
    }),

};

</script>

<!-- HTML -->
<template>

    <!-- MAIN -->
    <main>
        <!-- SE STORE.LOADING E' TRUE -->
        <h1 v-if="store.loading">Loading...</h1>
        <!-- ALTRIMENTI SEZIONE POKEDEX -->
        <section v-else id="recipe-pokedex">
            <!-- TITOLO -->
            <h2>pokedex</h2>
            <!-- RECIPIENTE POKEMONS -->
            <div class="recipe-pokemons">
                <!-- POKEDEX -->
                <Pokédex />
            </div>
        </section>
    </main>

</template>


<!-- CSS -->
<style lang="scss" scoped>
/* LOADING  */
h1 {
    text-align: center;
}

/* RECIPIENTE POKEDEX */
#recipe-pokedex {
    background-color: rgba(215, 16, 16, 0.532);
    min-height: 500px;
    display: flex;
    justify-content: center;
    flex-direction: column;

    /* TITOLO */
    h2 {
        text-transform: uppercase;
        text-align: center;
        font-size: 30px;

    }

}

/* RECIPIENTE POKEMONS */
.recipe-pokemons {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    border: 1px solid;
    margin: 10px;
}
</style>