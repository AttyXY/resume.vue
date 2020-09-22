<template>
    <div class="experience-container">
        <h1 class="subheader">EXPERIENCE</h1>
        <div class="experience">
            <div class="column" v-for="(experience, i) in data" :key="i">
                <div class="role">
                    <div class="company">
                        <h2 class="title">{{ experience.role.title }}</h2>
                        <h2 class="company">{{ experience.role.company }}</h2>
                    </div>
                    <div class="metadata">
                        <h2 class="date">{{ experience.role.date }}</h2>
                        <h2 class="location">{{ experience.role.location }}</h2>
                    </div>
                </div>
                <ul class="bullets">
                    <li
                        v-for="(bullet, j) in experience.bullets"
                        :key="j"
                        v-html="bullet"
                    >
                        {{ bullet }}
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "experience",
    props: {
        data: { type: Array, default: () => [] },
    },
    components: {},
};
</script>

<style lang="scss">
@import "../mixins.scss";

.experience-container {
    padding: 30px;
    background-color: white;
    h1 {
        font-weight: normal;
        font-size: $subheader-font-size;
        color: $highlight;
    }
    div {
        font-size: $content-font-size;
        h2 {
            .title .date {
                font-weight: normal;
            }
        }
    }
}

.role {
    display: flex;
    /* flex-direction: row; */
    justify-content: space-between;

    .company {
        display: flex;
        flex-direction: column;
    }
    .metadata {
        display: flex;
        flex-direction: column;
    }
}
</style>
