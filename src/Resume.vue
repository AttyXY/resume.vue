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
import Experience from "./components/Experience";
import Header from "./components/Header";
import Sidebar from "./components/Sidebar";

export default {
    name: "resume",
    data: () => ({ data: {} }),
    // Fetch JSON data upon creation.
    created: function() {
        fetch("data.json")
            .then(res => res.json())
            .then(data => (this.data = data));
    },
    computed: {
        headerData: () => this.data.header,
        experienceData: () => this.data.experience,
        sidebarData: () => this.data.sidebar,
    },
    components: {
        ResumeHeader: Header,
        Experience,
        Sidebar,
    },
};
</script>

<style lang="scss">
.resume {
    display: flex;
    flex-direction: column;

    // set to Letter paper size
    width: 8.5in;
    height: 11in;
}
.resume-header {
    display: flex;
    flex-direction: row;

    height: 12.5vh; // 1/8 height
    flex: 0 1 auto;
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

.experience {
    width: calc(100vw - 300px);
    flex: 0 1 auto;
}
.sidebar {
    width: 400px;
    flex: 0 1 auto;
}
</style>
