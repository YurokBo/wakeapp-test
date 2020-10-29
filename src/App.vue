<template>

    <Header/>
    <About/>
    <Games />

</template>

<script>

    import Header from "./components/Header/Header";
    import About from "./components/About/About";
    import Games from "./components/Games/Games";

    export default {
        name: 'App',
        components: {
            Games,
            About,
            Header,

        }
    }
</script>

<style lang="scss">

    @import "@/assets/styles/base.scss";

</style>
