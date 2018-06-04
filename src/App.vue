<template>
    <div id="app">
        <div class="wrapper">
            <toggle-switch aria-controls="live-content">
                Toggle!
            </toggle-switch>

            <span id="live-content" role="region" aria-live="polite" aria-atomic="true">
                ...
            </span>
        </div>
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
        -moz-osx-font-smoothing: grayscale;
        -webkit-font-smoothing: antialiased;
        align-items: center;
        color: #2c3e50;
        display: flex;
        font-family: Avenir, Helvetica, Arial, sans-serif;
        justify-content: center;
        height: 100vh;
    }

    #live-content, .toggle-switch {
        display: flex;
        justify-content: center;
    }

    .wrapper {
        display: block;
    }
</style>
