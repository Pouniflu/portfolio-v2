<template>
    <div v-if="project.medias" class="media-project">
        <h2>Médias</h2>
        <p>Découvre ici tous les médias en lien avec le projet !</p>
        <div class="media-project-gallery">
            <img v-for="n in project.medias.length" :key="n" :src="require(`~/assets/img/projects/medias/${project.medias[n-1]}`)" alt="">
        </div>
    </div>
</template>

<script>
export default {
    name: 'media-project',
    props: [
      'project'
    ]
}
</script>

<style lang="scss">
@import '~assets/scss/abstracts/mixins';

.media-project {
    margin-top: 100px;

    &-gallery {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-around;

        img {
            width: auto;
            height: 300px;
            margin-top: 26px;

            @include device-small {
                max-width: 100%;
                height: auto;
            }
        }
    }
}
</style>