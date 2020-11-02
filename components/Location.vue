<template>
  <div class="location">
    <h1>Наше месторасположение</h1>
    <div class="location__map">
      <div class="map">
        <iframe
          src="https://yandex.ru/map-widget/v1/?um=constructor%3A5d03f90a442ffaabd3e3e16cb986897cfbd80ef975aa95bc481bc18fb5e5bc58&amp;source=constructor"
          width="716"
          height="359"
          frameborder="0"
        ></iframe>
      </div>
      <div class="adress">
        <h4>г. Астана</h4>
        <div class="adress__exactly">
          <img src="../assets/img/end/loc.png" alt="" />
          <p>
            <span>Кабанбай батыра 58а,</span> <br />корпус 1 (ЖК EXPO
            Boulevard-6)
          </p>
        </div>
        <div class="adress__exactly">
          <img src="../assets/img/end/loc.png" alt="" />
          <p><span>Агыбай батыра 4</span> <br />(возле набережной)</p>
        </div>
        <div class="adress__time">
          <img src="../assets/img/end/clock.png" alt="" />
          <p>10:00 - 22:00</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../assets/style/fonts.scss";
@media all and (max-width: 768px) {
  .location {
    h1 {
      text-align: center !important;
      font-size: 28px !important;
      line-height: 34px !important;
      margin-bottom: 20px !important;
    }
    &__map {
      display: flex !important;
      flex-direction: column !important;
      align-items: center !important;
      justify-content: flex-start !important;
    }
  }
  .map {
    width: 315px !important;
    height: 158px !important;
    margin: 0 !important;
    margin-bottom: 20px !important;
    iframe {
      width: 315px !important;
      height: 158px !important;
    }
  }
}
.location {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-top: 60px;
  padding-bottom: 120px;
  h1 {
    @include medium;
    font-size: 48px;
    line-height: 59px;
    color: #123429;
    margin-bottom: 40px;
  }
  &__map {
    display: flex;
    align-items: flex-start;
    .map {
      width: 716px;
      height: 359px;
      margin-right: 20px;
    }
    .adress {
      h4 {
        @include medium;
        font-size: 18px;
        line-height: 22px;
        color: #123429;
        margin-bottom: 20px;
      }
      &__exactly {
        display: flex;
        align-items: flex-start;
        margin-bottom: 20px;
        p {
          @include medium;
          font-size: 18px;
          line-height: 22px;
          color: #123429;
          margin-left: 11px;
          span {
            color: #fd0bce;
          }
        }
      }
      &__time {
        display: flex;
        align-items: center;
        p {
          @include medium;
          margin-left: 8px;
          font-size: 18px;
          line-height: 22px;
          color: #123429;
        }
      }
    }
  }
}
</style>
