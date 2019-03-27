<template>
    <button v-on:click="openlink(linkTo)">{{buttonText}}</button>
</template>

<script>
    export default {
        name: "navbarButton2",
        props: ['buttonText','linkTo'],
        methods: {
            openlink(_linkTo) {
                window.open(_linkTo,'_blank');
            }
        }
    }
</script>

<style scoped>

</style>