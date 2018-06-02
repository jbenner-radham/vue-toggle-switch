<template>
    <div id="app">
        <toggle-switch>Toggle!</toggle-switch>
    </div>
</template>

<script>
    import ToggleSwitch from './components/ToggleSwitch.vue';

    export default {
        name: 'App',
        components: {
            ToggleSwitch
        }
    };
</script>

<style lang="scss">
    #app {
        display: flex;
        justify-content: space-around;
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 3rem;
    }
</style>
