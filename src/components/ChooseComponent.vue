<template>
  <section class="choose">
    <div class="choose__container">
      <div class="section-content content">
        <h2 class="content__title title">Why choose <span>FarmVest</span></h2>
        <p class="content__paragraph paragraph">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut eu, mollis
          aenean sit dictum tincidunt. Ut arcu, suscipit ac
        </p>
        <div class="content__steps steps">
          <ul class="steps__list">
            <li
              v-for="(advantage, index) in advantages"
              :key="index"
              class="steps__item"
            >
              <span class="steps__icon" v-html="advantage.icon"></span>
              <div>
                <h3 class="steps__subtitle">{{ advantage.title }}</h3>
              </div>
            </li>
          </ul>
        </div>

        <button class="button button--green" @click="goToAbout">
          Learn More
        </button>
      </div>
      <div class="section-image">
        <img
          src="../assets/images/choose-image.png"
          alt="man looks at his mobile"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
import { useRouter } from "vue-router";
const router = useRouter();
function goToAbout() {
  router.push({ name: "about" }); // Replace 'about' with the route name or path
}
const advantages = ref([
  {
    icon: "1",
    title: "Real-time Checkup",
  },
  {
    icon: "2",
    title: "Flexibility in Investment",
  },
  {
    icon: "3",
    title: "Encrypted and Secured",
  },
  {
    icon: "4",
    title: "Withdraw Anytime",
  },
]);
</script>

<style lang="scss" scoped>
@use "../assets/styles/common-styles/container.scss" as *;
@use "../assets/styles/common-styles/common.scss" as *;
.choose {
  // .choose__container

  &__container {
    display: flex;
    flex-direction: row;
    gap: 2rem;
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
  padding: 0 1rem;
  // .content__title

  &__title {
    padding-bottom: 10px;
  }

  // .content__paragraph

  &__paragraph {
    padding-bottom: 2rem;
    @media screen and (max-width: $tablet) {
      padding-bottom: 1rem;
    }
  }

  // .content__steps

  &__steps {
  }
}
.title {
}
.paragraph {
}
.steps {
  // .steps__list

  &__list {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: start;
    gap: 2rem;
    padding-bottom: 2rem;
    @media screen and (max-width: $tablet) {
      gap: 1rem;
      padding-bottom: 1rem;
    }
  }

  // .steps__item

  &__item {
    display: flex;
    flex-direction: row;

    align-items: center;
    gap: 2rem;
  }

  // .steps__icon

  &__icon {
    background-color: rgba($secondaryColor, 0.1);
    border-radius: 50%;
    width: 64px;
    aspect-ratio: 1/1;
    text-align: center;
    align-content: center;
    font-size: 36px;
    font-weight: 700;
    @media screen and (max-width: $tablet) {
      width: 50px;
      font-size: 24px;
    }
  }

  // .steps__subtitle

  &__subtitle {
    font-size: 20px;
    font-weight: 500;
    padding-bottom: 0.5rem;
    text-align: center;

    align-content: center;
  }
}
.section-image {
  flex: 1 1 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  img {
    border-radius: 20px;
    max-width: 100%;

    @media screen and (max-width: $mobile) {
      border-radius: 0;
    }
  }
}
</style>
