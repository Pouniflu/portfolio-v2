<template>
    <div class="project-page-competences">
        <img src="../assets/img/competences.webp" alt="">
        <div>
            <h2>Compétences développées</h2>
            <ul>
                <li>Liste 1</li>
                <li>Liste 2</li>
                <li>Liste 3</li>
                <li>Liste 4</li>
                <li>Liste 5</li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: 'competences-project',
}
</script>

<style lang="scss">
@import '~assets/scss/abstracts/mixins';

.project-page-competences {
    display: flex;

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

        li {
            margin-left: 20px;
        }
    }
}
</style>