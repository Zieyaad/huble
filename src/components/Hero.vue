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
        <a class="button primary" href=":javascript;">Request demo</a>
        <a class="button secondary" href=":javascript;">Speak to our team</a>
      </div>
    </div>
  </section>
</template>

<script></script>

<style scoped lang="scss">
  .Block {
    position: relative;
    display: flex;
    min-height: 500px;

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
  }
</style>