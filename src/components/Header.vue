<template>
    <div class="resume-header">
        <h1>Hewwo</h1>
        <!-- <about></about>
        <contact></contact> -->
    </div>
</template>

<script>
export default {
    name: "resume-header",
    props: {
        about: { type: String, default: "" },
        contact: { type: String, default: "" },
    },
    components: {},
};
</script>

<style lang="scss">
@import "../mixins.scss";

.resume-header {
    background-image: linear-gradient(
        rgb(33, 33, 33),
        rgb(34, 34, 34) 33%,
        90%,
        rgb(77, 76, 76)
    );
    padding: 30px;
    color: $highlight-dark;
    font-size: $header-font-size;
}
</style>
