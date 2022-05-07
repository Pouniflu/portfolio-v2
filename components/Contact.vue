<template>
    <div class="contact">
        <svg class="contact-polygon" fill="currentColor" viewBox="0 0 100 100" preserveAspectRatio="none" aria-hidden="true">
            <polygon points="0,0 100,0 0,60 0,0" />
        </svg>
        <div class="contact-container">
            <p>Portfolio</p>
            <div class="contact-container-title">
                <h2>Me contacter</h2>
                <a href="https://www.linkedin.com/in/claire-brisbart/" target="_blank">
                    <img src="../assets/img/linkedin.png" alt="">
                </a>
                <a href="mailto:claire.brisbart@gmail.com">
                    <img src="../assets/img/email.png" alt="">
                </a>
            </div>
        </div>
        <footer>
        <p>
            © Copyright Claire Brisbart 2022 - Tous droits réservés | <a href="#">Mentions légales</a>
        </p>
        </footer>
    </div>
</template>

<script>
export default {
    name: 'contact',
}
</script>

<style lang="scss">
@import '~assets/scss/abstracts/mixins';
@import '~assets/scss/abstracts/variables';
@import '~assets/scss/base/typography';

.contact {
    position: relative;
    margin-top: 180px;

    @include device-medium {
        margin-top: 100px;
    }
}

.contact-polygon {
    color: white;
    display: block;
    position: absolute;
    right: 0;
    top: -0.2%;
    bottom: 0;
    height: 70vh;
    width: 100%;
    z-index: 2;
}

.contact-container {
    width: 100%;
    height: 80vh;
    background: linear-gradient(0deg, rgba(30, 30, 30, 0.35), rgba(30, 30, 30, 0.35)), url("~/assets/img/contact.jpg");
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    position: relative;
    display: flex;
    flex-direction: center;
    align-items: flex-end;
    justify-content: center; 

    & > p {
        position: absolute;
        width: 100%;
        font-weight: $bold;
        font-size: 100px;
        text-transform: uppercase;
        color: rgba(255, 255, 255, 0.15);
        text-align: center;
        letter-spacing: 0.08em;

        @media screen and (min-width: 1540px) {
            top: 37vh;
            font-size: 140px;
        }

        @media screen and (min-width: 768px) and (max-width: 1539px) {
            top: 29vh;
            font-size: 100px;
        }

        @include device-small {
            top: 40vh;
            font-size: 54px;
        }
    }

    &-title {
        text-align: center;
        padding-bottom: 8%;
        z-index: 10;

        @include device-small {
            padding-bottom: 36%;
        }

        h2 {
            font-size: 46px;
            font-weight: $bold;
            color: white;

            @media screen and (min-width: 1540px) {
                font-size: 64px;
            }

            @include device-small {
                font-size: 40px;
            }
        }

        img {
            width: 60px;
            margin: 0 14px;
        }
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