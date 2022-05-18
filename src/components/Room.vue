<template>
  <div 
    :class="[this.activated ? 'room-active' : '']" 
    class="room" 
    id="room"
  >
    <transition name='room-menu'>
      <div v-if="this.activated" class="room__menu">
        <p class="room__menu_title">Как мы убираем</p>
        <ul class="room__menu_list">
          <a 
            href="#room"
            :class="[this.room === 1 ? 'rmi-active' : '']"
            class="room__menu_list_item"
            @click="room1"
          >
            <li>
                Кухня
            </li>
          </a>
          <a 
            href="#room"
            :class="[this.room === 2 ? 'rmi-active' : '']"
            class="room__menu_list_item"
            @click="room2"
          >          
          <li>
              Комнаты
            </li>
          </a>
          <a 
            href="#room"
            :class="[this.room === 3 ? 'rmi-active' : '']"
            class="room__menu_list_item"
            @click="room3"
          >
            <li>
              Ванная
            </li>
          </a>
          <a 
            href="#room"
            :class="[this.room === 4 ? 'rmi-active' : '']"
            class="room__menu_list_item"
            @click="room4"
          >
            <li>
              Прихожая
            </li>
          </a>
        </ul>
      </div>
    </transition>
    <transition name='room-start'>
      <img 
        v-if="this.room === 0" 
        class="room__img-start" 
        src="../assets/img/room_kitchen.png" 
        alt="комнаты"
      >
    </transition>
    <div class="room__item">
      <transition name='room'>
          <img 
          v-if="this.room === 1 || this.room === 2" 
            class="room__img" 
            src="../assets/img/room_k.png" 
            alt="кухня"
          >
      </transition>
      <transition name='plus'>
        <div
            v-if="this.room === 1 || this.room === 2" 
            class="room__plus k1" 
        >
          <img 
            src="../assets/img/+.png" 
            alt="+"
          >
          <p class="room__plus_p">Чистим фасад вытяжки</p>
        </div>
      </transition>
      <transition name='plus'>
        <div
            v-if="this.room === 1 || this.room === 2" 
            class="room__plus k2" 
        >
          <img 
            src="../assets/img/+.png" 
            alt="+"
          >
          <p class="room__plus_p">Чистим печку</p>
        </div>
      </transition>
      <transition name='plus'>
        <div
            v-if="this.room === 1 || this.room === 2" 
            class="room__plus k3" 
        >
          <img 
            src="../assets/img/+.png" 
            alt="+"
          >
          <p class="room__plus_p">Чистим пол</p>
        </div>
      </transition>
      <transition name='plus'>
        <div
            v-if="this.room === 1 || this.room === 2" 
            class="room__plus k4" 
        >
          <img 
            src="../assets/img/+.png" 
            alt="+"
          >
          <p class="room__plus_p">Чистим полки</p>
        </div>
      </transition>
      <transition name='plus'>
        <div
            v-if="this.room === 1 || this.room === 2" 
            class="room__plus k5" 
        >
          <img 
            src="../assets/img/+.png" 
            alt="+"
          >
          <p class="room__plus_p">Чистим стол</p>
        </div>
      </transition>
      <transition name='plus'>
        <div
            v-if="this.room === 1 || this.room === 2" 
            class="room__plus k6" 
        >
          <img 
            src="../assets/img/+.png" 
            alt="+"
          >
          <p class="room__plus_p">Чистим холодильник</p>
        </div>
      </transition>
      <transition name='plus'>
        <div
            v-if="this.room === 1 || this.room === 2" 
            class="room__plus k7" 
        >
          <img 
            src="../assets/img/+.png" 
            alt="+"
          >
          <p class="room__plus_p">Чистим мойку</p>
        </div>
      </transition>
    </div>
    <div class="room__item">  
      <transition name='room'>
        <img 
          v-if="this.room === 3 || this.room === 4" 
              class="room__img" 
              src="../assets/img/room_br.png" 
              alt="ванная"
        >
      </transition>
      <transition name='plus'>
        <div
          v-if="this.room === 3 || this.room === 4"
          class="room__plus br1" 
        >
          <img 
            src="../assets/img/+.png" 
            alt="+"
          >
          <p class="room__plus_p">Чистим зеркало</p>
        </div>
      </transition>
      <transition name='plus'>
        <div
          v-if="this.room === 3 || this.room === 4"
          class="room__plus br2" 
        >
          <img 
            src="../assets/img/+.png" 
            alt="+"
          >
          <p class="room__plus_p">Чистим тумбу</p>
        </div>
      </transition>
      <transition name='plus'>
        <div
          v-if="this.room === 3 || this.room === 4"
          class="room__plus br3" 
        >
          <img 
            src="../assets/img/+.png" 
            alt="+"
          >
          <p class="room__plus_p">Чистим унитаз</p>
        </div>
      </transition>
      <transition name='plus'>
        <div
          v-if="this.room === 3 || this.room === 4"
          class="room__plus br4" 
        >
          <img 
            src="../assets/img/+.png" 
            alt="+"
          >
          <p class="room__plus_p">Чистим кафель</p>
        </div>
      </transition>
      <transition name='plus'>
        <div
          v-if="this.room === 3 || this.room === 4"
          class="room__plus br5" 
        >
          <img 
            src="../assets/img/+.png" 
            alt="+"
          >
          <p class="room__plus_p">Чистим ванну</p>
        </div>
      </transition>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activated: false,
      room: 0
    }
  },
  methods: {
    room1() {
      this.room = 1;
    },
    room2() {
      this.room = 2;
    },
    room3() {
      this.room = 3;
    },
    room4() {
      this.room = 4;
    }
  },
  mounted() {
    let that = this;
    const el = document.getElementById('room');
    window.addEventListener("scroll", function(){
      const down = window.visualViewport.height + window.pageYOffset;
      if ((down - el.offsetHeight / 2) >= el.offsetTop) {
        that.activated = true;
      } else {
        that.activated = false;
        that.room = 0
      }
    });
  }
}
</script>

