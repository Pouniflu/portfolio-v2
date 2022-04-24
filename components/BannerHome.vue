<template>
    <header class="header">
        <div class="header-background">
            <img src="../assets/img/home-background.jpg" alt="">
            <div class="header-background-filter"></div>
        </div>
        <p class="background">Portfolio</p>
        <img class="middleground" src="../assets/img/claire.png" alt="">
        <div class="header-title foreground">
            <h1>Claire Brisbart</h1>
            <p>Etudiante en gestion de projet spécialisé développement web</p>
        </div>
        <a href="#">Me contacter</a>
        <svg class="polygon" fill="currentColor" viewBox="0 0 100 100" preserveAspectRatio="none" aria-hidden="true">
            <polygon points="0,0 0,60 100,100 0,100" />
        </svg>
    </header>
</template>

<script>
export default {
  name: 'banner-home'
}
</script>

<style lang="scss">
@import '~assets/scss/abstracts/mixins';
@import '~assets/scss/abstracts/variables';
@import '~assets/scss/base/typography';

.header {
    width: 100%;
    height: 70vh;
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    transform-style: preserve-3d;
    z-index: -1;

    &-background {
        width: 100%;
        height: 70vh;
        z-index: -1;

        img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        &-filter {
            width: 100%;
            height: 100%;
            background: $gradient;
            position: absolute;
            top: 0;
        }
    }

    .polygon {
        color: white;
        display: block;
        position: absolute;
        right: 0;
        top: 0;
        bottom: 0;
        height: 70vh;
        width: 100%;
        z-index: 10;
    }

    .background, .foreground {
        position: absolute;
        top: 20vh;
        width: 100%;
        height: 70vh;
        object-fit: cover;
    }

    .middleground {
        position: absolute;

        @media screen and (min-width: 1540px) {
            transform: translateY(-10px) translateZ(0px) scale(1);
        }

        @media screen and (min-width: 768px) and (max-width: 1539px) {
            transform: translateY(-10px) translateZ(0px) scale(0.6);
        }

        @include device-small {
            transform: translateY(-10px) translateZ(0px) scale(0.7);
        }

    }

    .background {
        transform: translateY(-44px) translateZ(0px) scale(1);

        @include device-small {
            transform: translateY(14px) translateZ(0px) scale(1);
        }
    }

    .foreground {
        transform: translateY(10px) translateZ(4px) scale(0.6);
    }
    
    a {
        position: absolute;
        top: 8%;
        right: 8%;
        text-decoration: none;
        color: white;
        border: 2px solid white;
        padding: 8px 26px;
        border-radius: 10px;
        z-index: 15;

        &:hover {
            background-color: white;
            color: violet;
            transition: 0.3s;
        }

        @include device-small {
            display: none;
        }
    }

    & > p {
        font-weight: $bold;
        font-size: 140px;
        text-transform: uppercase;
        color: rgba(255, 255, 255, 0.15);
        text-align: center;
        letter-spacing: 0.08em;

        @include device-small {
            font-size: 54px;
        }
    }

    h1 {
        font-size: 64px;
        font-weight: $extrabold;
        letter-spacing: 0.02em;
        text-transform: uppercase;

        @include device-small {
            font-size: 32px;
        }
    }

    &-title {
        text-align: center;
        color: white;

        p {
            @include device-small {
                padding: 0 30px;
            }
        }
    }
}
</style>