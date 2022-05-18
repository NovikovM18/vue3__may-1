<template>
  <div class="how">
    <p class="how__title">Как мы убираем</p>
    <p class="how__description">Клинер приезжает в назначенное время со всем необходимым и сразу приступает к делу. Вам остаётся только оценить результат.</p>
  </div>
</template>

<style lang="scss">
.how {
  font-family: 'Travels-Light';
  margin: 0 auto;
  margin-top: 148px;
  width: 1094px;
  display: flex;
  justify-content: space-between;
    @media (max-width: 1112px) {
      margin-top: 74px;
      width: 100%;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }
  &__title{
    margin: 0;
    padding: 0;
    font-family: 'Travels-Regular';
    width: 50%;
    font-size: 44px;
    line-height: 120%;
      @media (max-width: 1112px) {
        max-width: 412px;
      }
  }
  &__description{
    width: 50%;
    max-width: 412px;
    font-size: 18px;
    line-height: 140%;
  }
}
</style>