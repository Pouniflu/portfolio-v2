<template>
    <div class="wrapper">
        <banner-project />
        <div id="body">

        </div>
    </div>
</template>

<script>
import BannerProject from '~/components/BannerProject.vue'

export default {
    name: 'projet-page',
    components: { BannerProject, }
}
</script>

<style lang="scss">
@import '~assets/scss/base/reset';

.wrapper {
  height: 100vh;
  overflow-y: auto;
  overflow-x: hidden;
  perspective: 10px;
}
</style>