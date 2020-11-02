<template>
  <div class="main">
    <img src="../assets/img/person.png" />
    <div class="description">
      <p>
        <b>Добро пожаловать в</b> <span><b>Eliks!</b></span>
      </p>
      <br />
      <p>
        Меня зовут Еламан. Я и моя команда долго и тщательно отбирали рецепты
        самых вкусных и ярких мировых десертов. Хрустящие чешские трдельники,
        ароматные бельгийские вафли, воздушный испанский чизкейк - каждое из
        этих угощений как признание в любви к своему делу и к вам, друзья.
      </p>
      <br />
      <p>
        <span><b>Приятного аппетита!</b></span>
      </p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/style/fonts.scss";
@media all and (max-width: 768px) {
  .main {
    padding: 40px 30px 80px !important;
    background: url("../assets/img/mobile/bginfo.png") !important;
    background-size: 100% 100%;
    flex-direction: column !important;
    text-align: center !important;
  }
  .description {
    width: 100% !important;
    margin-top: 20px !important;
    margin-left: 0 !important;
    p {
      @include mobileSize;
    }
  }
}
.main {
  background: url("../assets/img/bginfo.png");
  background-position: center;
  background-size: contain;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 55px 180px 120px;
}
.description {
  max-width: 713px;
  margin-left: 113px;
  p {
    @include normal;
    font-size: 18px;
    line-height: 22px;
    color: #123429;
    span {
      color: #fd0bce;
    }
  }
}
</style>
