<template>
    <div class="list-projects">
        <h2>Projets</h2>
        <p>Professionnels, personnels, étudiants, associatifs...</p>
        <div class="list-projects-filter">
            <button id="alternance-stage">Alternance / Stage</button>
            <button id="projets-etu">Projets étudiants</button>
            <button id="projets-perso">Projets personnels</button>
            <button id="projets-asso">Projets associatifs</button>
            <button id="autre">Autre</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'list-of-projects',
}
</script>

<style lang="scss">
@import '~assets/scss/abstracts/variables';
@import '~assets/scss/abstracts/mixins';
@import '~assets/scss/base/typography';

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
                margin-top: 22px;
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
</style>