<style lang="scss">
.room {
  position: relative;
  margin: 0 auto;
  margin-top: 52px;
  width: 80%;
  max-width: 1094px;
  display: flex;
  justify-content: center;
  height: 630px;
  color: #FFFFFF;
    @media (max-width: 666px) {
      height: 462px;
    }
  &__item {
    overflow: hidden;
    position: absolute;
    right: 0;
    width: auto;
    height: 100%;
  }
  &__img {
    width: auto;
    right: 0;
    height: 100%;
    &-start {
      width: 100%;
    }
    @media (max-width: 540px) {
      width: 100%;
    }
  }
  &__plus {
    text-align: center;
    position: absolute;
    &_p {
      margin: 0;
      padding: 1px 4px;
      margin-top: -64px;
      font-size: 13px;
      line-height: 130%;
      text-align: center;
      color: #636C81;
      background-color: #fff;
      border-radius: 4px;
      pointer-events: none;
      opacity: 0;
      transition: 500ms;
    }
    & :hover + &_p {
      opacity: 1;
    }
  }
  &__menu {
    z-index: 2;
    position: absolute;
    box-sizing: border-box;
    padding: 35px 0 0 53px;
    width: 375px;
    height:100%;
    left: 0px;
    top: 0px;
    background: #5A30F0;
      @media (max-width: 1048px ) {
        padding: 35px 0 0 20px;
        width: 188px;
      }
      @media (max-width: 856px) {
        width: 100%;
        height: 10%;
        padding: 0;
      }
    &_title {
      margin: 0;
      font-size: 16px;
      line-height: 130%;
        @media (max-width: 856px) {
          display: none;
        }
    }
    &_list {
      height: 90%;
      margin: 0;
      padding: 0;
      display: flex;
      flex-direction: column;
      justify-content: center;
      gap: 1.6rem;
      list-style: none;
        @media (max-width: 1048px ) {
          font-size: 22px;
        }
        @media (max-width: 856px) {
          width: 100%;
          height: 100%;
          flex-direction: row;
          align-items: center;
          justify-content: space-around;
        }
        @media (max-width: 666px ) {
          gap: 0.4rem;
        }
      &_item {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        font-family: 'Travels-Light';
        font-size: 44px;
        line-height: 120%;
        text-decoration: none;
        color: inherit;
        opacity: 0.7;
        transition: 500ms;
          @media (max-width: 1048px ) {
            font-size: 22px;
          }
          @media (max-width: 666px) {
            font-size: 16px;
          }
        &:hover {
          opacity: 1;
        }
      }
      &_item.rmi-active {
        display: flex;
        font-style: italic;
        opacity: 1;
        transition: 500ms;
          @media (max-width: 856px) {
            font-style: normal;
          }
        &::before {
          content: '→';
          @media (max-width: 856px) {
            content: '';
          }
        }
      }
    }
  }
  transition: 1s;
}

.k1 {
  left: 15%;
  top: 33%;
}
.k2 {
  left: 18%;
  top: 55%;
}
.k3 {
  left: 22%;
  top: 90%;
}
.k4 {
  left: 38%;
  top: 57%;
}
.k5 {
  left: 47%;
  top: 68%;
}
.k6 {
  left: 48%;
  top: 39%;
}
.k7 {
  left: 78%;
  top: 62%;
}

.br1 {
  left: 20%;
  top: 42%;
}
.br2 {
  left: 26%;
  top: 82%;
}
.br3 {
  left: 53%;
  top: 86%;
}
.br4 {
  left: 61%;
  top: 49%;
}
.br5 {
  left: 78%;
  top: 80%;
}

.room-active {
  margin: 0;
  margin-top: 52px;
  width: 100%;
  max-width: 1214px;
  display: flex;
  transition: 1s;
}

.room-menu-enter-active{
  transition: all 1s ease;
  transition-delay: 100ms;
  transform: translateX(0px);
}
.room-menu-leave-active {
  transition: all 1s ease;
  transform: translateX(0px);
}
.room-menu-enter-from{
  opacity: 0;
  transform: translateX(-100%);
}
.room-menu-leave-to {
  opacity: 0;
}

.room-enter-active{
  transition: all 1s ease;
  transform: translateX(0px);
}
.room-leave-active {
  transition: all 1s ease;
  transform: translateX(0px);
}
.room-enter-from{
  transform: translateX(-100%);
}
.room-leave-to {
  transform: translateX(100%);
}

.room-start-enter-active,
.room-start-leave-active {
  transition: all 1s ease;
  opacity: 1;
}
.room-start-enter-from,
.room-start-leave-to {
  opacity: 0;
}

.plus-enter-active{
  transition: all 500ms ease;
  transition-delay: 1s;
  opacity: 1;
}
.plus-leave-active {
  transition: all 500ms ease;
  opacity: 1;
}
.plus-enter-from{
  opacity: 0;
}
.plus-leave-to {
  opacity: 0;
}
</style>