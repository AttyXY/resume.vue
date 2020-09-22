<template>
    <div class="sidebar-container">
        <div class="skills-container">
            <h1 class="subheader">SKILLS</h1>
            <div class="column">
                <h2>Languages</h2>
                <p v-for="lang in languages" :key="lang">
                    {{ lang }}
                </p>
            </div>
            <div class="column">
                <h2>Libraries</h2>
                <p v-for="lib in libraries" :key="lib">
                    {{ lib }}
                </p>
            </div>
            <div class="column">
                <h2>Technologies</h2>
                <p v-for="tech in technologies" :key="tech">
                    {{ tech }}
                </p>
            </div>
        </div>
        <!-- <div class="projects-container">
            <h1 class="subheader">PROJECTS</h1>
            <div class="projects">
                <p v-for="proj in projects" :key="proj">
                    {{ proj.name }}
                </p>
            </div>
        </div> -->
        <div class="education-container">
            <h1 class="subheader">EDUCATION</h1>
            <div class="education">
                <div class="main">
                    <h2>{{ education.degree }}</h2>
                    <h2>{{ education.year }}</h2>
                    <h2>{{ education.institution }}</h2>
                    <p>{{ education.minor }}</p>
                </div>
            </div>
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
        languages: function() {
            return this.data.skills.languages;
        },
        libraries: function() {
            return this.data.skills.libraries;
        },
        technologies: function() {
            return this.data.skills.technologies;
        },
        // projects: function() {
        //     return this.data.projects;
        // },
        education: function() {
            return this.data.education;
        },
    },
};
</script>

<style lang="scss">
@import "../mixins.scss";

.sidebar-container {
    background-color: rgb(246, 246, 246);
    padding: $border-padding;
    h1 {
        font-size: $subheader-font-size;
        font-weight: normal;
        color: $highlight;
    }
    h2 {
        font-size: $content-font-size;
    }
    p {
        display: flex;
        flex-direction: column;
        font-size: $content-font-size;
    }
    /* .skills-container {
        h2 {
        }
        p {
            font-size: $content-font-size;
        }
    }
    .projects-container {
        p {
            font-size: $content-font-size;
        }
    } */
}
</style>
