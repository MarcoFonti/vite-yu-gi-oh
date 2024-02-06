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
        Selects: Array
    }
      
};

</script>

<!-- HTML -->
<template>
    <!-- SELECT -->
    <form @submit.prevent="$emit('select-menu', menu)" >
        <select v-model="menu">
            <option>--</option>
            <option v-for="(select, i) in Selects" :key="i">{{ select }}</option>
        </select>
    </form>
</template>

<!-- CSS -->
<style lang="scss" scoped>

/* FORM */
form {
    display: flex;
    justify-content: flex-end;
    margin: 20px;

    /* SELECT */
    select {
        width: 100px;
        height: 30px;
    }
}

</style>