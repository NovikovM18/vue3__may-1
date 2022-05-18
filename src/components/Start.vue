<template>
  <div class="main">
    <div class="main__img"></div>
    <div class="main__title">
      <h1 class="main__title_title">Уборка 
        <span>
          {{ place }}
        </span>
        в Киеве
      </h1>
      <p class="main__title_description">Мы уберем у вас дома или в офисе. Наведем чистоту после ремонта и проведем генеральную уборку.</p>
    </div>
  </div>
</template>

<script>
  export default {
    props: ["place"]
  }
</script>

<style lang='scss'>
.main {
  display: flex;
  height: 100vh;
  width: 100%;
  &__img {
    width: 50%;
    background-image: url('../assets/img/main_home.png');
    background-repeat: no-repeat;
    background-size: cover;
      @media (max-width: 768px) {
        width: 0;
      }
  }
  &__title {
    font-family: 'Travels-Regular';
    margin-top: -10px;
    width: 50%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
      @media (max-width: 768px) {
        width: 100%;
        justify-content: space-around;
        background-image: url('../assets/img/main_home.png');
      }
    &_title {
      width: 384px;
      font-weight: 400;
      font-size: 76px;
      line-height: 110%;
      color: #404040;
        @media (max-width: 1232px) {
          width: 85%;
        }
    }
    &_description {
      width: 384px;
      font-style: normal;
      font-weight: 400;
      font-size: 18px;
      line-height: 140%;
      color: #404040;
        @media (max-width: 1232px) {
          width: 85%;
        }
        @media (max-width: 768px) {
          width: 60%;
        }
    }
  }
}
</style>