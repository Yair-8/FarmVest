<template>
  <section class="hero__container hero">
    <h1 class="hero__title title">
      The easiest and fastest way to <span>Invest</span> in Agriculture
    </h1>
    <p class="hero__paragraph paragraph">
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut eu, mollis
      aenean sit dictum tincidunt. Ut arcu, suscipit ac etLorem ipsum dolor sit
      amet.Lorem ipsum dolor sit amet, consectetur
    </p>
    <div class="hero__form">
      <input
        class="input"
        type="email"
        name="email"
        id="email"
        placeholder="Enter your email"
      />
      <button class="button button--green">Get started</button>
    </div>
    <div class="hero__logos">
      <img src="../assets/images/MarketWatch Logo.svg" alt="MarketWatch Logo" />
      <img src="../assets/images/Forbes.com Logo.svg" alt="Forbes.com Logo" />
      <img
        src="../assets/images/Business Insider Logo.svg"
        alt="Business Insider Logo"
      />
      <img
        src="../assets/images/Fidelity Management and Research Company Logo.svg"
        alt="Fidelity Management and Research Company Logo"
      />
      <img src="../assets/images/WIRED UK Logo.svg" alt="WIRED UK Logo" />
    </div>
  </section>
</template>

<script setup></script>

<style lang="scss" scoped>
@use "../assets/styles/common-styles/container.scss" as *;
@use "../assets/styles/common-styles/common.scss" as *;
.hero {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 2rem;
  font-family: $fontFamily;
  width: 100%;
  height: 100svh;
  background: url("../assets/images/background-img/Star 5.svg") no-repeat,
    url("../assets/images/background-img/currency.svg") no-repeat,
    url("../assets/images/background-img/Ellipse1.svg") no-repeat,
    url("../assets/images/background-img/money-bag.svg") no-repeat,
    url("../assets/images/background-img/tabler_currency.svg") no-repeat,
    url("../assets/images/background-img/Star.svg") no-repeat;
  background-position: 5% 30%, 0% 65%, 25% 75%, 80% 15%, 99% 35%, 85% 75%;

  @media screen and (max-width: $tablet) {
    gap: 1rem;
    padding: 5rem 1rem;
  }

  @media screen and (max-width: $mobile) {
    gap: 0.8rem;
    padding: 2rem 0;
    background: none;
    height: 100%;
  }
  // .hero__container

  &__container {
  }

  // .hero__title

  &__title {
    font-size: 70px;
    text-align: center;
    padding: 6rem 0 5rem 0;
    max-width: 900px;
    @media screen and (max-width: $tablet) {
      padding: 4rem 0 3rem 0;
      font-size: 50px;
    }

    @media screen and (max-width: 670px) {
      padding: 1rem 0;
      font-size: 40px;
    }
  }

  // .hero__paragraph

  &__paragraph {
    text-align: center;
    max-width: 725px;
  }

  // .hero__form

  &__form {
    display: flex;
    flex-direction: row;
    padding: 30px;
    max-width: 900px;
    margin-bottom: 60px;
    @media screen and (max-width: 500px) {
      padding: 0;
      flex-direction: column;
      width: 100%;
    }
  }
  &__logos {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    gap: 20px;
    width: 100%;
    flex-wrap: wrap;
    padding: 10px;
    @media screen and (max-width: $tablet) {
      //
    }
    @media screen and (max-width: 702px) {
      justify-content: space-around;
    }
    @media screen and (max-width: $mobile) {
      padding: 0;
    }
    img {
      width: 150px;
    }
  }
}

.button {
  // .button--green

  &--green {
    border-radius: 0 10px 10px 0;
    @media screen and (max-width: $mobile) {
      border-radius: 10px;
    }
  }
}
</style>
