<template>
    <div class="presentation">
        <img src="../assets/img/illustration-home.png" alt="">
        <div>
            <h2>Présentation</h2>
            <p>Je m’appelle Claire Brisbart et suis actuellement étudiante en 3ème année à l’IIM Digital School afin d’obtenir un diplôme “Chef de projet digital”. 
            <br>J’aime particulièrement la gestion de projet web et l’UX/UI design.</p>
        </div>
    </div>
</template>

<script>
export default {
  name: 'presentation-home'
}
</script>

<style lang="scss">
@import '~assets/scss/abstracts/mixins';
@import '~assets/scss/base/typography';

.presentation {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-bottom: 180px;

    @include device-small {
        flex-direction: column;
        margin-bottom: 100px;
    }

    @include device-medium {
        margin-bottom: 100px;
    }

    img {
        @include device-small {
            width: 80%;
            margin-bottom: 42px;
        }
    }

    h2 {
        position: relative;
        margin-bottom: 16px;

        // &::before {
        //     position: absolute;
        //     content: "Présentation";
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

    p {
        font-weight: $regular;
    }

    div {
        margin-left: 70px;

        @include device-small {
            margin: 0 0;
        }
    }

}
</style>