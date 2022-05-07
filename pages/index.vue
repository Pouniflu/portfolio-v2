<template>
  <div class="wrapper">
    <banner-home />
    <div id="body">
      <presentation />
      <div class="list-projects">
        <h2>Projets</h2>
        <p>Professionnels, personnels, étudiants, associatifs...</p>
        <div class="list-projects-filter">
            <button @click="filterCategory('all')" :class="{ activeAll: dataCategory== 'all'}" id="all-projects">Tous</button>
            <button @click="filterCategory('Alternance/Stage')" :class="{ activeAltSta: dataCategory== 'Alternance/Stage'}" id="alternance-stage">Alternance / Stage</button>
            <button @click="filterCategory('Projet étudiant')" :class="{ activeProEtu: dataCategory== 'Projet étudiant'}" id="projets-etu">Projets étudiants</button>
            <button @click="filterCategory('Projet personnel')" :class="{ activeProPer: dataCategory== 'Projet personnel'}" id="projets-perso">Projets personnels</button>
            <button @click="filterCategory('Projet associatif')" :class="{ activeProAss: dataCategory== 'Projet associatif'}" id="projets-asso">Projets associatifs</button>
            <button @click="filterCategory('Autre')" :class="{ activeAutre: dataCategory== 'Autre'}" id="autre">Autre</button>
        </div>
      </div>
      <div v-for="project in projects" :key="project.slug" class="projets">
        <project v-if="dataCategory == 'all' || dataCategory == project.category" :project="project" />
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
import Presentation from '~/components/Presentation.vue'
import Project from '~/components/Project.vue'

export default {
  name: 'IndexPage',
  components: { 
    Project, 
    BannerHome, 
    Presentation, 
    Contact 
  },
  data() {
    return {
      projects: projects,
      dataCategory: 'all'
    }
  },
  methods: {
    filterCategory(category) {
      this.dataCategory = category
    }
  }
}
</script>

<style lang="scss">
@import '~assets/scss/abstracts/mixins';
@import '~assets/scss/abstracts/variables';
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

.activeAll {
  background-color: #252525 !important;
  color: white;
}

.activeAltSta {
  background-color: $color-1 !important;
  color: white;
}

.activeProEtu {
  background-color: $color-2 !important;
  color: white;
}

.activeProPer {
  background-color: $color-3 !important;
  color: white;
}

.activeProAss {
  background-color: $color-4 !important;
  color: white;
}

.activeAutre {
  background-color: $color-5 !important;
  color: white;
}

.list-projects {   
    h2 {
        position: relative;
        margin-bottom: 16px;

        // &::before {
        //     position: absolute;
        //     content: "Projet";
        //     text-transform: uppercase;
        //     font-weight: $bold;
        //     color: rgba(32, 32, 32, 0.04);
        //     font-size: 32px;
        //     transform: rotate(-90deg);
        //     top: 2vw;

        //     @media screen and (min-width: 1540px) {
        //         left: -9vw;
        //     }

        //     @media screen and (min-width: 1024px) and (max-width: 1539px) {
        //         left: -11vw;
        //     }

        //     @include device-small {
        //         display: none;
        //     }

        //     @include device-medium {
        //         display: none;
        //     }
        // }

    }

    &-filter {
        display: flex;
        flex-wrap: wrap;
        margin-top: 26px;
        margin-bottom: 60px;

        @include device-small {
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        button {
            cursor: pointer;
            padding: 3px 18px;
            margin: 14px 30px 0 0;
            background: none;
            border-radius: 6px;
            font-size: 14px;
            font-weight: $semibold;

            @include device-small {
                margin: 22px 0 0 0;
            }
        }

        #all-projects {
          border: 3px solid #252525;

            &:hover {
                background: #252525;
                color: white;
                transition: 0.2s;
            }
        }

        #alternance-stage {
            border: 3px solid $color-1;

            &:hover {
                background: $color-1;
                color: white;
                transition: 0.2s;
            }
        }

        #projets-etu {
            border: 3px solid $color-2;

            &:hover {
                background: $color-2;
                color: white;
                transition: 0.2s;
            }
        }

        #projets-perso {
            border: 3px solid $color-3;

            &:hover {
                background: $color-3;
                color: white;
                transition: 0.2s;
            }
        }

        #projets-asso {
            border: 3px solid $color-4;

            &:hover {
                background: $color-4;
                color: white;
                transition: 0.2s;
            }
        }

        #autre {
            border: 3px solid $color-5;

            &:hover {
                background: $color-5;
                color: white;
                transition: 0.2s;
            }
        }
    }
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