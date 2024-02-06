<!-- JS -->
<script>

export default {
    // NOME
    name: 'SelectMenu',
    // DATI
    data: () => ({
        menu: ''
    }),
    // EMITS
    emits: ['select-menu'],
    // PROPS
    props: {
        options: Array
    }
      
};

</script>

<!-- HTML -->
<template>
    <div>
        <!-- SELECT -->
        <select v-model="menu" @change="$emit('select-menu', menu)">
            <option>--</option>
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