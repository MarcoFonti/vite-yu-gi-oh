<!-- JS -->
<script>


/* IMPORTO STORE */
import { store } from '../date/store';


/* ESPORTAZIONE */
export default {


    /* NOME PAGINA */
    name: 'Pokédex',


    /* DATI DI BASE DA UTILIZZARE NEL TEMPLATE */
    data: () => ({


        /* RECUPERO STORE */
        store
    }),
};

</script>

<!-- HTML -->
<template>

    <!-- CICLO SULL'ARRAY E RECUPERO OGNI SINGOLO ELEMENTO -->
    <div class="card" v-for="pokemon in store.pokemons">
        <img :src="pokemon.imageUrl" :alt="pokemon.name">
        <div class="recipe-card">
            <div>{{ pokemon.name }}</div>
            <div>{{ pokemon.type1 }}</div>
            <div>{{ pokemon.total }}</div>
        </div>
    </div>
</template>


<!-- CSS -->
<style lang="scss" scoped>

/* CARD */
.card {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: calc(100% / 5);
    text-align: center;
    background-color: rgb(207, 215, 215);
    padding-top: 10px;
    padding-bottom: 10px;

    /* IMMAGINI */
    img {
        width: 250px;
        height: 250px;
        border-radius: 20%;
        margin-bottom: 5px;
        border: 3px solid;
    }

}

</style>