<template>
    <div id="app">
        <Resume :data="data" />
    </div>
</template>

<script>
import Resume from "./Resume";

export default {
    name: "app",
    components: {
        Resume,
    },
};
</script>

<style lang="scss">
@import "./mixins.scss";

#app {
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;

    // Enable box sizing
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;

    // Contrasting background
    background-color: lightgrey;
    margin: 0;

    /* Global styling for resume */
    font-family: $font-family;

    // Normalize spacing around text.
    // prettier-ignore
    p, h1, h2, h3, h4, h5 {
        margin: 0;
        padding: 0;
    }

    // Keep #app centered.
    // prettier-ignore
    > #app { margin: 0 auto; }
}
*,
*:before,
*:after {
    -webkit-box-sizing: inherit;
    -moz-box-sizing: inherit;
    box-sizing: inherit;
}
</style>
