<template>
  <header class="header" :class="{ 'is-hidden': isHeaderHidden }">
    <div class="header__component">
      <div class="header__logo">
        <a href="#">FarmVest</a>
      </div>
      <div class="header__menu menu">
        <div
          :class="{ _active: sidebarVisible }"
          class="menu__icon"
          @click="showSidebar"
        >
          <span></span>
        </div>
        <nav :class="{ _active: sidebarVisible }" class="menu__body">
          <ul class="menu__list">
            <li class="menu__item"><router-link to="/">Home</router-link></li>
            <li class="menu__item">
              <router-link :to="{ name: 'about' }">About Us</router-link>
            </li>
            <li class="menu__item">
              <router-link :to="{ name: 'features' }"> Features </router-link>
            </li>
            <li class="menu__item">
              <router-link :to="{ name: 'how-it-works' }"
                >How it works</router-link
              >
            </li>
          </ul>
        </nav>
      </div>
      <div class="header__actions actions">
        <button class="button">Sign In</button>
        <button class="button button--green">Get Started</button>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref, onUnmounted, onMounted } from "vue";

// Reactive state for sidebar visibility
const sidebarVisible = ref(false);

// Reactive state for header visibility
const isHeaderHidden = ref(false);

// Method to toggle sidebar visibility
function showSidebar() {
  sidebarVisible.value = !sidebarVisible.value;

  if (sidebarVisible.value) {
    document.body.classList.add("no-scroll");
  } else {
    document.body.classList.remove("no-scroll");
  }
}

// Scroll detection logic to hide or show the header
let lastScrollTop = 0;
function handleScroll() {
  const currentScrollTop =
    window.pageYOffset || document.documentElement.scrollTop;

  // Hide header when scrolling down, show when scrolling up
  if (currentScrollTop > lastScrollTop) {
    isHeaderHidden.value = true;
  } else {
    isHeaderHidden.value = false;
  }

  lastScrollTop = currentScrollTop <= 0 ? 0 : currentScrollTop; // Prevent negative scroll
}
// Add scroll event listener on mounted
onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});
// Cleanup on unmount
onUnmounted(() => {
  // Always remove the scroll listener
  window.removeEventListener("scroll", handleScroll);
  document.body.classList.remove("no-scroll");
});
</script>

<style lang="scss" scoped>
@use "../assets/styles/common-styles/container.scss" as *;
.header {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 50;
  font-family: "Lato", serif;
  width: 100%;
  // padding: 20px 0;
  transition: transform 0.3s ease-in-out;
  background-color: #fff;
  @media (min-width: 1250px) {
    padding: 20px 10%;
  }
  // .header__container

  &__component {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    gap: 1rem;
    padding: 0 15px;
    align-items: center;
    font-weight: 500;
    @media (max-width: 1050px) {
      gap: 5px;
    }
    @media (max-width: 991px) {
    }
  }

  // .header__logo

  &__logo {
    font-family: "Lato", serif;
    font-weight: 400;
    font-size: 36px;
    align-items: center;
    @media (max-width: 840px) {
      font-size: 28px;
    }
    @media (max-width: 767px) {
      display: none;
    }
  }

  // .header__menu

  &__menu {
  }

  // .header__actions

  &__actions {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    gap: 1rem;
    @media (max-width: 790px) {
      gap: 0.5rem;
    }
    @media (max-width: 767px) {
      padding-top: 15px;
    }
  }
}
.header.is-hidden {
  transform: translateY(-100%); /* Hide header by moving it off-screen */
}
.menu {
  //.menu__icon
  &__icon {
    display: none;
  }
  // .menu__body

  &__body {
  }

  // .menu__list

  &__list {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-between;
    column-gap: 3.75rem; /* 60/16 */
    row-gap: 1rem;

    @media (max-width: 970px) {
      column-gap: 2rem;
    }
    @media (max-width: 890px) {
      column-gap: 1rem;
    }
  }

  // .menu__item

  &__item {
    flex: 1 1 auto;
    transition: opacity 0.3s;
    @media (any-hover: hover) {
      &:hover {
        opacity: 0.7;
      }
    }
  }
}

.actions {
  &__button {
  }
}
.button {
  padding: 1rem 2rem;

  @media (max-width: 840px) {
    padding: 1rem 1rem;
  }
  @media (max-width: 805px) {
    padding: 0.5rem 0.5rem;
  }
}
// Burger menu

@media (max-width: 767px) {
  .menu__list {
    align-items: flex-start;
    flex-direction: column;
  }
  .menu__list > li {
    padding: 10px 0;
    font-size: 1.5rem; /* 24/16 */
  }
  .menu__icon {
    display: block;
    z-index: 5;
    position: relative;
    width: 1.87rem; /* 30/16 */
    height: 1.12rem; /* 18/16 */

    cursor: pointer;
  }
  .menu__icon span,
  .menu__icon::before,
  .menu__icon::after {
    left: 0;
    position: absolute;
    width: 100%;
    height: 10%;
    background-color: #423939;
    transition: all 0.3s ease 0s;
  }
  //три полосочки меню

  .menu__icon::before,
  .menu__icon::after {
    content: "";
  }
  .menu__icon::before {
    top: 0;
  }
  .menu__icon::after {
    bottom: 0;
  }
  .menu__icon span {
    top: 50%;
    transform: scale(1) translate(0px, -50%);
  }
  .menu__body {
    position: fixed;
    overflow: auto;
    left: -100%;
    top: 0;
    width: 100%;
    height: 100%;
    padding: 100px 30px 30px 30px;
    background-color: #263238;
    transition: left 0.5s ease 0s;
    color: #fff;
  }
  .menu__body._active {
    left: 0;
  }
  .menu__icon._active span {
    transform: scale(0) translate(0px, -50%);
  }
  .menu__icon._active::before {
    top: 50%;
    transform: rotate(-45deg) translate(0px, -50%);
  }
  .menu__icon._active::after {
    bottom: 50%;
    transform: rotate(45deg) translate(0px, 50%);
  }
}
.no-scroll {
  overflow: hidden; /* Prevent scrolling */
  height: 100vh; /* Lock the height of the page */
}
</style>
