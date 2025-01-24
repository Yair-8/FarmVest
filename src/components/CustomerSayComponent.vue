<template>
  <section class="customers">
    <div class="customers__container">
      <h2 class="title">What <span>Customers</span> have to say</h2>
      <p class="paragraph">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut eu, mollis
        aenean sit dictum tincidunt. Ut arcu, suscipit ac
      </p>
      <div class="reviews">
        <div
          v-for="(review, index) in reviews"
          :key="index"
          class="reviews-item"
        >
          <div class="reviews-image">
            <img :src="review.img" alt="customer image" />
          </div>
          <div class="reviews-content">
            <p class="reviews-paragraph">{{ review.review }}</p>
            <h5 class="reviews-title">{{ review.name }}</h5>
          </div>
        </div>
      </div>
      <button class="button button--green">View All</button>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
import customer1 from "@/assets/images/customer1.png";
import customer2 from "@/assets/images/customer2.png";
const reviews = ref([
  {
    img: customer1,
    name: "Tonia Smart",
    review:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut eu, mollis aenean sit dictum tincidunt. Ut arcu, suscipit ac",
  },
  {
    img: customer2,
    name: "Grace Obi",
    review:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut eu, mollis aenean sit dictum tincidunt. Ut arcu, suscipit ac",
  },
]);
</script>

<style lang="scss" scoped>
@use "../assets/styles/common-styles/container.scss" as *;
@use "../assets/styles/common-styles/common.scss" as *;
.customers {
  margin-bottom: 20px;
  // .customers__container

  &__container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 1rem;
    @media screen and (max-width: $tablet) {
      gap: 0.5rem;
      padding: 1rem 0;
    }
  }
}
.title {
  padding: 0 1rem;
  @media screen and (max-width: 1085px) {
    font-size: 56px;
  }
  @media screen and (max-width: $tablet) {
    font-size: 50px;
  }
  @media screen and (max-width: 450px) {
    font-size: 40px;
  }
}
.paragraph {
  padding: 0 1rem;
  max-width: 550px;
  @media screen and (max-width: $tablet) {
    padding-bottom: 0.5rem;
  }
}
.reviews {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 2rem;

  @media screen and (max-width: $mobile) {
    grid-template-columns: repeat(1, 1fr);
  }
}
.reviews-item {
  display: flex;
  flex-direction: row;

  @media screen and (max-width: 450px) {
    flex-direction: column;
  }
}
.reviews-image {
  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 20px 0 0 20px;
    @media screen and (max-width: 450px) {
      border-radius: 20px 20px 0 0;
    }
  }
}
.reviews-content {
  padding: 2rem 2rem;
  background-color: rgba($secondaryColor, 0.1);
  min-width: 300px;
  height: 100%;
  flex: 1;
  border-radius: 0 20px 20px 0;
  position: relative;
  @media screen and (max-width: 1180px) {
    min-width: 200px;
    padding: 1rem 1rem;
  }
  @media screen and (max-width: $mobile) {
    font-size: 20px;
    line-height: 1;
  }
  @media screen and (max-width: 450px) {
    border-radius: 0 0 20px 20px;
  }
}
.reviews-title {
  position: absolute;
  bottom: 0;
  left: 0;
  padding: 2rem 2rem;
  font-weight: 700;
  @media screen and (max-width: 1180px) {
    position: static;
    padding: 1rem 0;
  }
  @media screen and (max-width: $mobile) {
    position: absolute;
    padding: 1rem 1rem;
  }
  @media screen and (max-width: 450px) {
    position: static;
    padding: 1rem 0;
  }
}
.reviews-paragraph {
  line-height: 1.8;
  @media screen and (max-width: $mobile) {
    line-height: 1.3;
  }
}
.button {
  // .button--green

  &--green {
  }
}
</style>
