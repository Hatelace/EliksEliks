<template>
  <div class="main">
    <div class="page_one">
      <div class="navigation">
        <img src="../assets/img/elics-logo.png" />
        <div class="navigation__links">
          <a href="#">Главная</a>
          <a
            href="#"
            v-scroll-to="{
              el: '#about',
              easing: 'linear',
              duration: 500,
              offset: -200
            }"
            >О нас</a
          >
          <a
            href="#"
            v-scroll-to="{
              el: '#catalog',
              easing: 'linear',
              duration: 500
            }"
            >Каталог</a
          >
          <a
            href="#"
            v-scroll-to="{
              el: '#calculator',
              easing: 'linear',
              duration: 500,
              offset: -100
            }"
            >Собери свой трдельник</a
          >
          <a
            href="#"
            v-scroll-to="{
              el: '#contacts',
              easing: 'linear',
              duration: 500
            }"
            >Контакты</a
          >
        </div>
      </div>
      <div class="title">
        <h1>Особенная выпечка. Трдельники.</h1>
        <p>
          <img src="../assets/img/coffe.png" />При покупке трдельника кофе в
          подарок!
        </p>
        <button
          class="buy_now"
          v-scroll-to="{
            el: '#catalog',
            easing: 'linear',
            duration: 500
          }"
        >
          Заказать уже сейчас
        </button>
      </div>
    </div>
    <ElemanInfo id="about" />
    <Catalog id="catalog" />
    <Calculator id="calculator" />
    <About />
    <Location id="contacts" />
    <Foooter />
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../assets/style/fonts.scss";
@media all and (max-width: 768px) {
  .navigation {
    padding-top: 20px !important;
    padding-left: 30px !important;
    &__links {
      display: none !important;
    }
  }
  .page_one {
    background: url("../assets/img/mobile/bg.png") !important;
    height: 780px !important;
    background-size: 100% 100% !important;
    padding: 0 !important;
  }
  .title {
    text-align: center !important;
    margin-top: 32px !important;
    h1 {
      font-size: 28px !important;
      line-height: 34px !important;
      margin-bottom: 10px !important;
    }
    p {
      flex-direction: column !important;
      margin: 0 !important;
      font-size: 14px !important;
      line-height: 17px !important;
      img {
        margin-bottom: 10px !important;
      }
    }
    .buy_now {
      margin-top: 350px !important;
    }
  }
}
.page_one {
  background: url("../assets/img/bg.png");
  background-size: 100% 100%;
  height: 836px;
  padding: 13px 180px;
}
.navigation {
  display: flex;
  justify-content: space-between;
  align-items: center;
  &__links {
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
  p {
    display: flex;
    align-items: center;
    @include normal;
    font-size: 18px;
    line-height: 22px;
    color: #123429;
    margin-right: 16px;
  }
  .buy_now {
    @include medium;
    color: #ffffff;
    font-size: 18px;
    line-height: 22px;
    margin-top: 59px;
    background: #fd0bce;
    border-radius: 16px;
    width: 319px;
    height: 50px;
    cursor: pointer;
    outline: none;
    border: none;
  }
}
</style>
