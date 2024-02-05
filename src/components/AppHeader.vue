<!-- JS -->
<script>


export default {
    // NOME
    name: 'AppHeader',
      
};
</script>

<!-- HTML -->
<template>
    <header id="recipe-header">
        <h1>pokemon</h1>
    </header>
</template>

<!-- CSS -->
<style lang="scss" scoped>

#recipe-header {
    display: flex;
    background-color: #ffa500;

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