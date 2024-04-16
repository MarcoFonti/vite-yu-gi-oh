<!-- JS -->
<script>


/* ESPORTAZIONE */
export default {


    /* NOME PAGINA */
    name: 'AppFooter',

};

</script>

<!-- HTML -->
<template>

    <!-- FOOTER -->
    <footer>
        <ul>
            <li>Centro Pokemon</li>
            <li>Palestre</li>
            <li>Classifica</li>
        </ul>
    </footer>

</template>

<!-- CSS -->
<style scoped lang="scss">
/* LISTA */
ul {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 20px;
    background-color: orange;
    margin: 0px;
    padding: 20px;

    /* CONTENUTO LISTA */
    li {
        list-style: none;
        font-size: 20px;
        border-bottom: 1px solid;
    }
}
</style>