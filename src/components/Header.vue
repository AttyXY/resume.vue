<template>
    <div class="resume-header">
        <div class="about">
            <h1>{{ about.name }}</h1>
            <!-- <h6>{{ about.blurb }}</h6> -->
        </div>
        <div class="contact">
            <a
                class="link"
                v-for="contact in contacts"
                :key="contact.url"
                :href="contact.url"
                :target="contact.newtab !== false && '_blank'"
                rel="noopener noreferrer"
            >
                <p>{{ contact.url }}</p>
                <i :class="contact.icon" />
            </a>
        </div>
    </div>
</template>

<script>
export default {
    name: "resume-header",
    props: {
        about: { type: Object, default: () => ({}) },
        contacts: { type: Array, default: () => [] },
    },
    components: {},
};
</script>

<style lang="scss">
@import "../mixins.scss";

.resume-header {
    justify-content: space-between;
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
.about {
    display: flex;
    flex-direction: column;
    h1 {
        font-weight: bold !important;
        color: $highlight-dark !important;
    }
}
.contact {
    display: flex;
    flex-direction: column;
    font-size: $content-font-size;
    & a {
        display: flex;
        flex-direction: row;
        justify-content: flex-end;
        /* text-align: right; */
        text-decoration: none;
        * {
            color: $highlight !important;
        }
        & i {
            /* background-image: -webkit-linear-gradient(#9c47fc, #356ad2); */
            padding: 0 5px;
        }
    }
}
</style>
