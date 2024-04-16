<!-- JS -->
<script>


/* ESPORTAZIONE */
export default {


    /* NOME PAGINA */
    name: 'SelectMenu',


    /* DATI DI BASE DA UTILIZZARE NEL TEMPLATE */
    data: () => ({


        /* CREO UN COLLEGAMENTO CON CIO' CHE SCRIVERA' L'UTENTE */
        menu: ''
    }),



    /* EMITS (INVIO AD APP) */
    emits: ['select-menu'],


    /* PROPS CHE RICEVE UN ARRAY (DA APP) */
    props: {
        options: Array
    }
};

</script>

<!-- HTML -->
<template>

    <div>
        <!-- CREO UNA SELECT A CUI USO COME DIRETTIVA UN V-MODEL PER RECUPERARE IL VALORE SCELTO DALL'UTENTE E AL EVENTO CHANGE PASSO UN EMIT CON ARGOMENTO (IL NOME CREATO NELL'EMITS) E IL VALORE SCELTO DALL'UTENTE (MENU) -->
        <select v-model="menu" @change="$emit('select-menu', menu)">
            <option>--</option>
            <!-- CICLO SULL'ARRAY E RECUPERO OGNI SINGOLO ELEMENTO E INDICE -->
            <option v-for="(select, i) in options" :key="i">{{ select }}</option>
        </select>
    </div>

</template>


<!-- CSS -->
<style lang="scss" scoped>
/* CONTENITORE */
div {

    display: flex;
    justify-content: flex-end;
    background-color: red;
    padding: 10px;

    /* SELECT */
    select {
        width: 100px;
        height: 30px;
        margin-top: 10px;
    }

}
</style>