<template>
  <div class="wrapper">
    <banner-home />
    <div id="body">
      <presentation />
      <list-of-projects />
      <project />
      <project />
      <project />
      <project />
    </div>
  </div>
</template>

<script>
import BannerHome from '~/components/BannerHome.vue'
import ListOfProjects from '~/components/ListOfProjects.vue'
import Presentation from '~/components/Presentation.vue'
import Project from '~/components/Project.vue'

export default {
  name: 'IndexPage',
  components: { Project, BannerHome, Presentation, ListOfProjects },
}
</script>

<style lang="scss">
@import '~assets/scss/abstracts/mixins';
@import '~assets/scss/base/reset';
@import '~assets/scss/base/typography';

#body {
  scroll-behavior: smooth;

  @include device-small {
    margin: 0 20px;
  }

  @include device-large {
    margin: 0 16vw;
  }
}

h2 {
  letter-spacing: 0.04em;
  text-transform: uppercase;
  margin-bottom: 16px;
}

h3 {
  font-size: 16px;
  font-weight: $bold;
}

.wrapper {
  height: 100vh;
  overflow-y: auto;
  overflow-x: hidden;
  perspective: 10px;
}

</style>