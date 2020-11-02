<template>
  <div class="footer">
    <div class="footer__items">
      <img class="footer-logo" src="../assets/img/footer/elics-logo.png" />
      <div class="contacts">
        <div class="contacts__items">
          <img src="../assets/img/footer/1.png" />
          <a href="87771212121">+7 (777) 121 2121</a>
        </div>
        <div class="contacts__items">
          <img src="../assets/img/footer/2.png" />
          <a href="#">eliksast@gmail.com</a>
        </div>
      </div>
      <div class="social">
        <p>Мы в соц сетях</p>
        <div class="social__links">
          <a href="https://instagram.com/eliks_ast?igshid=9kq5bxpojmsj"
            ><img src="../assets/img/footer/instagram.png"
          /></a>
          <a
            href="https://api.whatsapp.com/send/?phone=77784310143&text&app_absent=0"
            ><img src="../assets/img/footer/whatsapp.png"
          /></a>
        </div>
      </div>
    </div>
    <h1 class="copyright">&copy;eliks 2020</h1>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../assets/style/fonts.scss";
@media all and (max-width: 768px) {
  .footer {
    padding: 40px 0px 60px !important;
    &__items {
      display: flex !important;
      flex-direction: column !important;
      align-items: center !important;
      justify-content: flex-start !important;
    }
  }
  .contacts {
    margin: 0 !important;
    display: flex !important;
    flex-direction: column !important;
    align-items: center !important;
    justify-content: flex-start !important;
    margin-top: 30px !important;
  }
  .social {
    margin: 0 !important;
    margin-top: 20px !important;
    &__links {
      display: flex;
      align-items: center;
      a {
        margin-right: 20px;
      }
    }
  }
}
.footer {
  background: #7ddecd;
  padding: 30px 180px 30px;
  &__items {
    display: flex;
    align-items: center;
  }
}
.contacts {
  margin-left: 155px;
  &__items {
    display: flex;
    align-items: center;
    margin: 10px 0;
    img {
      width: 20px;
    }
    a {
      @include medium;
      font-size: 12px;
      line-height: 22px;
      text-decoration-line: underline;
      margin-left: 10px;
      color: #123429;
    }
  }
}
.social {
  margin-left: 220px;
  p {
    @include medium;
    font-size: 12px;
    line-height: 22px;
    color: #123429;
    margin-bottom: 20px;
  }
  &__links {
    display: flex;
    align-items: center;
    img {
      width: 20px;
    }
    a {
      margin-right: 20px;
    }
  }
}
.copyright {
  @include medium;
  font-size: 12px;
  line-height: 32px;
  color: #fd0bce;
  text-align: center;
  margin-top: 20px;
}
.footer-logo {
  height: 60px;
  width: auto;
}
</style>
