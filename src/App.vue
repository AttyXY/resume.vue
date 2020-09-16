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
            // .then(data => console.log(data))
            .then(data => (this.data = data))
            .catch(e => console.log(e));
    },
    components: {
        Resume,
    },
};
</script>

<style lang="scss">
@import "./mixins.scss";

body {
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;

    // Enable box sizing
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
    *,
    *:before,
    *:after {
        -webkit-box-sizing: inherit;
        -moz-box-sizing: inherit;
        box-sizing: inherit;
    }

    // Contrasting background
    background-color: lightgrey;
    margin: 0;

    /* Global styling defaults */
    font-family: $font-family;

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
