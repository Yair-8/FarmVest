<template>
  <section class="pathway">
    <div class="pathway__container">
      <div class="section-image">
        <img
          src="../assets/images/unsplash_oqY09oVTa3k.png"
          alt="man looks at his mobile"
        />
      </div>
      <div class="section-content content">
        <h2 class="content__title title">
          Your <span>pathway</span> to Future Investment
        </h2>
        <p class="content__paragraph paragraph">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut eu, mollis
          aenean sit dictum tincidunt. Ut arcu, suscipit ac etLorem ipsum dolor
          sit amet.Lorem ipsum dolor sit amet, consectetur
        </p>
        <div class="content__steps steps">
          <v-expansion-panels>
            <v-expansion-panel v-for="(item, index) in items" :key="index">
              <v-expansion-panel-title @click="toggleRotation">
                {{ item.title }}
                <template #actions>
                  <span class="custom-icon">
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      fill="none"
                      viewBox="0 0 24 24"
                      stroke="currentColor"
                      stroke-width="2"
                      width="16"
                      height="16"
                      :class="{ rotated: isRotated }"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        d="M19 9l-7 7-7-7"
                      />
                    </svg>
                  </span>
                </template>
              </v-expansion-panel-title>
              <v-expansion-panel-text>
                {{ item.text }}
              </v-expansion-panel-text>
            </v-expansion-panel>
          </v-expansion-panels>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";

const isRotated = ref(false);

function toggleRotation() {
  isRotated.value = !isRotated.value;
}
const items = ref([
  {
    title: "What is FarmVest?",
    text:
      "FarmVest is a platform that helps you invest in agriculture securely and efficiently.",
  },
  {
    title: "How safe is FarmVest",
    text:
      "FarmVest employs state-of-the-art security measures to protect your investments and personal information.",
  },
  {
    title: "What do I gain from using FarmVest?",
    text:
      "With FarmVest, you gain access to sustainable investment opportunities and steady returns in agriculture.",
  },
]);
</script>

<style lang="scss" scoped>
@use "../assets/styles/common-styles/container.scss" as *;
@use "../assets/styles/common-styles/common.scss" as *;
.pathway {
  // .pathway__container

  &__container {
    display: flex;
    flex-direction: row;
    gap: 4rem;
    @media screen and (max-width: $tablet) {
      gap: 2rem;
      padding: 1rem 0;
    }
    @media screen and (max-width: $mobile) {
      flex-direction: column-reverse;
      gap: 1rem;
      padding-left: 0;
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
    padding: 0;
  }
  img {
    max-width: 90%;
    max-height: 600px;
    object-fit: cover;
    border-radius: 20px;
    @media screen and (max-width: $mobile) {
      max-width: 100%;
      height: 100%;
      border-radius: 0;
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
    font-size: 70px;
    padding-bottom: 20px;
    @media screen and (max-width: $tablet) {
      font-size: 50px;
    }
    @media screen and (max-width: 670px) {
      font-size: 40px;
    }
  }

  // .content__paragraph

  &__paragraph {
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
}
.v-expansion-panel {
  background-color: rgba($secondaryColor, 0.1);
  border-radius: 8px;
  margin-bottom: 1rem;
}

.v-expansion-panel-title {
  font-size: 24px;
  padding: 30px;
  line-height: 1.5;
  @media screen and (max-width: $mobile) {
    font-size: 18px;
    padding: 15px;
  }
}

.v-expansion-panel-text {
  color: #7f8c8d;
  padding: 0.5rem 1rem;
  font-size: 18px;
  line-height: 150%;
}

.custom-icon svg {
  transition: transform 0.3s ease-in-out;
}

.custom-icon svg.rotated {
  transform: rotate(180deg);
}
</style>
