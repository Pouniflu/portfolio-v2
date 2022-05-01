<template>
  <div class="wrapper">
    <banner-home />
    <div id="body">
      <presentation />
      <list-of-projects />
      <div class="projets">
        <project v-for="project in projects" :key="project.slug" :project="project" />
      </div>
    </div>
    <contact />
    <footer>
      <p>
        © Copyright Claire Brisbart 2022 - Tous droits réservés | <a href="#">Mentions légales</a>
      </p>
    </footer>
  </div>
</template>

<script>
import projects from '~/content/data'
import BannerHome from '~/components/BannerHome.vue'
import Contact from '~/components/Contact.vue'
import ListOfProjects from '~/components/ListOfProjects.vue'
import Presentation from '~/components/Presentation.vue'
import Project from '~/components/Project.vue'

export default {
  name: 'IndexPage',
  components: { 
    Project, 
    BannerHome, 
    Presentation, 
    ListOfProjects, 
    Contact 
  },
  data() {
    return {
      projects: projects
    }
  }
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

  @include device-medium {
    margin: 0 6vw;
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

.projets {
  @include device-medium {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
  }
}

footer {
  background: #252525;
  color: white;
  height: 80px;
  font-weight: $light;
  font-size: 12px;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;

  @include device-small {
    padding: 0 20px;
  }

  a {
    text-decoration: none;
    color: white;
  }
}

</style>