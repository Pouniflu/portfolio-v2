<template>
    <div class="wrapper">
        <banner-project :project="project" />
        <div class="project-page" id="body">
            <div class="project-page-title">
                <h2>Description</h2>
                <span>{{ project.category }}</span>
            </div>
            <p>{{ project.details }}</p>
            <div class="project-page-button">
                <a id="instagram" href="#">
                    Instagram
                </a>
                <a id="website" href="#">
                    Site internet
                </a>
                <a id="twitter" href="#">
                    Twitter
                </a>
                <a id="linkedin" href="#">
                    LinkedIn
                </a>
                <a id="youtube" href="#">
                    YouTube
                </a>
            </div>
            <competences-project />
        </div>
    </div>
</template>

<script>
import projects from '~/content/data'
import BannerProject from '~/components/BannerProject.vue'
import CompetencesProject from '~/components/CompetencesProject.vue'

export default {
    name: 'projet-page',
    components: { 
        BannerProject, 
        CompetencesProject, 
    },
    data() {
        return {
            project: []
        }
    },
    mounted() {
        this.project = projects.find(project => project.slug === this.$route.params.slug)
        if(!this.project) {
            this.$router.push('/404')
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

.wrapper {
  height: 100vh;
  overflow-y: auto;
  overflow-x: hidden;
  perspective: 10px;
}

.project-page {
    &-title {
        display: flex;
        align-items: center;

        span {
            font-weight: $medium;
            font-size: 10px;
            font-style: italic;
            background: $color-5;
            padding: 5px 9px;
            margin: 0 0 12px 20px;
            border-radius: 6px;
        }
    }

    &-button {
        display: flex;
        flex-wrap: wrap;
        margin-bottom: 120px;

        a {
            text-decoration: none;
            font-weight: $semibold;
            font-size: 16px;
            padding: 4px 16px;
            border-radius: 10px;
            margin: 0 16px 16px;
        }

        #instagram {
            background: $instagram;
            background-clip: border-box;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;

            &:hover {
                background: $instagram;
                background-clip: initial;
                -webkit-background-clip: initial;
                -webkit-text-fill-color: initial;
                color: white;
            }
        }

        #website {
            color: $website;
            border: 2px solid $website;

            &:hover {
                background: $website;
                color: white;
            }
        }

        #twitter {
            color: $twitter;
            border: 2px solid $twitter;

            &:hover {
                background: $twitter;
                color: white;
            }
        }

        #linkedin {
            color: $linkedin;
            border: 2px solid $linkedin;

            &:hover {
                background: $linkedin;
                color: white;
            }
        }

        #youtube {
            color: $youtube;
            border: 2px solid $youtube;

            &:hover {
                background: $youtube;
                color: white;
            }
        }
    }

    p {
        margin-bottom: 28px;
        font-size: 16px;
    }
}
</style>