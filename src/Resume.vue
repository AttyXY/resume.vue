<template>
    <div class="resume">
        <Header v-bind="headerData" />
        <div class="content">
            <Experience :data="experienceData" />
            <Sidebar :data="sidebarData" />
        </div>
    </div>
</template>

<script>
import _ from "lodash";
import Experience from "./components/Experience";
import Header from "./components/Header";
import Sidebar from "./components/Sidebar";

export default {
    name: "resume",
    props: {
        data: { type: Object, required: true },
    },
    computed: {
        headerData: function() {
            return _.pick(this.data.header, ["about", "contacts"]);
        },
        experienceData: function() {
            return this.data.experience;
        },
        sidebarData: function() {
            return this.data.sideba;
        },
    },
    components: {
        Header: Header,
        Experience,
        Sidebar,
    },
};
</script>

<style lang="scss">
.resume {
    // Letter paper size
    width: 8.5in;
    height: 11in;

    display: flex;
    flex-direction: column;
}

.resume-header {
    flex: 0 1 auto;
    display: flex;
    flex-direction: row;
}

.content {
    display: flex;
    flex-direction: row;

    flex: 1;
    & .subheader {
        border-bottom: 0.001rem solid black;
    }
}

.column {
    padding-top: 0.4rem;
    padding-bottom: 0.4rem;
}

.experience-container {
    width: 6in;
}

.sidebar-container {
    width: calc(8.5in - 6in);
}
</style>
