<!-- JS -->
<script>


/* ESPORTAZIONE */
export default {


    /* NOME PAGINA */
    name: 'AppHeader',

};

</script>


<!-- HTML -->
<template>

    <!-- HEADER -->
    <header id="recipe-header">
        <!-- TITOLO -->
        <h1>pokemon</h1>
    </header>

</template>


<!-- CSS -->
<style lang="scss" scoped>
/* RECIPENTE HEADER */
#recipe-header {
    display: flex;
    background-color: #ffa500;

    /* TITOLO */
    h1 {
        text-transform: uppercase;
        font-size: 50px;
        width: 100%;
        text-align: center;
        background-color: #ffff00;
        color: #ffa500;
        -webkit-text-stroke: 2px #000000;
        padding: 20px;
    }

}
</style>