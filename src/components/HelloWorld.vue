<template>
  <header class="header">
    <nav class="header__navbar">
      <div class="header__navbar-left">
        <h2 class="header__navbar-logo">Quirk</h2>

        <ul class="header__navbar-links">
          <li class="header__navbar-link">Course</li>
          <li class="header__navbar-link">Download</li>
          <li class="header__navbar-link">Pricing</li>
        </ul>
      </div>
      <div class="header__mobile animate" v-if="navStyle">
        <div class="header__mobile-top">
          <h2 class="header__mobile-logo">Quirk</h2>
          <i class="fas fa-times" @click="closeNav"></i>
        </div>
        <ul class="header__mobile-links">
          <li class="header__mobile-link">Course</li>
          <li class="header__mobile-link">Download</li>
          <li class="header__mobile-link">Pricing</li>
        </ul>
        <a href="#" class="header__navbar-btn">LOGIN</a>
      </div>
      <i class="fas fa-bars header__navbar-icon" @click="openNav"></i>
      <div class="header__navbar-right">
        <a href="#" class="header__navbar-btn ">LOGIN</a>
      </div>
    </nav>
    <div class="header__content">
      <div class="header__info">
        <h1 class="header__heading-big">Design System Course</h1>
        <p class="header__heading-paragraph">
          Build a design system from scratch and learn all about workflow
        </p>
        <div class="header__btn-con">
          <a href="#" class="header__btn-big red">LOOK INSIDE</a>
          <a href="#" class="header__btn-big green">ENROLL NOW</a>
        </div>
        <p class="header__special">Special price 15% off!</p>
      </div>
      <img class="header__image" src="../assets/images/hero.svg" alt="hero" />
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      navStyle: false,
    };
  },
  methods: {
    openNav() {
      this.navStyle = true;
    },
    closeNav() {
      this.navStyle = false;
    },
  },
};
</script>

<style lang="scss">
.green {
  color: #fff;
  background-color: #07b51c;
}
.red {
  background-color: #eb346b;
  color: #fff;
}
.animate {
  animation-duration: 1s;
  animation-fill-mode: both;
  transform-origin: right bottom;
  animation-name: rotate;
}
.header {
  &__navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 2em 4em;

    &-left {
      display: flex;
      justify-content: space-around;
      align-items: center;
    }
    &-logo {
      font-size: 1.6em;
      font-weight: 900;
      font-family: serif;
      font-size: 2em;
    }
    &-icon {
      display: none;
    }
    &-links {
      display: flex;
      justify-content: space-around;
      align-items: center;
    }
    &-link {
      padding-left: 2em;
      font-size: 1.2em;
      font-weight: 600;
    }
    &-btn {
      border-radius: 0.2em;
      font-size: 0.8em;
      padding: 1em 2em;
      margin: 0.8rem;
      cursor: pointer;
      color: #fff;
      background-color: #07b51c;
    }
    &__mobile {
      display: none !important;
    }
  }
  &__content {
    max-width: 1200px;
    margin: 2em auto;
    text-align: center;
  }
  &__heading-big {
    font-size: 2.5em;
    padding: 0.2em;
  }
  &__heading-paragraph {
    font-size: 1.2em;
    line-height: 1.8;
    padding: 0.2em;
    margin-bottom: 1.3em;
  }
  &__btn-con {
    display: flex;
    align-items: center;
    justify-content: center;
  }
  &__btn-big {
    border-radius: 0.4em;
    font-size: 0.9em;
    padding: 1em 4em;
    margin: 1em;
    cursor: pointer;
  }
  &__special {
    margin: 0.7em 0 4em 14em;
  }
  &__image {
    width: 70%;
    object-fit: cover;
  }
}
@media (max-width: 860px) {
  .header {
    &__mobile {
      position: fixed;
      display: block;
      top: 0;
      bottom: 0;
      left: 0;
      right: 0;
      height: 100%;
      width: 100%;
      background-color: #fafafa;
    }
    &__content {
      margin: 0;
    }
    &__navbar-left {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    &__mobile-top {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    &__btn-con {
      flex-direction: column;
    }
    &__heading-big {
      font-size: 2em;
    }
    &__heading-paragraph {
      font-size: 0.9em;
      margin-bottom: 2.5em;
    }
    &__btn-big {
      font-size: 0.7em;
      padding: 1em 3.5em;
    }
    &__special {
      margin: 1em;
    }
    &__image {
      margin-top: 1.5em;
      width: 100%;
    }
    &__mobile-top {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin: 2em;
    }
    &__navbar-links {
      display: none;
    }
    &__navbar-right {
      display: none;
    }
    &__navbar-icon {
      display: block;
    }
    &__mobile-link {
      text-align: center;
      padding: 2em;
    }
    &__navbar-btn {
      display: flex;
      align-items: center;
      justify-content: center;
    }
  }
}

@keyframes rotate {
  0% {
    transform: rotate(-90deg);
    opacity: 0;
  }
  100% {
    transform: translateZ(0);
    opacity: 1;
  }
}
</style>
