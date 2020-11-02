<template>
  <div class="about">
    <h1>О трдельниках</h1>
    <div class="about_end">
      <img src="../assets/img/end/1.png" alt="" />
      <div class="about_end__text">
        <p>
          <span><b>Трдельник</b></span> – традиционная чешская выпечка в форме
          цилиндра, выпекаемая в специальной гриль-печи или на углях. Он
          готовится исключительно из натуральных ингредиентов.
        </p>
        <img src="../assets/img/end/11.png" alt="" />
        <p>
          Тесто наматывается на деревянный валик, посыпается сахаром и готовится
          в специальной печи для трдельника в течение 3-4 минут.
        </p>
        <img src="../assets/img/end/22.png" alt="" />
        <p>
          Приготовленный трдельник снимается с валика, посыпается любой посыпкой
          на ваш вкус.
        </p>
      </div>
      <img src="../assets/img/end/2.png" alt="" />
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../assets/style/fonts.scss";
@media all and (max-width: 768px) {
  .about {
    background: url("../assets/img/mobile/bgabout.png") !important;
    background-size: 100% 100% !important;
    height: 1019px !important;
    padding: 40px 30px 0px 30px !important;
    h1 {
      font-size: 28px !important;
      line-height: 34px !important;
    }
    &_end {
      display: flex !important;
      flex-direction: column !important;
      justify-content: flex-start !important;
      align-items: center !important;
      img {
        width: 134px !important;
        height: 200px !important;
      }
      &__text {
        width: 100% !important;
        padding: 20px 10px !important;
        img {
          width: 24px !important;
          height: 24px !important;
        }
        p {
          font-size: 14px !important;
          line-height: 17px !important;
        }
      }
    }
  }
}
.about {
  background: url("../assets/img/end/bg.png");
  background-size: 100% 100%;
  height: 759px;
  padding-top: 60px;
  h1 {
    @include medium;
    text-align: center;
    font-size: 48px;
    line-height: 59px;
    color: #123429;
  }
}
.about_end {
  display: flex;
  justify-content: center;
  align-items: center;
  &__text {
    background: #ffffff;
    box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.25);
    border-radius: 16px;
    width: 530px;
    height: 402px;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding-top: 20px;
    margin: 0 20px;
    p {
      @include medium;
      text-align: center;
      max-width: 490px;
      font-size: 18px;
      line-height: 22px;
      color: #123429;
      span {
        color: #fd0bce;
      }
    }
    img {
      margin-top: 40px;
      margin-bottom: 10px;
    }
  }
}
</style>
