<template>
    <div id="app">
        <Resume :data="data" />
    </div>
</template>

<script>
import Resume from "./Resume";

export default {
    name: "app",
    data: () => ({ data: {} }),
    // Fetch JSON data upon creation.
    created: function() {
        fetch("data.json")
            .then(res => res.json())
            .then(data => (this.data = data));
    },
    components: {
        Resume,
    },
};
</script>

<style lang="scss">
@import "./mixins.scss";

body {
    // Enable box sizing
    box-sizing: border-box;
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    *,
    *:before,
    *:after {
        -webkit-box-sizing: inherit;
        -moz-box-sizing: inherit;
        box-sizing: inherit;
    }

    // Avoid overflow font
    -moz-text-size-adjust: none;
    -webkit-text-size-adjust: none;
    -ms-text-size-adjust: none;

    // Keep #app centred
    // prettier-ignore
    > #app { margin: 0 auto; }

    // Contrasting background
    margin: 0;
    background-color: lightgrey;

    /* Global styling defaults */
    font-family: $font-family;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;

    // prettier-ignore
    p, h1, h2, h3, h4, h5, h6 {
        // normalize text spacing
        margin: 0;
        padding: 0;

        // Overwrite user style agent
        /* font-weight: normal; */
        /* color: black; */
    }
}

// Keep resume centered.
// prettier-ignore
#app > div { margin: 0 auto; }
</style>
