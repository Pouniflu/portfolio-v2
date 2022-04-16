<template>
  <div id="body">
    <h1>hi</h1>
    <project />
    <project />
    <project />
    <project />
  </div>
</template>

<script>
import Project from '~/components/Project.vue'

export default {
  name: 'IndexPage',
  components: { Project },
}
</script>

<style lang="scss">
@import '~assets/scss/base/reset';
@import '~assets/scss/base/typography';

#body {
  margin: 0 16vw;
}

h3 {
  font-size: 16px;
  font-weight: $bold;
}

</style>