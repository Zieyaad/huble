<template>
  <section class="Block">
    <div class="Block-Mask">
      <img src="../assets/img/hero-bg.png" loading="eager" alt="hero-bg" width="1600"/>
    </div>
    <div class="Container">
      <div class="Block-Content">
        <p class="subtitle">Monolith</p>
        <h1>Use AI software to test less and learn more.</h1>
        <p>
          Spend less time running expensive, repetitive tests and more time learning
          from your engineering data to predict the exact tests to run.
        </p>
      </div>

      <div class="Block-Footer">
        <a class="button button-primary" href=":javascript;">Request demo</a>
        <a class="button button-secondary" href=":javascript;">Speak to our team</a>
      </div>

      <Splide :options="options" aria-label="My Favorite Images">
        <SplideSlide>
          <img src="../assets/logo/bmw-logo.webp" alt="BMW">
        </SplideSlide>
        <SplideSlide>
          <img src="../assets/logo/bae-logo.svg" alt="BAE">
        </SplideSlide>
        <SplideSlide>
          <img src="../assets/logo/mercedes-logo.webp" alt="MERCEDES">
        </SplideSlide>
        <SplideSlide>
          <img src="../assets/logo/honda-logo.svg" alt="HONDA">
        </SplideSlide>
        <SplideSlide>
          <img src="../assets/logo/siemens-logo.svg" alt="SIEMENS">
        </SplideSlide>
        <SplideSlide>
          <img src="../assets/logo/honeywell-logo.webp" alt="HONEYWELL">
        </SplideSlide>
        <SplideSlide>
          <img src="../assets/logo/kautex-logo.webp" alt="KAUTEX">
        </SplideSlide>
        <SplideSlide>
          <img src="../assets/logo/michelin-logo.webp" alt="MICHELIN">
        </SplideSlide>
        <SplideSlide>
          <img src="../assets/logo/aptar-logo.svg" alt="APTAR">
        </SplideSlide>
        <SplideSlide>
          <img src="../assets/logo/jota-logo.webp" alt="JOTA">
        </SplideSlide>
      </Splide>
    </div>
  </section>
</template>

<script>
import { Splide, SplideSlide } from '@splidejs/vue-splide';
import { defineComponent } from 'vue';
import '@splidejs/vue-splide/dist/css/splide.min.css';

export default defineComponent( {
  components: {
    Splide,
    SplideSlide,
  },

  data() {
    const options = {
      rewind    : true,
      autoplay  : true,
      interval  : 3000,
      type      : 'loop',
      perPage   : 5,
      perMove   : 1,
      gap       : '1rem',
      pagination: false,
      arrows: false,
      dots: false,
      // Client Feedback
      pauseOnHover: true,
      breakpoints: {
        480: {
          perPage: 1,
          gap       : '2rem',
        },
        600: {
          perPage: 2,
          gap       : '2rem',
        },
        900: {
          perPage: 3,
          gap       : '1rem',
        },
        1200: {
          perPage: 5,
          gap       : '1rem',
        },
      },
    };

    return { options };
  },
} );
</script>

<style scoped lang="scss">
  .Block {
    position: relative;
    min-height: 500px;
    display: flex;
    align-items: flex-end;
    padding: 80px 0;

    @include breakpoint-up(desktop) {
      min-height: 700px;
    }

    // Mask
    &-Mask {
      position: absolute;
      top: 0;
      right: 0;
      bottom: 0;
      left: 0;
      z-index: -1;
      background-color: var(--color-black);

      img {
        position: absolute;
        width: 100%;
        height: 100%;
        object-fit: cover;
        object-position: center center;
        opacity: 0.4;
      }
    }

    &-Content {
      max-width: 650px;
    }

    &-Footer {
      max-width: 550px;
      // Client Feedback
      max-width: 500px;
      padding-top: 30px;
      padding-bottom: 40px;

      @include breakpoint-up(mobile) {
        display: flex;
        justify-content: space-between;
      }

      @include breakpoint-up(big-tablet) {
        padding-top: 40px;
        padding-bottom: 80px;
      }

      a {
        margin-top: 5px;
        margin-bottom: 5px;

        + a {
          margin-left: 5px;
        }
      }
    }

    .subtitle {
      color: var(--color-red);
      font-weight: bold;
    }

    .splide__slide {
      display: flex;
      align-items: center;
      justify-content: center;

      img {
        object-fit: contain;
        width: auto;
        max-width: 100%;

        @include breakpoint-up(desktop) {
          max-width: 155px;
        }
      }
    }
  }
</style>