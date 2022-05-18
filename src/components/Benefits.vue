<template>
  <div class="benefits" id="benefits">
    <div class="benefits__block">
      <transition appear name="ben-1">
        <div v-if="ben1" class="benefits__item benefit_1">
          <p class="benefits__item_description">Тщательно отобранный персонал</p>
          <div class="benefits__item_img-box">
            <div class="benefits__item_img ben_1"></div>
          </div>
          <span>Не нужно тратить время, силы и ресурсы на разме- щение вакансий, проведе- ние собеседований, про- верку кандидатов на должность уборщицы. За счет больших объемов мы можем сделать это эффективнее.</span>
        </div>
      </transition>
      <transition appear name="ben-2">
        <div v-if="ben2" class="benefits__item benefit_2">
          <p class="benefits__item_description">Качественная эко-химия</p>
          <div class="benefits__item_img-box">
            <div class="benefits__item_img ben_2-1"></div>
            <div class="benefits__item_img ben_2-2"></div>
            <div class="benefits__item_img ben_2-3"></div>
          </div>
          <span>Не нужно тратить время, силы и ресурсы на разме- щение вакансий, проведе- ние собеседований, про- верку кандидатов на должность уборщицы. За счет больших объемов мы можем сделать это эффективнее.</span>
        </div>
      </transition>
    </div>
    <div class="benefits__block">
      <transition appear name="ben-3">
        <div v-if="ben3" class="benefits__item benefit_3">
          <p class="benefits__item_description">Контролируем качество</p>
          <div class="benefits__item_img-box">
            <div class="benefits__item_img ben_3"></div>
          </div>
          <span>Не нужно тратить время, силы и ресурсы на разме- щение вакансий, проведе- ние собеседований, про- верку кандидатов на должность уборщицы. За счет больших объемов мы можем сделать это эффективнее.</span>
        </div>
      </transition>
      <transition appear name="ben-4">
        <div v-if="ben4" class="benefits__item benefit_4">
          <p class="benefits__item_description">Работаем круглосуточно</p>
          <div class="benefits__item_img-box">
            <div class="benefits__item_img ben_4"></div>
          </div>
          <span>Не нужно тратить время, силы и ресурсы на разме- щение вакансий, проведе- ние собеседований, про- верку кандидатов на должность уборщицы. За счет больших объемов мы можем сделать это эффективнее.</span>
        </div>
      </transition>
    </div>
  </div>
</template>

<script>

export default {
  data() {
    return {
      ben1: false,
      ben2: false,
      ben3: false,
      ben4: false
    }
  },
  created () {

    },
  methods: {
    showBen() {
      this.ben1 = true;
      this.ben2 = true;
      this.ben3 = true;
      this.ben4 = true;
    }
  },

  mounted() {
    let that = this;
    let el = document.getElementById('benefits')
    window.addEventListener("scroll", function(){
      const down = window.visualViewport.height + window.pageYOffset;
      if (down - 20 >= el.offsetTop) {
        that.showBen()
      }
    });
  }
}
</script>

<style lang="scss">
.benefits {
  margin-top: 20px;
  padding-top: 52px;
  display: flex;
  justify-content: space-between;
  gap: 40px;
    @media (max-width: 1340px ) {
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }
  &__block {
    display: flex;
    gap: 40px;
      @media (max-width: 1340px ) {
        justify-content: space-around;
      }
      @media (max-width: 768px ) {
        flex-direction: column;
      }
  }
  &__item > span {
    font-family: 'Travels-Light';
    margin: 30px;
    position: absolute;
    font-weight: 400;
    font-size: 16px;
    line-height: 140%;
    color: #FFFFFF;
    width: 240px;
    opacity: 0;
    &:hover{
      opacity: 1;
    }
  }
  &__item {
    position: relative;
    width: 300px;
    height: 328px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    background: #F3F6FB;
    border-radius: 8px;
    transition: all 500ms;
    &:hover {
      background: #5A30F0;
      color: #FFF;
      content: '123erwdtwerfwert';
      transition: all 1s;
    }
    &:hover :first-child {
      opacity: 0;
    }
    &:hover :nth-child(2){
      opacity: 0;
    }
    
    &:hover span{
      opacity: 1;
    }
    &_description {
      width: 219px;
      font-size: 24px;
      line-height: 130%;
      text-align: center;
      color: #404040;
      transition: 250ms;
    }
    &_img {
      transition: 500ms;
    }
    &_img-box {
      display: flex;
      align-items: flex-end;
      gap: 12px;
    }
  }
}
.ben_1 {
  width: 151px;
  height: 151px;
  background-image: url('../assets/img/ben_1.png');
  background-repeat: no-repeat;
  background-size: cover;
}
.ben_2-1 {
  width: 51.11px;
  height: 152px;
  background-image: url('../assets/img/ben_2-1.png');
  background-repeat: no-repeat;
  background-size: cover;
}
.ben_2-2 {
  width: 58.25px;
  height: 162px;
  background-image: url('../assets/img/ben_2-2.png');
  background-repeat: no-repeat;
  background-size: cover;
}
.ben_2-3 {
  width: 53px;
  height: 152px;
  background-image: url('../assets/img/ben_2-3.png');
  background-repeat: no-repeat;
  background-size: cover;
}
.ben_3 {
  width: 211px;
  height: 172px;
  background-image: url('../assets/img/ben_3.png');
  background-repeat: no-repeat;
  background-size: cover;
  
}
.ben_4 {
  width: 151px;
  height: 151px;
  background-image: url('../assets/img/ben_4.png');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}

.ben-1-enter-active,
.ben-1-leave-active {
  transition: all 1200ms ease;
  transform: translateY(0px);
}
.ben-1-enter-from,
.ben-1-leave-to {
  opacity: 0;
  transform: translateY(300px);
}

.ben-2-enter-active,
.ben-2-leave-active {
  transition: all 1200ms ease;
  transition-delay: 500ms;
  transform: translateY(0px);
}
.ben-2-enter-from,
.ben-2-leave-to {
  opacity: 0;
  transform: translateY(300px);
}

.ben-3-enter-active,
.ben-3-leave-active {
  transition: all 1200ms ease;
  transition-delay: 1000ms;
  transform: translateY(0px);
}
.ben-3-enter-from,
.ben-3-leave-to {
  opacity: 0;
  transform: translateY(300px);
}

.ben-4-enter-active,
.ben-4-leave-active {
  transition: all 1200ms ease;
  transition-delay: 1500ms;
  transform: translateY(0px);
}
.ben-4-enter-from,
.ben-4-leave-to {
  opacity: 0;
  transform: translateY(300px);
}
</style>