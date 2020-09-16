<template>
    <div class="sidebar-container">
        <div class="skills-container">
            <h1 class="subheader">SKILLS</h1>
            <div class="languages">
                <h2>Languages</h2>
                <p v-for="(lang, i) in languagesData" :key="i" v-html="lang">
                    {{ lang }}
                </p>
            </div>
            <div class="libraries">
                <h2>Libraries</h2>
            </div>
            <div class="technologies">
                <h2>Technologies</h2>
            </div>
        </div>
        <div class="projects-container">
            <h1 class="subheader">PROJECTS</h1>
            <div class="projects">
                <p v-for="(proj, i) in projectsData" :key="i" v-html="proj">
                    {{ proj.name }}
                </p>
            </div>
        </div>
        <div class="education-container">
            <h1 class="subheader">EDUCATION</h1>
            <div class="education"></div>
        </div>
    </div>
</template>

<script>
export default {
    name: "sidebar",
    props: {
        data: { type: Object, required: true },
    },
    components: {},
    computed: {
        languagesData: function() {
            return this.data.skills.languages;
        },
        librariesData: function() {
            return this.data.skills.libraries;
        },
        technologies: function() {
            return this.data.skills.technologies;
        },
        projectsData: function() {
            return this.data.projects;
        },
        educationData: function() {
            return this.data.education;
        },
    },
};
</script>

<style lang="scss">
@import "../mixins.scss";

.sidebar-container {
    background-color: rgb(246, 246, 246);
    padding: 30px;
    h1 {
        font-size: 14pt;
        font-weight: normal;
        color: $highlight;
    }
    .skills-container {
        h2 {
            font-size: 10pt;
        }
        p {
            font-size: 8pt;
        }
    }
    .projects {
        p {
            font-size: 8pt;
        }
    }
}
</style>
