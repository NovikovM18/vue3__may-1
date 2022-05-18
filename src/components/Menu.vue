<template>
  <div
    :class="[this.scrolling ? 'menu-active' : '']" 
    class="menu" 
    id="menu"
  >
    <div class="menu__container">
      <div class="menu__logo">
        <a href="#">
          <img  class="menu__logo_img" src="../assets/img/menu_logo.png" alt="logo">
        </a>
      </div>
      <div class="menu__switch">
        <p
          :class="[this.switch === 'home' ? 'switch-active' : '']" 
          class="menu__switch_item"
          @click="switchHome"
        >
          Дом
        </p>
        <p 
          :class="[this.switch === 'office' ? 'switch-active' : '']" 
          class="menu__switch_item"
          @click="switchOffice"  
        >
          Офис
        </p>
      </div>
      <div>
        <ul class="menu__list">
          <a class="menu__list_item" href="#benefits">
            <li>
              После ремонта
            </li>
          </a>
          <a class="menu__list_item" href="#benefits">
            <li>
              Генеральная уборка
            </li>
          </a>
          <a class="menu__list_item" href="#benefits">
            <li>
              Регулярная уборка
            </li>
          </a>
          <a class="menu__list_item" href="#benefits">
            <li>
              Мойка окон
            </li>
          </a>
        </ul>
        <transition appear name="mobile">
          
          <ul class="menu__list-mobile" v-if="mobile">
            <img 
              src="@/assets/img/close.png" 
              alt="close" 
              class="menu__list-mobile__close"
              @click="switchMobileOff"
            >
<li>

      <div class="menu__switch-mobile">
        <p
          :class="[this.switch === 'home' ? 'switch-active' : '']" 
          class="menu__switch-mobile_item"
          @click="switchHome"
        >
          Дом
        </p>
        <p 
          :class="[this.switch === 'office' ? 'switch-active' : '']" 
          class="menu__switch-mobile_item"
          @click="switchOffice"  
        >
          Офис
        </p>
      </div>
</li>

            <a class="menu__list_item" href="#benefits" @click="switchMobileOff">
              <li>
                После ремонта
              </li>
            </a>
            <a class="menu__list_item" href="#benefits" @click="switchMobileOff">
              <li>
                Генеральная уборка
              </li>
            </a>
            <a class="menu__list_item" href="#benefits" @click="switchMobileOff">
              <li>
                Регулярная уборка
              </li>
            </a>
            <a class="menu__list_item" href="#benefits" @click="switchMobileOff">
              <li>
                Мойка окон
              </li>
            </a>
            <div class="menu__phone-mobile">
              <p>+380 67 401 69 77</p>
              <p>|</p>
              <p>24/7</p>
            </div>
          </ul>
        </transition>
      </div>
      <div class="menu__phone">
        <p>+380 67 401 69 77</p>
        <p>|</p>
        <p>24/7</p>
      </div>
      <div class="menu__button" @click="switchMobileOn">
        <img src="../assets/img/menu_button.png" alt="button">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      switch: 'home',
      place: 'квартир',
      scrolling: false,
      mobile: false
    }
  },
  created () {
    window.addEventListener('scroll', this.handleScroll);
  },
  methods: {
    switchOffice() {
        this.switch = 'office';
        this.place = 'офисов';
        this.$emit('changePlace', this.place);
      },
    switchHome() {
      this.switch = 'home';
      this.place = 'квартир';
      this.$emit('changePlace', this.place);
      },
    handleScroll() {
      this.scrolling = (window.scrollY > 0);
    },
    switchMobileOn() {
        this.mobile = true;
        document.body.style.overflowY = 'hidden';
    },
    switchMobileOff() {
      this.mobile = false; 
      document.body.style.overflowY = 'auto';
    }
  }
}
</script>

<style lang="scss">
.menu {
  z-index: 5;
  position: fixed;
  width: 100%;
  transition: 1s;

  &__container {
    height: 52px;
    box-sizing: border-box;
    z-index: 5;
    max-width: 1440px;
    margin: 0 auto;
    padding: 0 24px 0 54px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
      @media (max-width: 1232px) {
        padding: 0 20px;
      }
  }
  &__logo {
    &_img {
      width: 96px;
      height: 24px;
      transition: 300ms;
      &:hover {
        transform: scale(1.1);
      }
    }
  }
  &__switch {
    margin: 0 20px;
    box-sizing: border-box;
    display: flex;
    justify-content: space-around;
    align-items: center;
    gap: 4px;
    width: 131px;
    height: 37px;
    background: #FFFFFF;
    border: 1px solid #E2E8F0;
    border-radius: 48px;
      @media (max-width: 924px) {
        display: none;
      }
    &_item {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
      width: 55px;
      height: 31px;
      border-radius: 34px;
      font-size: 14px;
      line-height: 110%;
      color: #636C81;
      transition: 300ms;
      &:hover {
        cursor: pointer;
      }
    }
    &-mobile {
      display: flex;
      flex-direction: row;
      background: #FFFFFF;
      border: 1px solid #E2E8F0;
      border-radius: 48px;
      height: 34px;
      &_item {
        margin-top: 2px;
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 10px;
        width: 55px;
        height: 31px;
        border-radius: 34px;
        font-size: 14px;
        line-height: 110%;
        color: #636C81;
        transition: 300ms;
        &:hover {
          cursor: pointer;
        }
      }
    }
  }
  &__list {
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: space-between;
    gap: 1rem;
    list-style: none;
    text-align: center;
    &_item{
      text-decoration: none;
      color: inherit;
      transition: 300ms;
      &:hover {
        transform: scale(1.025);
      }
    }
    @media (max-width: 768px) {
      display: none;
    }
    &-mobile {
      overflow: hidden;
      position: absolute;
      display: flex;
      flex-direction: column;
      left: 0;
      top: 0;
      margin: 0;
      padding: 80px 0 0 0;
      background: #5A30F0;
      color: #FFF;
      list-style: none;
      width: 100%;
      height: 100vh;
      z-index: 16;
      align-items: center;
      font-size: 1.2rem;
      gap: 3rem;
      &__close {
        position: fixed;
        top: 20px;
        right: 20px;
        width: 12px;
        cursor: pointer;
      }
      @media (min-width: 768px) {
        display: none;
      }
    }
  }
  &__phone {
    margin: 0 20px;
    display: flex;
    justify-content: space-between;
    gap: 1rem;
    font-size: 16px;
    line-height: 120%;
    letter-spacing: 0.2px;
      @media (max-width: 1232px) {
        display: none;
      }
    &-mobile {
      display: flex;
      gap: 2rem;
    }
  }
  &__button {
    display: none;
    @media (max-width: 768px) {
      display: block;
    }
  }
  &__button > img {
    &:hover {
      cursor: pointer;
      transform: scale(1.05);
    }
  }
}

.switch-active {
  background: #5A30F0;
  color: #FFF;
  transition: 600ms;
}

.menu-active {
  background-color: #fff;
  transition: 1s;
}

.mobile-enter-active,
.mobile-leave-active {
  transition: all 500ms ease;
  transform: translateY(0);
}
.mobile-enter-from,
.mobile-leave-to {
  transform: translateY(-100%);
}
</style>
