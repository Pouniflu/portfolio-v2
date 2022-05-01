<template>
    <article class="project">
        <div></div>
        <div>
            <div>
                <img :src="require(`~/assets/img/projects/${project.image}`)" alt="site ukraine">
                <div class="project-img-filter"></div>
                <div class="project-img-logo">
                    <img :src="require(`~/assets/img/projects/${project.logo}`)" alt="">
                </div>
                <div class="project-category">
                    <p>{{ project.category }}</p>
                </div>
            </div>
            <div class="information">
                <div>
                    <div class="information-title">
                        <h3>{{ project.title }}</h3>
                        <div class="information-links">
                            <a href=""><img src="../assets/img/instagram.png" alt=""></a>
                            <a href=""><img src="../assets/img/website.png" alt=""></a>
                        </div>
                    </div>
                    <p>{{ project.short_description }}</p>
                </div>
                <a :href="'/' + project.slug">En savoir plus</a>
            </div>
        </div>
    </article>
</template>

<script>
export default {
  name: 'project',
  props: [
      'project'
  ]
}
</script>

<style lang="scss">
@import '~assets/scss/abstracts/mixins';
@import '~assets/scss/abstracts/variables';
@import '~assets/scss/base/typography';

.project {
    width: 100%;
    display: flex;
    box-shadow: 0px 4px 4px rgba(155, 155, 155, 0.25);
    border-radius: 10px;
    margin-bottom: 50px;

    @include device-large {
        & > div:first-child {
            width: 20px;
            background-color: $color-4;
            border-top-left-radius: 10px;
            border-bottom-left-radius: 10px;
        }

        & > div:nth-of-type(2) {
            display: flex;
            width: 100%;
        }

        & > div:nth-of-type(2) > div:first-child{
            width: 320px;
            height: 100px;
            position: relative;
            display: flex;
            
            & > img {
                width: 320px;
                height: 100px;
                object-fit: cover;
            }

            .project-img-filter {
                position: absolute;
                top: 0;
                width: 320px;
                height: 100px;
                background: linear-gradient(0deg, rgba(30, 30, 30, 0.1), rgba(30, 30, 30, 0.1));
            }

            .project-img-logo {
                position: absolute;
                width: 70px;
                height: 70px;
                background-color: white;
                top: 15%;
                right: 10%;
                border-radius: 6px;
                box-shadow: 0px 4px 4px rgba(177, 177, 177, 0.25);
                display: flex;
                align-items: center;
                justify-content: center;

                img {
                    width: 60px;
                }
            }

            .project-category {
                position: absolute;
                background-color: $color-4;
                padding: 5px 9px;
                border-radius: 6px;
                top: 6%;
                left: 4%;

                p {
                    font-size: 10px;
                    font-weight: $medium;
                    font-style: italic;
                }
            }
        }

        .information {
            width: 100%;
            display: flex;
            align-items: center;
            justify-content: space-between;

            &-title {
                display: flex;
                margin-bottom: 6px;
            }

            &-links {
                display: flex;
                margin-left: 20px;

                img {
                    width: 20px;
                    height: 20px;
                }

                a:not(:first-of-type) {
                    margin-left: 12px;
                }
            }

            & > div {
                margin-left: 4%;
                width: 100%;
            }

            p {
                font-size: 12px;
                font-weight: $regular;
            }

            & > a {
                width: 26%;
                text-align: center;
                text-decoration: none;
                font-size: 12px;
                font-weight: $semibold;
                margin-right: 16px;
                color: $color-4;
            }
        }
    }

    @include device-medium {
        width: 44%;
        display: flex;
        box-shadow: 0px 4px 4px rgba(155, 155, 155, 0.25);
        border-radius: 10px;
        margin-bottom: 50px;

        & > div:first-child {
            width: 32px;
            background-color: $color-4;
            border-top-left-radius: 10px;
            border-bottom-left-radius: 10px;
        }

        & > div:nth-of-type(2) > div:first-child{
            width: 100%;
            height: 100px;
            position: relative;
            display: flex;
            border-top-right-radius: 10px;
            
            & > img {
                width: 100%;
                height: 100px;
                object-fit: cover;
                border-top-right-radius: 10px;
            }

            .project-img-filter {
                position: absolute;
                top: 0;
                width: 100%;
                height: 100px;
                background: linear-gradient(0deg, rgba(30, 30, 30, 0.1), rgba(30, 30, 30, 0.1));
                border-top-right-radius: 10px;
            }

            .project-img-logo {
                position: absolute;
                width: 70px;
                height: 70px;
                background-color: white;
                top: 60%;
                left: 10%;
                border-radius: 6px;
                box-shadow: 0px 4px 4px rgba(177, 177, 177, 0.25);
                display: flex;
                align-items: center;
                justify-content: center;

                img {
                    width: 60px;
                }
            }

            .project-category {
                position: absolute;
                background-color: $color-4;
                padding: 5px 9px;
                border-radius: 6px;
                top: 6%;
                right: 4%;

                p {
                    font-size: 10px;
                    font-weight: $medium;
                    font-style: italic;
                }
            }
        }

        .information {
            width: 100%;
            padding: 8px 36px 30px;

            &-title {
                display: flex;
                margin-bottom: 20px;
                margin-left: 85px;
            }

            &-links {
                display: flex;
                margin-left: 12px;

                img {
                    width: 15px;
                    height: 15px;
                }

                a:not(:first-of-type) {
                    margin-left: 10px;
                }
            }

            p {
                font-size: 12px;
                font-weight: $regular;
                margin-bottom: 8px;
            }

            & > a {
                width: 26%;
                text-align: center;
                text-decoration: none;
                font-size: 12px;
                font-weight: $semibold;
                color: $color-4;
            }
        }
    }

    @include device-small {
        & > div:first-child {
            width: 32px;
            background-color: $color-4;
            border-top-left-radius: 10px;
            border-bottom-left-radius: 10px;
        }

        & > div:nth-of-type(2) > div:first-child{
            width: 100%;
            height: 100px;
            position: relative;
            display: flex;
            border-top-right-radius: 10px;
            
            & > img {
                width: 100%;
                height: 100px;
                object-fit: cover;
                border-top-right-radius: 10px;
            }

            .project-img-filter {
                position: absolute;
                top: 0;
                width: 100%;
                height: 100px;
                background: linear-gradient(0deg, rgba(30, 30, 30, 0.1), rgba(30, 30, 30, 0.1));
                border-top-right-radius: 10px;
            }

            .project-img-logo {
                position: absolute;
                width: 70px;
                height: 70px;
                background-color: white;
                top: 60%;
                left: 10%;
                border-radius: 6px;
                box-shadow: 0px 4px 4px rgba(177, 177, 177, 0.25);
                display: flex;
                align-items: center;
                justify-content: center;

                img {
                    width: 60px;
                }
            }

            .project-category {
                position: absolute;
                background-color: $color-4;
                padding: 5px 9px;
                border-radius: 6px;
                top: 6%;
                right: 4%;

                p {
                    font-size: 10px;
                    font-weight: $medium;
                    font-style: italic;
                }
            }
        }

        .information {
            width: 100%;
            padding: 8px 36px 30px;

            &-title {
                display: flex;
                margin-bottom: 20px;
                margin-left: 85px;
            }

            &-links {
                display: flex;
                margin-left: 12px;

                img {
                    width: 15px;
                    height: 15px;
                }

                a:not(:first-of-type) {
                    margin-left: 10px;
                }
            }

            p {
                font-size: 12px;
                font-weight: $regular;
                margin-bottom: 8px;
            }

            & > a {
                width: 26%;
                text-align: center;
                text-decoration: none;
                font-size: 12px;
                font-weight: $semibold;
                color: $color-4;
            }
        }
    }

    @media screen and (max-width: 376px) {
        .information-links {
            display: none;
        }
    }
}
</style>