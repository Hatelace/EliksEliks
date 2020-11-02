<template>
  <div class="page_one">
    <div class="candy_bg">
      <div class="navigation">
        <img src="../assets/img/elics-logo.png" />
        <div class="navigation__items">
          <a href="#">Главная</a>
          <a href="#">О нас</a>
          <a href="#">Каталог</a>
          <a href="#">Собери свой трдельник</a>
          <a href="#">Контакты</a>
        </div>
      </div>
      <div class="title">
        <h1>Особенная выпечка. Трдельники.</h1>
        <div class="bonus_text">
          <img src="../assets/img/coffe.png" />
          <p>При покупке трдельника кофе в подарок!</p>
        </div>
        <button class="buy_now" v-scroll-to="'#catalog'">
          Заказать уже сейчас
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {}
};
</script>

<style lang="scss" scoped>
@import "../assets/style/fonts.scss";
.page_one {
  background: url("../assets/img/Page1.png");
  background-size: 100% 100%;
  height: 836px;
}
.candy_bg {
  background: url("../assets/img/Page1Candy.png");
  background-size: 100% 100%;
  height: 711px;
  padding: 13px 180px;
}
.navigation {
  display: flex;
  justify-content: space-between;
  align-items: center;
  &__items {
    a {
      @include medium;
      font-size: 18px;
      line-height: 22px;
      color: #fff;
      text-decoration: none;
      cursor: pointer;
      margin-left: 40px;
    }
    a:hover {
      color: #fd0bce;
      border-bottom: 2px solid #fd0bce;
    }
  }
}
.title {
  margin-top: 155px;
  h1 {
    @include bold;
    font-size: 48px;
    line-height: 59px;
    color: #123429;
    margin-bottom: 20px;
    max-width: 540px;
  }
  .bonus_text {
    display: flex;
    align-items: center;
    p {
      @include normal;
      font-size: 18px;
      line-height: 22px;
      color: #123429;
      margin-left: 16px;
    }
  }
  .buy_now {
    margin-top: 59px;
    background: #fd0bce;
    border-radius: 16px;
    width: 319px;
    height: 50px;
    font-size: 18px;
    line-height: 22px;
    cursor: pointer;
    outline: none;
    border: none;
    @include medium;
    color: #ffffff;
  }
}
</style>
