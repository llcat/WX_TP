<template>
    <div class="project-intro">
        <h3 class="project-name"><a :href="projectInfo.link" target="_blank">{{projectInfo.name}}</a><img src="../assets/link.png"></h3>
        <p class="project-info">{{projectInfo.info}}</p>
        <p>powered by:</p>
        <div class="skill-box">
            <skill-item
                    v-for="skill in projectInfo.skillList"
                    :key="skill.skillName"
                    :imgSrc="skill.imgSrc"
                    :skillName="skill.skillName">
            </skill-item>
        </div>
    </div>
</template>

<script>
    import SkillItem from './SkillItem';

    export default {
        name: "ProjectIntro",
        components: {SkillItem},
        component: {
          SkillItem
        },
        props: {
            projectInfo: Object
        }
    }

</script>

<style scoped lang="scss">
    .project-intro {
        background: aliceblue;
        display: inline-flex;
        flex-direction: column;
        border: 1px dashed gray;
        padding: 1vmin;

        p {
            color: gray;
            font-size: 20px;
            margin: 1vmin 1vmin;
        }

        .project-name {
            margin: 1vmin 0 1vmin 1vmin;
            display: flex;
            align-items: center;
            a {
                color: black;
            }
            img {
                width: 20px;
            }
        }

        .project-info {
            color: #4a4a4a;
        }

        .skill-box {
            display: flex;
            flex-wrap: wrap;
        }

        @media screen and (min-width: 320px) and (max-aspect-ratio: 1/1){
            & {
                max-width: 75vw;
            }
        }

        @media screen and (min-width: 768px) and (min-aspect-ratio: 1/1) {
            & {
                max-width: 40vw;
            }
        }
    }
</style>