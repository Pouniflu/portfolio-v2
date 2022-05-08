<template>
    <div class="project-page-competences">
        <img src="../assets/img/competences.webp" alt="">
        <div>
            <h2>Compétences développées</h2>
            <ul>
                <li v-for="n in project.competences.length" :key="n">{{ project.competences[n-1] }}</li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: 'competences-project',
    props: [
      'project'
    ]
}
</script>

<style lang="scss">
@import '~assets/scss/abstracts/mixins';

.project-page-competences {
    display: flex;

    li {
        margin-left: 40px;
    }

    @media screen and (min-width: 1540px) {
        justify-content: space-around;
    }

    @media screen and (min-width: 1025px) and (max-width: 1539px) {
        justify-content: space-between;
    }

    @include device-medium {
        justify-content: space-between;

        img {
            width: 36%;
        }
    }

    @include device-small {
        flex-direction: column;

        img {
            width: 80%;
            margin: 0 auto 40px;
        }
    }
}
</style>