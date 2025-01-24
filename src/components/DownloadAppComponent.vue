<template>
  <section class="download">
    <div class="download__container">
      <h2 class="download__title title">
        Download <span> FarmVest app</span> and invest in your future
      </h2>
      <div class="download__icons">
        <button @click="goToAppStore">
          <img src="../assets/images/icons/app-store.png" alt="" />
        </button>
        <button @click="goToGoogleStore">
          <img
            src="../assets/images/icons/google-store.png"
            alt="Google Play Store"
          />
        </button>
      </div>
    </div>
  </section>
</template>

<script setup>
const goToGoogleStore = () => {
  window.open("https://play.google.com/store/apps", "_blank");
};
const goToAppStore = () => {
  window.open("https://www.apple.com/app-store/");
};
</script>

<style lang="scss" scoped>
@use "../assets/styles/common-styles/container.scss" as *;
@use "../assets/styles/common-styles/common.scss" as *;
.download {
  margin-bottom: 50px;
  // .download__container

  &__container {
    text-align: center;
    padding: 3rem 20rem;
    background: url("../assets/images/background-img/Ellipse.svg") no-repeat,
      url("../assets/images/background-img/Ellipse.svg") no-repeat;
    background-position: 50% 40%, 50% 70%;
    background-color: rgba($secondaryColor, 0.1);
    border-radius: 20px;
    @media screen and (max-width: 1200px) {
      padding: 3rem 10rem;
    }
    @media screen and (max-width: $tablet) {
      padding: 3rem 5rem;
      border-radius: 0;
    }
    @media screen and (max-width: $mobile) {
      padding: 2rem 2rem;
    }
  }

  // .download__title

  &__title {
  }

  // .download__icons

  &__icons {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    gap: 20px;

    @media screen and (max-width: 430px) {
      flex-direction: column;
    }
  }
}
.title {
  font-size: 56px;
  padding-bottom: 40px;
  @media screen and (max-width: $tablet) {
    font-size: 50px;
  }
  @media screen and (max-width: $mobile) {
    font-size: 40px;
  }
  @media screen and (max-width: 430px) {
    font-size: 34px;
    padding-bottom: 20px;
  }
}
</style>
