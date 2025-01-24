<template>
  <section class="how-works">
    <div class="how-works__container">
      <div class="section-content content">
        <h2 class="content__title title">How <span>FarmVest</span> Works</h2>
        <p class="content__paragraph paragraph">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut eu, mollis
          aenean sit dictum tincidunt. Ut arcu, suscipit ac etLorem ipsum dolor
          sit amet.Lorem ipsum dolor sit amet, consectetur
        </p>
        <div class="content__steps steps">
          <ul class="steps__list">
            <li v-for="(step, index) in steps" :key="index" class="steps__item">
              <span class="steps__icon" v-html="step.icon"></span>
              <div>
                <h3 class="steps__subtitle">{{ step.title }}</h3>
                <p class="steps__description">{{ step.description }}</p>
              </div>
            </li>
          </ul>
        </div>
      </div>
      <div class="section-image">
        <img
          src="../assets/images/how-works-image.png"
          alt="man looks at his mobile"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";

const steps = ref([
  {
    icon: `<svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 32 32"><path fill="currentColor" d="m28 25l-1.414-1.414L24 26.172V18h-2v8.172l-2.586-2.586L18 25l5 5z"/><path fill="currentColor" d="M10 28V10h12v5h2V6a2 2 0 0 0-2-2H10a2 2 0 0 0-2 2v22a2 2 0 0 0 2 2h6v-2Zm0-22h12v2H10Z"/></svg>`,
    title: "Download FarmVest",
    description: "Start by downloading FarmVest app on your Android or iOS.",
  },
  {
    icon: `<svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" viewBox="0 0 28 28"><path fill="currentColor" d="M21 16c1.306 0 2.418.835 2.83 2H14v-.5H7a1.5 1.5 0 0 0-1.493 1.355L5.5 19v.715c0 2.674 3.389 4.785 8.5 4.785V24h7.471c-1.79 1.243-4.41 2-7.471 2c-5.79 0-10-2.567-10-6.285V19a3 3 0 0 1 3-3zm3 3v.715q0 .4-.07.785H14V19zm-.371 2.5H14V23h8.634c.427-.461.763-.964.995-1.5M19.954 7.25a6 6 0 0 1 0 1.5H14v-1.5zm-.213-1a6 6 0 0 0-.697-1.5H14v1.5zM14 2c1.653 0 3.15.669 4.235 1.75H14V3.5a4.5 4.5 0 1 0 0 9v-.25h4.235A6 6 0 1 1 14 2m5.044 9.25H14v-1.5h5.74a6 6 0 0 1-.696 1.5"/></svg>`,
    title: "Create account",
    description: "Start by downloading FarmVest app on your Android or iOS.",
  },
  {
    icon: `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path fill="currentColor" d="M5 17v-7h2v7zm6 0v-7h2v7zm-9 4v-2h20v2zm15-4v-7h2v7zM2 8V6l10-5l10 5v2zm4.45-2h11.1zm0 0h11.1L12 3.25z"/></svg>`,
    title: "Link your bank account",
    description: "Start by downloading FarmVest app on your Android or iOS.",
  },
  {
    icon: `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20"><g fill="currentColor" fill-rule="evenodd" clip-rule="evenodd"><path d="M7.097 5.3c-.646.484-1 1.115-1 1.77c0 .656.354 1.287 1 1.772s1.562.8 2.595.8a.5.5 0 0 1 0 1c-1.228 0-2.36-.373-3.195-1c-.836-.627-1.4-1.53-1.4-2.571c0-1.04.564-1.945 1.4-2.572c.836-.626 1.967-.999 3.195-.999c1.918 0 3.647.919 4.314 2.334a.5.5 0 0 1-.905.426c-.457-.97-1.761-1.76-3.409-1.76c-1.033 0-1.949.315-2.595.8"/><path d="M11.957 14.983c.646-.484.999-1.116.999-1.77c0-.656-.353-1.287-1-1.772c-.646-.485-1.562-.8-2.594-.8a.5.5 0 1 1 0-1c1.228 0 2.36.373 3.195 1s1.399 1.53 1.399 2.571c0 1.04-.564 1.945-1.4 2.571c-.835.627-1.966 1-3.194 1c-1.918 0-3.647-.919-4.314-2.334a.5.5 0 0 1 .905-.426c.457.97 1.76 1.76 3.409 1.76c1.032 0 1.948-.315 2.595-.8M9 1a.5.5 0 0 1 .5.5v2a.5.5 0 0 1-1 0v-2A.5.5 0 0 1 9 1"/><path d="M9 16a.5.5 0 0 1 .5.5v2a.5.5 0 0 1-1 0v-2A.5.5 0 0 1 9 16"/></g></svg>`,
    title: "Start Investing",
    description: "Start by downloading FarmVest app on your Android or iOS.",
  },
]);
</script>

<style lang="scss" scoped>
@use "../assets/styles/common-styles/container.scss" as *;
@use "../assets/styles/common-styles/common.scss" as *;

.how-works {
  // .how-works__container

  &__container {
    display: flex;
    flex-direction: row;
    gap: 4rem;
    padding-top: 4rem;
    padding-bottom: 4rem;
    margin-bottom: 20px;
    @media screen and (max-width: $tablet) {
      gap: 2rem;
      padding: 1rem 0;
    }
    @media screen and (max-width: $mobile) {
      flex-direction: column;
      gap: 1rem;
      padding-left: 0;
      padding-right: 0;
    }
  }
}
.section-content {
}
.content {
  flex: 1 1 50%;
  padding: 0 2rem;
  @media screen and (max-width: $mobile) {
    padding: 0 1rem;
  }
  // .content__title

  &__title {
    font-size: 64px;
    @media screen and (max-width: $tablet) {
      font-size: 50px;
    }
    @media screen and (max-width: $mobile) {
      padding-bottom: 10px;
    }
  }

  // .content__paragraph

  &__paragraph {
    padding-bottom: 2rem;
  }

  // .content__steps

  &__steps {
  }
}

.steps {
  // .steps__list

  &__list {
    display: flex;
    flex-direction: column;
    align-items: start;
    gap: 2rem;
  }

  // .steps__item

  &__item {
    display: flex;
    align-items: flex-start;
    gap: 2rem;
  }

  // .steps__icon

  &__icon {
    background-color: rgba($secondaryColor, 0.1);
    border-radius: 50%;
    width: 100px;
    aspect-ratio: 1/1;
    text-align: center;
    align-content: center;
    @media screen and (max-width: $mobile) {
      width: 70px;
    }
  }

  // .steps__subtitle

  &__subtitle {
    font-size: 20px;
    font-weight: 700;
    padding-bottom: 0.5rem;
  }

  // .steps__description

  &__description {
    line-height: 180%;
    padding-right: 100px;
    @media screen and (max-width: $tablet) {
      padding-right: 0;
    }
  }
}

.section-image {
  flex: 1 1 50%;
  background: url("../assets/images/background-img/Ellipse-right.svg") no-repeat,
    url("../assets/images/background-img/Ellipse-right.svg") no-repeat;
  background-position: 100% -20%, 100% -60%;
  background-color: rgba($secondaryColor, 0.07);
  display: flex;
  justify-content: center;
  align-items: center;

  @media screen and (max-width: $mobile) {
    background: none;
  }
  img {
    max-width: 90%;
    max-height: 600px;
    object-fit: cover;
    border-radius: 20px;
    @media screen and (max-width: $mobile) {
      height: 100%;
      max-width: 100%;
      border-radius: 0;
    }
  }
}
</style>
