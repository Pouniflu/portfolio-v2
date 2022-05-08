<template>
    <div class="presentation">
        <img src="../assets/img/illustration-home.png" alt="">
        <div>
            <h2>Présentation</h2>
            <p>Je m’appelle Claire Brisbart et suis actuellement étudiante en 3ème année à l’IIM Digital School afin d’obtenir un diplôme « Chef de projet digital ».  Je souhaite poursuivre mes études en intégrant le mastère « Management de la transformation digitale » à l’IIM, spécialité conduite du changement et innovation. Double diplôme avec l’ESILV – Ecole Supérieure d'Ingénieurs Léonard de Vinci, il prépare les étudiants à répondre aux nouveaux besoins des entreprises en axant la formation sur un socle de compétences en gestion de produit et sur l’agilité nécessaire à mener des changements en continu. 
            <br><br>Plus personnellement, j’aime m’impliquer dans tous mes projets et je souhaite désormais saisir toutes les opportunités qui se présentent à moi. J’aime l’UX, l’UI design, l'astrologie et le monde de l’esport.</p>
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