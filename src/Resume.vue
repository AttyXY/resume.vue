<template>
    <div class="resume">
        <ResumeHeader v-bind="headerData" />
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
            return this.data.sidebar;
        },
    },
    components: {
        ResumeHeader: Header,
        Experience,
        Sidebar,
    },
};
</script>

<style lang="scss">
/* Global layout grid */
.resume {
    // set to Letter paper size
    width: 8.5in;
    height: 11in;

    display: flex;
    flex-direction: column;
}

.resume-header {
    height: 12.5vh; // 1/8 height
    flex: 0 1 auto;

    display: flex;
    flex-direction: row;
}

.content {
    display: flex;
    flex-direction: row;

    height: calc(100vh - 12.5vh);
    flex: 1;
    & .subheader {
        border-bottom: 1.5px solid black;
    }
}

.experience-container {
    width: calc(100vw - 300px);
}
.sidebar-container {
    width: 300px;
}
</style>
