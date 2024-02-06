<!-- JS -->
<script>

// IMPORTO STORE
import { store } from '../data/store';

export default {
    // NOME
    name: 'Pokédex',
    // DATI
    data:() => ({
        store
    }),
    
    
};

</script>

<!-- HTML -->
<template>
    <!-- V-FOR PER CREARE LE CARD -->
    <div class="card" v-for="pokemon in store.pokemons">
        <img :src="pokemon.imageUrl" :alt="pokemon.name">
        <div class="recipe-card">
            <div>{{ pokemon.name }}</div>
            <div>{{ pokemon.type1 }}</div>
            <div>{{ pokemon.total}}</div>
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
        margin-bottom: 5px ;
        border: 3px solid;
    }

}

</style>