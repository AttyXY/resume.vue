<template>
    <div class="sidebar">
        <h1 class="subheader">SIDEBAR</h1>
    </div>
</template>

<script>
export default {
    name: "sidebar",
    components: {},
};
</script>

<style lang="scss">
@import "../mixins.scss";

.sidebar {
    background-color: rgb(246, 246, 246);
    padding: 30px;
    color: $highlight;
    font-size: $subheader-font-size;
}
</style>
