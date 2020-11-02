<template>
  <div class="calculator">
    <div class="collect_candy">
      <h1 class="collect_candy__title" v-if="step <= 7">
        Собери свой трдельник
      </h1>
      <p class="step" v-if="step <= 7">
        Шаг {{ step }}/ 7.
        <span v-if="step === 1" class="color">Выбери трдельник</span>
        <span v-else-if="step === 2" class="color"
          >Выбери, чем помазать трдельник изнутри</span
        >
        <span v-else-if="step === 3" class="color">Выбери посыпку</span>
        <span v-else-if="step === 4" class="color"
          >Выбери фрукты в начинку</span
        >
        <span v-else-if="step === 5" class="color"
          >Теперь самое важное. Выберите вкус мороженого</span
        >
        <span v-else-if="step === 6" class="color"
          >Выбери топпинг, чем полить трдельник</span
        >
        <span v-else class="color"
          >Практически все) Выбери украшения для трдельника</span
        >
      </p>
      <!-- trdelnik step -->
      <div v-if="step === 1" class="content_one">
        <div class="boxes">
          <div
            @click.prevent="selectTraditionalType"
            class="box"
            :style="[
              TraditionalConus
                ? { filter: 'grayscale(100%)' }
                : { background: 'white' }
            ]"
          >
            <img src="../assets/img/calculator/1.png" alt="" />
            <h1 ref="type">Традиционый - конус</h1>
            <div class="price">
              <p>600</p>
              <img src="../assets/img/catalog/tenge.png" alt="" />
            </div>
          </div>
          <div
            @click.prevent="selectSugarType"
            class="box"
            :style="[
              TraditionalSugar
                ? { filter: 'grayscale(100%)' }
                : { background: 'white' }
            ]"
          >
            <img src="../assets/img/calculator/1.png" alt="" />
            <h1>с сахаром и корицей</h1>
            <div class="price">
              <p>650</p>
              <img src="../assets/img/catalog/tenge.png" alt="" />
            </div>
          </div>
        </div>
        <div class="click_description">
          <img src="../assets/img/calculator/click.png" alt="" />
          <p>
            Нажми на трдельник, который тебе нравится, и собери все ингредиенты
            на свой вкус.
          </p>
        </div>
      </div>
      <!-- pomazka step -->
      <div v-if="step === 2" class="content_two">
        <h1 class="title_calculator">
          Помазка на стенки изнутри
          <span>100 <img src="../assets/img/catalog/tenge.png" alt=""/></span>
        </h1>
        <div class="pomazka">
          <div
            @click.prevent="selectNutella"
            class="pomazka__box"
            :style="[
              PomazkaNuttela
                ? { filter: 'grayscale(100%)' }
                : { background: 'white' }
            ]"
          >
            <img src="../assets/img/calculator/11.png" alt="" />
            <h2>нутелла</h2>
          </div>
          <div
            @click.prevent="selectWhiteCh"
            class="pomazka__box"
            :style="[
              PomazkaWhiteChocolade
                ? { filter: 'grayscale(100%)' }
                : { background: 'white' }
            ]"
          >
            <img src="../assets/img/calculator/22.png" alt="" />
            <h2>бел.шоколад</h2>
          </div>
          <div
            @click.prevent="selectKaramel"
            class="pomazka__box"
            :style="[
              PomazkaKaramel
                ? { filter: 'grayscale(100%)' }
                : { background: 'white' }
            ]"
          >
            <img src="../assets/img/calculator/33.png" alt="" />
            <h2>карамель</h2>
          </div>
          <div
            @click.prevent="selectArahPas"
            class="pomazka__box"
            :style="[
              PomazkaArahisPasta
                ? { filter: 'grayscale(100%)' }
                : { background: 'white' }
            ]"
          >
            <img src="../assets/img/calculator/44.png" alt="" />
            <h2>арах. паста</h2>
          </div>
        </div>
      </div>
      <!-- posypka step -->
      <div v-if="step === 3" class="content_three">
        <h1 class="title_calculator">
          Посыпка<span
            >100 <img src="../assets/img/catalog/tenge.png" alt=""
          /></span>
        </h1>
        <div class="posypka">
          <div
            @click.prevent="selectOreo"
            class="posypka__box"
            :style="[
              PosipkaOreo
                ? { filter: 'grayscale(100%)' }
                : { background: 'white' }
            ]"
          >
            <img src="../assets/img/calculator/111.png" alt="" />
            <h2>oreo</h2>
          </div>
          <div
            @click.prevent="selectArahis"
            class="posypka__box"
            :style="[
              PosipkaArahis
                ? { filter: 'grayscale(100%)' }
                : { background: 'white' }
            ]"
          >
            <img src="../assets/img/calculator/222.png" alt="" />
            <h2>арахис</h2>
          </div>
          <div
            @click.prevent="selectKorica"
            class="posypka__box"
            :style="[
              PosipkaKorica
                ? { filter: 'grayscale(100%)' }
                : { background: 'white' }
            ]"
          >
            <img src="../assets/img/calculator/333.png" alt="" />
            <h2>корица</h2>
          </div>
          <div
            @click.prevent="selectGrecOreh"
            class="posypka__box"
            :style="[
              PosipkaCgecOreh
                ? { filter: 'grayscale(100%)' }
                : { background: 'white' }
            ]"
          >
            <img src="../assets/img/calculator/444.png" alt="" />
            <h2>грецкий орех</h2>
          </div>
          <div
            @click.prevent="selectKokos"
            class="posypka__box"
            :style="[
              PosipkaKokos
                ? { filter: 'grayscale(100%)' }
                : { background: 'white' }
            ]"
          >
            <img src="../assets/img/calculator/555.png" alt="" />
            <h2>кокос</h2>
          </div>
          <div
            @click.prevent="selectMindal"
            class="posypka__box"
            :style="[
              PosipkaMindal
                ? { filter: 'grayscale(100%)' }
                : { background: 'white' }
            ]"
          >
            <img src="../assets/img/calculator/666.png" alt="" />
            <h2>миндаль</h2>
          </div>
        </div>
      </div>
      <!-- nachinki step -->
      <div v-if="step === 4" class="content_four">
        <h1>Начинки</h1>
        <div class="content_four__swiper">
          <div class="swiper_btns__prev"></div>
          <swiper ref="mySwiper" :options="swiperOptions">
            <swiper-slide>
              <div
                @click.prevent="posypkaBanana"
                class="slider_content"
                :style="[
                  NachinkaBanana
                    ? { filter: 'grayscale(100%)' }
                    : { background: 'white' }
                ]"
              >
                <img src="../assets/img/calculator/swiper/1.png" alt="" />
                <h1>банан</h1>
                <div class="price">
                  <p>400</p>
                  <img src="../assets/img/catalog/tenge.png" alt="" />
                </div>
              </div>
            </swiper-slide>
            <swiper-slide>
              <div
                @click.prevent="posypkaKiwi"
                class="slider_content"
                :style="[
                  NachinkaKiwi
                    ? { filter: 'grayscale(100%)' }
                    : { background: 'white' }
                ]"
              >
                <img src="../assets/img/calculator/swiper/2.png" alt="" />
                <h1>киви</h1>
                <div class="price">
                  <p>400</p>
                  <img src="../assets/img/catalog/tenge.png" alt="" />
                </div>
              </div>
            </swiper-slide>
            <swiper-slide>
              <div
                @click.prevent="posypkaAnanas"
                class="slider_content"
                :style="[
                  NachinkaAnanas
                    ? { filter: 'grayscale(100%)' }
                    : { background: 'white' }
                ]"
              >
                <img src="../assets/img/calculator/swiper/3.png" alt="" />
                <h1>ананас</h1>
                <div class="price">
                  <p>550</p>
                  <img src="../assets/img/catalog/tenge.png" alt="" />
                </div>
              </div>
            </swiper-slide>
            <swiper-slide>
              <div
                @click.prevent="posypkaApelsin"
                class="slider_content"
                :style="[
                  NachinkaApelsin
                    ? { filter: 'grayscale(100%)' }
                    : { background: 'white' }
                ]"
              >
                <img src="../assets/img/calculator/swiper/4.png" alt="" />
                <h1>апельсин</h1>
                <div class="price">
                  <p>450</p>
                  <img src="../assets/img/catalog/tenge.png" alt="" />
                </div>
              </div>
            </swiper-slide>
            <swiper-slide>
              <div
                @click.prevent="posypkaApple"
                class="slider_content"
                :style="[
                  NachinkaApple
                    ? { filter: 'grayscale(100%)' }
                    : { background: 'white' }
                ]"
              >
                <img src="../assets/img/calculator/swiper/5.png" alt="" />
                <h1>яблоко</h1>
                <div class="price">
                  <p>350</p>
                  <img src="../assets/img/catalog/tenge.png" alt="" />
                </div>
              </div>
            </swiper-slide>
            <swiper-slide>
              <div
                @click.prevent="posypkaBerry"
                class="slider_content"
                :style="[
                  NachinkaBerry
                    ? { filter: 'grayscale(100%)' }
                    : { background: 'white' }
                ]"
              >
                <img src="../assets/img/calculator/swiper/6.png" alt="" />
                <h1>ягоды</h1>
                <div class="price">
                  <p>650</p>
                  <img src="../assets/img/catalog/tenge.png" alt="" />
                </div>
              </div>
            </swiper-slide>
            <swiper-slide>
              <div
                @click.prevent="posypkaMango"
                class="slider_content"
                :style="[
                  NachinkaMango
                    ? { filter: 'grayscale(100%)' }
                    : { background: 'white' }
                ]"
              >
                <img src="../assets/img/calculator/swiper/7.png" alt="" />
                <h1>манго</h1>
                <div class="price">
                  <p>650</p>
                  <img src="../assets/img/catalog/tenge.png" alt="" />
                </div>
              </div>
            </swiper-slide>
          </swiper>
          <div class="swiper_btns__next"></div>
        </div>
      </div>
      <!-- ice-cream step -->
      <div v-if="step === 5" class="content_five">
        <h1 class="title_calculator">
          Мороженое<span
            >390 <img src="../assets/img/catalog/tenge.png" alt=""
          /></span>
        </h1>
        <div class="ice_cream">
          <div
            @click.prevent="iceSlivki"
            class="ice_cream__box"
            :style="[
              IceCreamSliv
                ? { filter: 'grayscale(100%)' }
                : { background: 'white' }
            ]"
          >
            <img src="../assets/img/calculator/ice1.png" alt="" />
            <h1>сливочное</h1>
          </div>
          <div
            @click.prevent="iceChokolade"
            class="ice_cream__box"
            :style="[
              IceCreamChokolade
                ? { filter: 'grayscale(100%)' }
                : { background: 'white' }
            ]"
          >
            <img src="../assets/img/calculator/ice2.png" alt="" />
            <h1>шоколадное</h1>
          </div>
          <div
            @click.prevent="iceAssorty"
            class="ice_cream__box"
            :style="[
              IceCreamAssorty
                ? { filter: 'grayscale(100%)' }
                : { background: 'white' }
            ]"
          >
            <img src="../assets/img/calculator/ice3.png" alt="" />
            <h1>ассорти</h1>
          </div>
          <div
            @click.prevent="iceShake"
            class="ice_cream__box"
            :style="[
              IceCreamMilkShake
                ? { filter: 'grayscale(100%)' }
                : { background: 'white' }
            ]"
          >
            <img src="../assets/img/calculator/ice4.png" alt="" />
            <h1>взбитые сливки</h1>
          </div>
        </div>
      </div>
      <!-- topping step -->
      <div v-if="step === 6" class="content_six">
        <h1 class="title_calculator">
          Топпинг<span
            >50 <img src="../assets/img/catalog/tenge.png" alt=""
          /></span>
        </h1>
        <div class="topping">
          <div
            @click.prevent="toppingBanana"
            class="topping__box"
            :style="[
              BananaTopping
                ? { filter: 'grayscale(100%)' }
                : { background: 'white' }
            ]"
          >
            <img src="../assets/img/calculator/top1.png" alt="" />
            <h1>банан</h1>
          </div>
          <div
            @click.prevent="toppingChokolad"
            class="topping__box"
            :style="[
              ChokoladeTopping
                ? { filter: 'grayscale(100%)' }
                : { background: 'white' }
            ]"
          >
            <img src="../assets/img/calculator/top2.png" alt="" />
            <h1>шоколад</h1>
          </div>
          <div
            @click.prevent="toppingBerry"
            class="topping__box"
            :style="[
              BerryTopping
                ? { filter: 'grayscale(100%)' }
                : { background: 'white' }
            ]"
          >
            <img src="../assets/img/calculator/top3.png" alt="" />
            <h1>ягоды</h1>
          </div>
          <div
            @click.prevent="toppingKaramel"
            class="topping__box"
            :style="[
              KaramelTopping
                ? { filter: 'grayscale(100%)' }
                : { background: 'white' }
            ]"
          >
            <img src="../assets/img/calculator/top4.png" alt="" />
            <h1>карамель</h1>
          </div>
        </div>
      </div>
      <!-- decoration step -->
      <div v-if="step === 7" class="content_seven">
        <h1 class="title_calculator">
          Украшения<span
            >390 <img src="../assets/img/catalog/tenge.png" alt=""
          /></span>
        </h1>
        <div class="decorations">
          <div
            @click.prevent="decorationsSnikecrs"
            class="decorations__box"
            :style="[
              SnikersDecorations
                ? { filter: 'grayscale(100%)' }
                : { background: 'white' }
            ]"
          >
            <img src="../assets/img/calculator/dec1.png" alt="" />
            <h1>snickers</h1>
          </div>
          <div
            @click.prevent="decorationsRafaello"
            class="decorations__box"
            :style="[
              RafaelloDecorations
                ? { filter: 'grayscale(100%)' }
                : { background: 'white' }
            ]"
          >
            <img src="../assets/img/calculator/dec2.png" alt="" />
            <h1>rafaello</h1>
          </div>
          <div
            @click.prevent="decorationsOreo"
            class="decorations__box"
            :style="[
              OreoDecorations
                ? { filter: 'grayscale(100%)' }
                : { background: 'white' }
            ]"
          >
            <img src="../assets/img/calculator/dec3.png" alt="" />
            <h1>oreo</h1>
          </div>
        </div>
      </div>
      <!-- py bill step -->
      <div v-if="step == 8" class="pay_bill">
        <h1 class="title_calculator">
          <span>Трдельник собран)</span> Проверь свой заказ
        </h1>
        <div class="content">
          <div class="content__bill">
            <div class="content__bill__price_list">
              <div class="content__bill__price_list__item">
                <p>Трдельник</p>
                <p>{{ trdelnikPrice }} тг</p>
              </div>
              <div class="content__bill__price_list__item">
                <p>Помазка на стенки</p>
                <p>{{ pomazkaPrice }} тг</p>
              </div>
              <div class="content__bill__price_list__item">
                <p>Посыпка</p>
                <p>{{ PosipkaPrice }} тг</p>
              </div>
              <div class="content__bill__price_list__item">
                <p>Начинка</p>
                <p>{{ nachinkaPrice }} тг</p>
              </div>
              <div class="content__bill__price_list__item">
                <p>Мороженое</p>
                <p>{{ icePrice }} тг</p>
              </div>
              <div class="content__bill__price_list__item">
                <p>Топпинг</p>
                <p>{{ toppingPrice }} тг</p>
              </div>
              <div class="content__bill__price_list__item">
                <p>Украшения</p>
                <p>{{ decoratinPrice }} тг</p>
              </div>
              <div class="content__bill__price_list__item">
                <p>Всего</p>
                <p>{{ totalPrice }} тг</p>
              </div>
            </div>
          </div>
          <div class="content__adress">
            <h1>Выбери откуда сможешь забрать свой заказ</h1>
            <h2>
              <img src="../assets/img/calculator/clock.png" alt="" /> Режим
              работы 10:00 - 22:00
            </h2>
            <div class="adress_one">
              <div
                @click.prevent="adressKabanbay"
                :class="[firstAdress ? 'label_selected' : 'label_disabled']"
              >
                <img
                  v-if="firstAdress"
                  src="../assets/img/calculator/radio-btn.png"
                />
                <img v-else src="../assets/img/calculator/radio-btn-dis.png" />
                <div class="location">
                  <p>
                    <span>Кабанбай батыра 58а,</span> <br />корпус 1 (ЖК EXPO
                    Boulevard-6)
                  </p>
                </div>
              </div>
            </div>
            <div class="adress_two">
              <div
                @click.prevent="adressAginbay"
                :class="[secondAdress ? 'label_selected' : 'label_disabled']"
              >
                <img
                  v-if="secondAdress"
                  src="../assets/img/calculator/radio-btn.png"
                />
                <img v-else src="../assets/img/calculator/radio-btn-dis.png" />
                <div class="location">
                  <p><span>Агыбай батыра 4,</span> <br />(возле набережной)</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <!-- success step -->
      <div v-if="step == 9" class="success">
        <h1>Заказ успешно оформлен</h1>
        <p>Спасибо за ваш заказ) Мы будем Вас ждать у нас</p>
        <img src="../assets/img/calculator/success.png" alt="" />
        <h3>
          <img src="../assets/img/calculator/clock.png" alt="" /> Режим работы
          10:00 - 22:00
        </h3>
      </div>
      <!-- buttons -->
      <div class="btns">
        <div
          @click.prevent="backStep"
          class="btns__prev"
          v-if="step <= 8 && step != 1"
        >
          <img src="../assets/img/calculator/back.png" alt="" />
          <p>шаг назад</p>
        </div>
        <button
          @click.prevent="passStep"
          class="btns__next"
          v-if="step != 1 && step < 7"
        >
          Пропустить шаг
        </button>
        <button
          class="btns__next_end"
          @click.prevent="passStep"
          v-if="step === 7"
        >
          всё!
        </button>
        <button
          @click.prevent="submitOrder"
          class="btns__next_end"
          v-if="step === 8"
        >
          отправить заказ
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Swiper, { Navigation } from "swiper";
Swiper.use([Navigation]);
export default {
  data: () => ({
    step: 1,
    trdelnik_type: "",
    pomazka_type: "",
    posypka_type: "",
    nachinka_type: "",
    iceCream_type: "",
    Topping_type: "",
    Decorations_type: "",
    Adress_type: "Кабанбай батыра 58а",
    // back step podsvetka start
    TraditionalConus: false,
    TraditionalSugar: false,
    PomazkaNuttela: false,
    PomazkaWhiteChocolade: false,
    PomazkaKaramel: false,
    PomazkaArahisPasta: false,

    PosipkaOreo: false,
    PosipkaArahis: false,
    PosipkaKorica: false,
    PosipkaCgecOreh: false,
    PosipkaKokos: false,
    PosipkaMindal: false,

    NachinkaBanana: false,
    NachinkaKiwi: false,
    NachinkaAnanas: false,
    NachinkaApelsin: false,
    NachinkaApple: false,
    NachinkaBerry: false,
    NachinkaMango: false,

    IceCreamSliv: false,
    IceCreamChokolade: false,
    IceCreamAssorty: false,
    IceCreamMilkShake: false,

    BananaTopping: false,
    ChokoladeTopping: false,
    BerryTopping: false,
    KaramelTopping: false,

    SnikersDecorations: false,
    RafaelloDecorations: false,
    OreoDecorations: false,
    // back step podsvetka end
    trdelnikPrice: 0,
    pomazkaPrice: 0,
    PosipkaPrice: 0,
    nachinkaPrice: 0,
    icePrice: 0,
    toppingPrice: 0,
    decoratinPrice: 0,
    firstAdress: true,
    secondAdress: false,
    swiperOptions: {
      spaceBetween: 20,
      slidesPerView: "auto",
      loop: true,
      navigation: {
        nextEl: ".swiper_btns__next",
        prevEl: ".swiper_btns__prev"
      }
    }
  }),
  computed: {
    totalPrice() {
      return (
        this.trdelnikPrice +
        this.pomazkaPrice +
        this.PosipkaPrice +
        this.nachinkaPrice +
        this.icePrice +
        this.toppingPrice +
        this.decoratinPrice
      );
    }
  },
  methods: {
    passStep() {
      this.step++;
    },
    backStep() {
      this.step--;
    },
    submitOrder() {
      this.step = 9;
      axios.post("http://eliks.kz/api/trdelnik-order/", {
        trdelnik_type: this.trdelnik_type,
        pomazka_type: this.pomazka_type,
        posypka_type: this.posypka_type,
        nachinka_type: this.nachinka_type,
        iceCream_type: this.iceCream_type,
        Topping_type: this.Topping_type,
        Decorations_type: this.Decorations_type,
        Adress_type: this.Adress_type
      });
    },
    adressKabanbay() {
      this.firstAdress = true;
      this.secondAdress = false;
      this.Adress_type = "Кабанбай батыра 58а";
    },
    adressAginbay() {
      this.firstAdress = false;
      this.secondAdress = true;
      this.Adress_type = "Агыбай батыра 4";
    },
    selectTraditionalType() {
      this.trdelnikPrice = 600;
      this.TraditionalConus = true;
      this.TraditionalSugar = false;
      this.trdelnik_type = "Традиционый - конус";
      this.step = 2;
    },
    selectSugarType() {
      this.trdelnikPrice = 650;
      this.TraditionalConus = false;
      this.TraditionalSugar = true;
      this.trdelnik_type = "с сахаром и корицей";
      this.step = 2;
    },
    selectNutella() {
      this.pomazkaPrice = 100;
      this.PomazkaNuttela = true;
      this.PomazkaWhiteChocolade = false;
      this.PomazkaKaramel = false;
      this.PomazkaArahisPasta = false;
      this.pomazka_type = "нутелла";
      this.step = 3;
    },
    selectWhiteCh() {
      this.pomazkaPrice = 100;
      this.PomazkaNuttela = false;
      this.PomazkaWhiteChocolade = true;
      this.PomazkaKaramel = false;
      this.PomazkaArahisPasta = false;
      this.pomazka_type = "бел.шоколад";
      this.step = 3;
    },
    selectKaramel() {
      this.pomazkaPrice = 100;
      this.PomazkaNuttela = false;
      this.PomazkaWhiteChocolade = false;
      this.PomazkaKaramel = true;
      this.PomazkaArahisPasta = false;
      this.pomazka_type = "карамель";
      this.step = 3;
    },
    selectArahPas() {
      this.pomazkaPrice = 100;
      this.PomazkaNuttela = false;
      this.PomazkaWhiteChocolade = false;
      this.PomazkaKaramel = false;
      this.PomazkaArahisPasta = true;
      this.pomazka_type = "арах. паста";
      this.step = 3;
    },
    selectOreo() {
      this.PosipkaPrice = 100;
      this.PosipkaOreo = true;
      this.PosipkaArahis = false;
      this.PosipkaKorica = false;
      this.PosipkaCgecOreh = false;
      this.PosipkaKokos = false;
      this.PosipkaMindal = false;
      this.posypka_type = "oreo";
      this.step = 4;
    },
    selectArahis() {
      this.PosipkaPrice = 100;
      this.PosipkaOreo = false;
      this.PosipkaArahis = true;
      this.PosipkaKorica = false;
      this.PosipkaCgecOreh = false;
      this.PosipkaKokos = false;
      this.PosipkaMindal = false;
      this.posypka_type = "арахис";
      this.step = 4;
    },
    selectKorica() {
      this.PosipkaPrice = 100;
      this.PosipkaOreo = false;
      this.PosipkaArahis = false;
      this.PosipkaKorica = true;
      this.PosipkaCgecOreh = false;
      this.PosipkaKokos = false;
      this.PosipkaMindal = false;
      this.posypka_type = "корица";
      this.step = 4;
    },
    selectGrecOreh() {
      this.PosipkaPrice = 100;
      this.PosipkaOreo = false;
      this.PosipkaArahis = false;
      this.PosipkaKorica = false;
      this.PosipkaCgecOreh = true;
      this.PosipkaKokos = false;
      this.PosipkaMindal = false;
      this.posypka_type = "грецкий орех";
      this.step = 4;
    },
    selectKokos() {
      this.PosipkaPrice = 100;
      this.PosipkaOreo = false;
      this.PosipkaArahis = false;
      this.PosipkaKorica = false;
      this.PosipkaCgecOreh = false;
      this.PosipkaKokos = true;
      this.PosipkaMindal = false;
      this.posypka_type = "кокос";
      this.step = 4;
    },
    selectMindal() {
      this.PosipkaPrice = 100;
      this.PosipkaOreo = false;
      this.PosipkaArahis = false;
      this.PosipkaKorica = false;
      this.PosipkaCgecOreh = false;
      this.PosipkaKokos = false;
      this.PosipkaMindal = true;
      this.posypka_type = "миндаль";
      this.step = 4;
    },
    posypkaKiwi() {
      this.nachinkaPrice = 400;
      this.NachinkaKiwi = true;
      this.NachinkaAnanas = false;
      this.NachinkaApelsin = false;
      this.NachinkaApple = false;
      this.NachinkaBerry = false;
      this.NachinkaMango = false;
      this.NachinkaBanana = false;
      this.nachinka_type = "киви";
      this.step = 5;
    },
    posypkaAnanas() {
      this.nachinkaPrice = 550;
      this.NachinkaKiwi = false;
      this.NachinkaAnanas = true;
      this.NachinkaApelsin = false;
      this.NachinkaApple = false;
      this.NachinkaBerry = false;
      this.NachinkaMango = false;
      this.NachinkaBanana = false;
      this.nachinka_type = "ананас";
      this.step = 5;
    },
    posypkaApelsin() {
      this.nachinkaPrice = 450;
      this.NachinkaKiwi = false;
      this.NachinkaAnanas = false;
      this.NachinkaApelsin = true;
      this.NachinkaApple = false;
      this.NachinkaBerry = false;
      this.NachinkaMango = false;
      this.NachinkaBanana = false;
      this.nachinka_type = "апельсин";
      this.step = 5;
    },
    posypkaApple() {
      this.nachinkaPrice = 350;
      this.NachinkaKiwi = false;
      this.NachinkaAnanas = false;
      this.NachinkaApelsin = false;
      this.NachinkaApple = true;
      this.NachinkaBerry = false;
      this.NachinkaMango = false;
      this.NachinkaBanana = false;
      this.nachinka_type = "яблоко";
      this.step = 5;
    },
    posypkaBerry() {
      this.nachinkaPrice = 650;
      this.NachinkaKiwi = false;
      this.NachinkaAnanas = false;
      this.NachinkaApelsin = false;
      this.NachinkaApple = false;
      this.NachinkaBerry = true;
      this.NachinkaMango = false;
      this.NachinkaBanana = false;
      this.nachinka_type = "ягоды";
      this.step = 5;
    },
    posypkaMango() {
      this.nachinkaPrice = 650;
      this.NachinkaKiwi = false;
      this.NachinkaAnanas = false;
      this.NachinkaApelsin = false;
      this.NachinkaApple = false;
      this.NachinkaBerry = false;
      this.NachinkaMango = true;
      this.NachinkaBanana = false;
      this.nachinka_type = "манго";
      this.step = 5;
    },
    posypkaBanana() {
      this.nachinkaPrice = 400;
      this.NachinkaKiwi = false;
      this.NachinkaAnanas = false;
      this.NachinkaApelsin = false;
      this.NachinkaApple = false;
      this.NachinkaBerry = false;
      this.NachinkaMango = false;
      this.NachinkaBanana = true;
      this.nachinka_type = "банан";
      this.step = 5;
    },
    iceSlivki() {
      this.icePrice = 390;
      this.IceCreamSliv = true;
      this.IceCreamChokolade = false;
      this.IceCreamAssorty = false;
      this.IceCreamMilkShake = false;
      this.iceCream_type = "сливочное";
      this.step = 6;
    },
    iceChokolade() {
      this.icePrice = 390;
      this.IceCreamSliv = false;
      this.IceCreamChokolade = true;
      this.IceCreamAssorty = false;
      this.IceCreamMilkShake = false;
      this.iceCream_type = "шоколадное";
      this.step = 6;
    },
    iceAssorty() {
      this.icePrice = 390;
      this.IceCreamSliv = false;
      this.IceCreamChokolade = false;
      this.IceCreamAssorty = true;
      this.IceCreamMilkShake = false;
      this.iceCream_type = "смешанное";
      this.step = 6;
    },
    iceShake() {
      this.icePrice = 390;
      this.IceCreamSliv = false;
      this.IceCreamChokolade = false;
      this.IceCreamAssorty = false;
      this.IceCreamMilkShake = true;
      this.iceCream_type = "взбитые сливки";
      this.step = 6;
    },
    toppingBanana() {
      this.toppingPrice = 50;
      this.BananaTopping = true;
      this.ChokoladeTopping = false;
      this.BerryTopping = false;
      this.KaramelTopping = false;
      this.Topping_type = "банан";
      this.step = 7;
    },
    toppingChokolad() {
      this.toppingPrice = 50;
      this.BananaTopping = false;
      this.ChokoladeTopping = true;
      this.BerryTopping = false;
      this.KaramelTopping = false;
      this.Topping_type = "шоколад";
      this.step = 7;
    },
    toppingBerry() {
      this.toppingPrice = 50;
      this.BananaTopping = false;
      this.ChokoladeTopping = false;
      this.BerryTopping = true;
      this.KaramelTopping = false;
      this.Topping_type = "ягоды";
      this.step = 7;
    },
    toppingKaramel() {
      this.toppingPrice = 50;
      this.BananaTopping = false;
      this.ChokoladeTopping = false;
      this.BerryTopping = false;
      this.KaramelTopping = true;
      this.Topping_type = "карамель";
      this.step = 7;
    },
    decorationsSnikecrs() {
      this.decoratinPrice = 390;
      this.SnikersDecorations = true;
      this.RafaelloDecorations = false;
      this.OreoDecorations = false;
      this.Decorations_type = "snickers";
      this.step = 8;
    },
    decorationsRafaello() {
      this.decoratinPrice = 390;
      this.SnikersDecorations = false;
      this.RafaelloDecorations = true;
      this.OreoDecorations = false;
      this.Decorations_type = "rafaello";
      this.step = 8;
    },
    decorationsOreo() {
      this.decoratinPrice = 390;
      this.SnikersDecorations = false;
      this.RafaelloDecorations = false;
      this.OreoDecorations = true;
      this.Decorations_type = "oreo";
      this.step = 8;
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/style/fonts.scss";
@media all and (max-width: 768px) {
  .title_calculator {
    font-size: 14px !important;
    line-height: 17px !important;
    margin-top: 20px !important;
  }
  .click_description {
    margin-top: 40px !important;
    p {
      font-size: 14px !important;
      line-height: 17px !important;
    }
  }
  .calculator {
    background: none !important;
    // height: 586px !important;
    height: auto !important;
    padding-top: 40px !important;
  }
  .collect_candy {
    &__title {
      font-size: 28px !important;
      line-height: 34px !important;
    }
    .step {
      font-size: 14px !important;
      line-height: 17px !important;
      text-align: center !important;
    }
  }
  .box {
    width: 154px !important;
    height: 270px !important;
    img {
      width: 88px !important;
      height: 160px !important;
    }
    h1 {
      font-size: 14px !important;
      line-height: 17px !important;
    }
    .price {
      p {
        font-size: 14px !important;
        line-height: 17px !important;
      }
      img {
        width: 7px !important;
        height: 8px !important;
      }
    }
  }
  .btns {
    display: flex !important;
    flex-direction: row !important;
    align-items: center !important;
    justify-content: space-between !important;
    width: 100% !important;
    padding: 0 20px !important;
    &__prev {
      margin-bottom: 0 !important;
    }
    &__next {
      width: 164px !important;
      overflow: hidden;
      &_end {
        width: 155px !important;
        height: 50px !important;
      }
    }
  }
  .content_two {
    height: 331px !important;
    .pomazka {
      display: grid !important;
      grid-template-columns: repeat(2, 1fr) !important;
      grid-column-gap: 9px !important;
      grid-row-gap: 20px !important;
      &__box {
        width: 153px !important;
        height: 127px !important;
        h2 {
          font-size: 14px !important;
          line-height: 17px !important;
        }
        img {
          width: 80px !important;
          height: 80px !important;
        }
      }
    }
  }
  .content_three {
    height: 331px !important;
    .posypka {
      display: grid !important;
      grid-template-columns: repeat(3, 1fr) !important;
      grid-column-gap: 8px !important;
      grid-row-gap: 20px !important;
      &__box {
        width: 100px !important;
        height: 127px !important;
        overflow: hidden !important;
        h2 {
          font-size: 14px !important;
          line-height: 17px !important;
        }
        img {
          width: 80px !important;
          height: 80px !important;
        }
      }
    }
  }
  .content_four {
    .swiper-container {
      width: 350px !important;
    }
    height: 331px !important;
    h1 {
      font-size: 14px !important;
      line-height: 17px !important;
      margin-top: 20px !important;
    }
    .swiper-slide {
      width: auto !important;
      .slider_content {
        width: 144px !important;
        padding-top: 25px !important;
        img {
          width: 100px !important;
          height: 100px !important;
        }
        .price {
          img {
            width: 10px !important;
            height: 12px !important;
          }
        }
      }
    }
    .swiper_btns__prev {
      display: none !important;
    }
    .swiper_btns__next {
      display: none !important;
    }
  }
  .content_five {
    height: 331px !important;
    .ice_cream {
      grid-template-columns: repeat(2, 1fr) !important;
      grid-row-gap: 30px !important;
      grid-column-gap: 9px !important;
      &__box {
        width: 153px !important;
        height: 127px !important;
        margin-top: 0 !important;
        h1 {
          font-size: 14px !important;
          line-height: 17px !important;
        }
        img {
          width: 100px !important;
          height: 100px !important;
          top: -20px !important;
        }
      }
    }
  }
  .content_six {
    height: 331px !important;
    .topping {
      grid-template-columns: repeat(2, 1fr) !important;
      grid-row-gap: 20px !important;
      grid-column-gap: 9px !important;
      &__box {
        width: 153px !important;
        height: 127px !important;
        img {
          width: 80px !important;
          height: 80px !important;
        }
      }
    }
  }
  .content_seven {
    height: 331px !important;
    .decorations {
      display: flex !important;
      flex-wrap: wrap !important;
      justify-content: center !important;
      grid-row-gap: 0px !important;
      grid-column-gap: 0px !important;
      &__box {
        width: 153px !important;
        height: 127px !important;
        margin-bottom: 20px !important;
        margin-left: 5px !important;
        margin-right: 5px !important;
        img {
          width: 80px !important;
          height: 80px !important;
        }
      }
    }
  }
  .pay_bill {
    .content {
      display: flex !important;
      flex-direction: column !important;
      align-items: center !important;
      justify-content: flex-start !important;
      margin-top: 0 !important;
      &__adress {
        margin-left: 0 !important;
        padding: 0 20px !important;
        display: flex !important;
        flex-direction: column !important;
        align-items: center !important;
        justify-content: flex-start !important;
        .label_selected {
          width: 315px !important;
          height: 58px !important;
          .location {
            p {
              font-size: 14px !important;
              line-height: 17px !important;
            }
          }
        }
        .label_disabled {
          width: 315px !important;
          height: 58px !important;
          .location {
            p {
              font-size: 14px !important;
              line-height: 17px !important;
            }
          }
        }
        .adress_one {
          margin-top: 20px !important;
        }
      }
    }
  }
  .success {
    text-align: center !important;
    img {
      width: 344px !important;
      height: 178px !important;
    }
    h3 {
      display: none !important;
    }
  }
}
.calculator {
  background: url("../assets/img/calculator/bg.png");
  background-size: 100% 100%;
  height: 747px;
}
.collect_candy {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-bottom: 60px;
  &__title {
    @include medium;
    font-size: 48px;
    line-height: 59px;
    color: #123429;
  }
  .step {
    @include medium;
    font-size: 18px;
    line-height: 22px;
    color: #123429;
    margin-top: 20px;
    .color {
      color: #fd0bce;
    }
  }
}
.title_calculator {
  @include medium;
  font-size: 26px;
  line-height: 32px;
  margin-top: 60px;
  margin-bottom: 20px;
  color: #123429;
  text-align: center;
  span {
    color: #fd0bce;
    margin-left: 9px;
    margin-right: 2px;
  }
}
.price {
  display: flex;
  align-items: center;
  p {
    @include normal;
    font-size: 18px;
    line-height: 22px;
    text-transform: uppercase;
    margin-right: 5px;
    color: #fd0bce;
  }
}
.content_one {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 25px;
  .boxes {
    display: flex;
    .box {
      width: 347px;
      height: 344px;
      background: #ffffff;
      box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.25);
      border-radius: 16px;
      display: flex;
      flex-direction: column;
      align-items: center;
      margin: 0 10px;
      cursor: pointer;
      h1 {
        @include medium;
        font-size: 18px;
        line-height: 22px;
        text-align: center;
        text-transform: uppercase;
        margin: 10px 0;
        color: #123429;
      }
    }
  }
  .click_description {
    display: flex;
    align-items: center;
    margin-top: 96px;
    p {
      @include medium;
      font-size: 18px;
      line-height: 22px;
      margin-left: 16px;
      color: #123429;
    }
  }
}
.content_two {
  height: 375px;
  .pomazka {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-column-gap: 20px;
    &__box {
      display: flex;
      flex-direction: column;
      align-items: center;
      width: 163px;
      height: 211px;
      background: #ffffff;
      box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.25);
      border-radius: 16px;
      cursor: pointer;
      h2 {
        @include medium;
        font-size: 18px;
        line-height: 22px;
        text-align: center;
        text-transform: uppercase;
        margin-top: 9px;
        color: #123429;
      }
    }
  }
}
.content_three {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 375px;
  .posypka {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    grid-column-gap: 20px;
    &__box {
      width: 163px;
      height: 211px;
      background: #ffffff;
      box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.25);
      border-radius: 16px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: flex-end;
      cursor: pointer;
      h2 {
        margin-top: 12px;
        margin-bottom: 20px;
        font-size: 18px;
        line-height: 22px;
        @include medium;
        text-align: center;
        text-transform: uppercase;
        color: #123429;
      }
    }
  }
}
.content_four {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 375px;
  &__swiper {
    display: flex;
    align-items: center;
  }
  h1 {
    @include medium;
    font-size: 26px;
    line-height: 32px;
    color: #123429;
    margin-top: 50px;
    margin-bottom: 20px;
  }
  .swiper-container {
    width: 800px;
    padding: 20px 0;
    .swiper-slide {
      display: flex;
      justify-content: center;
      width: auto;
      .slider_content {
        cursor: pointer;
        padding-top: 10px;
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 163px;
        height: 233px;
        background: #ffffff;
        box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.25);
        border-radius: 16px;
        h1 {
          margin: 10px 0;
          font-size: 18px;
          line-height: 22px;
          @include medium;
          text-align: center;
          text-transform: uppercase;
          color: #123429;
        }
      }
    }
  }
  .swiper_btns__prev {
    background: url("../assets/img/calculator/swiper/arrow.png");
    background-size: 100% 100%;
    cursor: pointer;
    transform: rotate(180deg);
    margin-right: 25px;
    height: 40px;
    width: 21.6px;
  }
  .swiper_btns__next {
    background: url("../assets/img/calculator/swiper/arrow.png");
    background-size: 100% 100%;
    cursor: pointer;
    margin-left: 25px;
    height: 40px;
    width: 21.6px;
  }
}
.content_five {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 375px;
  .ice_cream {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-column-gap: 20px;
    &__box {
      cursor: pointer;
      position: relative;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: flex-end;
      padding-bottom: 20px;
      background: #ffffff;
      box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.25);
      border-radius: 16px;
      width: 255px;
      height: 140px;
      margin-top: 117px;
      img {
        cursor: pointer;
        position: absolute;
        top: -116px;
      }
      h1 {
        @include medium;
        font-size: 18px;
        line-height: 22px;
        text-align: center;
        text-transform: uppercase;
        color: #123429;
      }
    }
  }
}
.content_six {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 375px;
  .topping {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-column-gap: 20px;
    &__box {
      cursor: pointer;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: flex-end;
      padding-bottom: 20px;
      width: 163px;
      height: 211px;
      background: #ffffff;
      box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.25);
      border-radius: 16px;
      h1 {
        font-size: 18px;
        line-height: 22px;
        @include medium;
        text-align: center;
        text-transform: uppercase;
        color: #123429;
      }
    }
  }
}
.content_seven {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 375px;
  .decorations {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-column-gap: 20px;
    &__box {
      cursor: pointer;
      width: 164px;
      height: 211px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: flex-end;
      padding-bottom: 20px;
      background: #ffffff;
      box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.25);
      border-radius: 16px;
      h1 {
        font-size: 18px;
        line-height: 22px;
        @include medium;
        text-align: center;
        text-transform: uppercase;
        color: #123429;
      }
    }
  }
}
.pay_bill {
  display: flex;
  flex-direction: column;
  align-items: center;
  .content {
    display: flex;
    align-items: flex-start;
    margin-top: 20px;
    &__bill {
      background: url("../assets/img/calculator/pay-bill.png");
      background-size: 100% 100%;
      width: 292px;
      height: 421px;
      display: flex;
      justify-content: center;
      align-items: flex-start;
      &__price_list {
        margin-top: 111px;
        &__item {
          display: flex;
          justify-content: space-between;
          width: 200px;
          margin-bottom: 4px;
          p {
            font-size: 12px;
            line-height: 15px;
            @include medium;
            color: #123429;
          }
        }
        &__item:last-of-type {
          margin-top: 40px;
        }
      }
    }
    &__adress {
      margin-left: 103px;
      h1 {
        @include medium;
        font-size: 18px;
        line-height: 22px;
        color: #123429;
        margin-bottom: 15px;
      }
      h2 {
        @include medium;
        display: flex;
        align-items: center;
        font-size: 18px;
        line-height: 22px;
        color: #123429;
        opacity: 0.3;
        img {
          margin-right: 8px;
        }
      }
      .adress_one {
        margin-top: 40px;
      }
      .adress_two {
        margin-top: 20px;
      }
    }
  }
}
.success {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-top: 80px;
  h1 {
    @include medium;
    font-size: 26px;
    line-height: 32px;
    text-align: center;
    color: #fd0bce;
    margin-bottom: 20px;
  }
  p {
    @include medium;
    font-size: 18px;
    line-height: 22px;
    margin-bottom: 40px;
    color: #123429;
  }
  h3 {
    display: flex;
    align-items: center;
    margin-top: 13px;
    @include medium;
    font-size: 18px;
    line-height: 22px;
    color: #123429;
    opacity: 0.3;
    img {
      margin-right: 8px;
      opacity: 1;
    }
  }
}
.btns {
  margin-top: 50px;
  display: flex;
  flex-direction: column;
  align-items: center;
  &__prev {
    display: flex;
    align-items: center;
    margin-bottom: 20px;
    cursor: pointer;
    p {
      @include medium;
      font-size: 18px;
      line-height: 22px;
      text-transform: uppercase;
      margin-left: 11px;
      color: #123429;
      opacity: 0.5;
    }
  }
  &__next {
    cursor: pointer;
    outline: none;
    border: none;
    background: #7ddecd;
    width: 369px;
    height: 50px;
    border-radius: 16px;
    font-size: 18px;
    line-height: 22px;
    @include medium;
    color: #ffffff;
  }
  &__next_end {
    background: #fd0bce;
    cursor: pointer;
    outline: none;
    border: none;
    width: 369px;
    height: 50px;
    border-radius: 16px;
    font-size: 18px;
    line-height: 22px;
    @include medium;
    color: #ffffff;
  }
}
.label_selected {
  display: flex;
  align-items: center;
  width: 382px;
  height: 68px;
  background: rgba(125, 222, 205, 0.2);
  border: 1px solid #fd0bce;
  box-sizing: border-box;
  border-radius: 16px;
  padding: 12px 16px;
  cursor: pointer;
  .location {
    margin-left: 16px;
    p {
      @include medium;
      font-size: 18px;
      line-height: 22px;
      color: #123429;
      span {
        color: #fd0bce;
      }
    }
  }
}
.label_disabled {
  display: flex;
  align-items: center;
  width: 382px;
  height: 68px;
  padding: 12px 16px;
  cursor: pointer;
  .location {
    margin-left: 16px;
    p {
      @include medium;
      font-size: 18px;
      line-height: 22px;
      color: #123429;
      span {
        color: #fd0bce;
      }
    }
  }
}
.selectedBOX {
  filter: grayscale(100%);
}
</style>
