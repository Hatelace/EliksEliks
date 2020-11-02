<template>
  <div class="main" id="catalog">
    <h1 class="title">Католог товаров</h1>
    <div class="navigation">
      <div class="navigation__items" @click.prevent="showTrdelniki">
        <a :style="[!isTrdelnik ? {} : { color: '#fd0bce', opacity: 1 }]"
          >Трдельники</a
        >
        <div
          class="image"
          :style="[isTrdelnik ? { background: 'rgba(98, 213, 192, 0.8)' } : {}]"
        >
          <img src="../assets/img/catalog/1.png" />
        </div>
      </div>
      <div class="navigation__items" @click.prevent="showChimni">
        <a :style="[!isChimni ? {} : { color: '#fd0bce', opacity: 1 }]"
          >Чимни-доги</a
        >
        <div
          class="image"
          :style="[isChimni ? { background: 'rgba(98, 213, 192, 0.8)' } : {}]"
        >
          <img src="../assets/img/catalog/2.png" />
        </div>
      </div>
      <div class="navigation__items" @click.prevent="showSandwich">
        <a :style="[!isSandwich ? {} : { color: '#fd0bce', opacity: 1 }]"
          >Сэндвичи</a
        >
        <div
          class="image"
          :style="[isSandwich ? { background: 'rgba(98, 213, 192, 0.8)' } : {}]"
        >
          <img src="../assets/img/catalog/4.png" />
        </div>
      </div>
      <div class="navigation__items" @click.prevent="showDeserts">
        <a :style="[!isDesert ? {} : { color: '#fd0bce', opacity: 1 }]"
          >Десерты</a
        >
        <div
          class="image"
          :style="[isDesert ? { background: 'rgba(98, 213, 192, 0.8)' } : {}]"
        >
          <img src="../assets/img/catalog/5.png" />
        </div>
      </div>
      <div class="navigation__items" @click.prevent="showDrinks">
        <a :style="[!isDrinks ? {} : { color: '#fd0bce', opacity: 1 }]"
          >Напитки</a
        >
        <div
          class="image"
          :style="[isDrinks ? { background: 'rgba(98, 213, 192, 0.8)' } : {}]"
        >
          <img src="../assets/img/catalog/3.png" />
        </div>
      </div>
      <div class="navigation__items" @click.prevent="showKruasan">
        <a :style="[!isKruasan ? {} : { color: '#fd0bce', opacity: 1 }]"
          >Круассаны</a
        >
        <div
          class="image"
          :style="[isKruasan ? { background: 'rgba(98, 213, 192, 0.8)' } : {}]"
        >
          <img src="../assets/img/catalog/6.png" />
        </div>
      </div>
    </div>

    <div v-if="isTrdelnik" class="catalog">
      <div
        class="cart mobile_cart_trdelnik"
        v-for="trdelnik in trdelnikCatalog"
        :key="trdelnik.id"
        :style="[
          indexMassive.includes(trdelnik.id)
            ? { filter: 'grayscale(100%)' }
            : {}
        ]"
      >
        <img class="image" :src="'http://eliks.kz' + trdelnik.image" />
        <h1 class="cart_title">{{ trdelnik.title }}</h1>
        <div class="price">
          <p>{{ trdelnik.price }}</p>
          <img src="../assets/img/catalog/tenge.png" />
        </div>
        <button
          v-if="!indexMassive.includes(trdelnik.id)"
          class="buy_ice_cream"
          @click.prevent="buyTrdelnik(trdelnik)"
        >
          Купить
        </button>
        <button
          v-else
          class="buy_ice_cream"
          @click.prevent="sellTrdelnik(trdelnik)"
        >
          Заказ принят
          <img src="../assets/img/catalog/check.png" />
        </button>
      </div>
    </div>

    <div v-else-if="isChimni" class="catalog chimni_mobile_catalog">
      <div
        class="cart mobile_cart_chimni"
        v-for="chimni in chimniCatalog"
        :key="chimni.id"
        :style="[
          chimniMassive.includes(chimni.id) ? { filter: 'grayscale(100%)' } : {}
        ]"
      >
        <img
          class="image chimni_mobile_image"
          :src="'http://eliks.kz' + chimni.image"
        />
        <h1 class="cart_title">{{ chimni.title }}</h1>
        <div class="price">
          <p>{{ chimni.price }}</p>
          <img src="../assets/img/catalog/tenge.png" />
        </div>
        <button
          v-if="!chimniMassive.includes(chimni.id)"
          class="buy_ice_cream"
          @click.prevent="buyChimni(chimni)"
        >
          Купить
        </button>
        <button
          v-else
          class="buy_ice_cream"
          @click.prevent="sellChimni(chimni)"
        >
          Заказ принят
          <img src="../assets/img/catalog/check.png" />
        </button>
      </div>
    </div>

    <div v-else-if="isSandwich" class="catalog sandwich_mobile_catalog">
      <div
        class="cart mobile_cart_sandwich"
        v-for="sandwich in sandwichCatalog"
        :key="sandwich.id"
        :style="[
          sandwichMassive.includes(sandwich.id)
            ? { filter: 'grayscale(100%)' }
            : {}
        ]"
      >
        <img
          class="image sandwich_mobile_image"
          :src="'http://eliks.kz' + sandwich.image"
          style="top: -107px"
        />
        <h1 class="cart_title">{{ sandwich.title }}</h1>
        <div class="price">
          <p>{{ sandwich.price }}</p>
          <img src="../assets/img/catalog/tenge.png" />
        </div>
        <button
          v-if="!sandwichMassive.includes(sandwich.id)"
          class="buy_ice_cream"
          @click.prevent="buySandwich(sandwich)"
        >
          Купить
        </button>
        <button
          v-else
          class="buy_ice_cream"
          @click.prevent="sellSandwich(sandwich)"
        >
          Заказ принят
          <img src="../assets/img/catalog/check.png" />
        </button>
      </div>
    </div>

    <div
      v-else-if="isDesert"
      :style="[
        isDesert ? { 'margin-top': '204px', 'grid-row-gap': '94px' } : {}
      ]"
      class="catalog mobile_catalog_desert"
    >
      <div
        class="cartDesert mobile_cart_desertt"
        v-for="deserts in desertsCatalog"
        :key="deserts.id"
        :style="[
          desertMassive.includes(deserts.id)
            ? { filter: 'grayscale(100%)' }
            : {}
        ]"
      >
        <img
          class="image"
          :src="'http://eliks.kz' + deserts.image"
          style="top: -72px"
        />
        <h1 class="cart_title mobile_cart_desert">{{ deserts.title }}</h1>
        <div class="price">
          <p>{{ deserts.price }}</p>
          <img src="../assets/img/catalog/tenge.png" />
        </div>
        <button
          v-if="!desertMassive.includes(deserts.id)"
          class="buy_ice_cream"
          @click.prevent="buyDesert(deserts)"
        >
          Купить
        </button>
        <button
          v-else
          class="buy_ice_cream"
          @click.prevent="sellDesert(deserts)"
        >
          Заказ принят
          <img src="../assets/img/catalog/check.png" />
        </button>
      </div>
    </div>

    <div
      v-else-if="isDrinks"
      :style="[
        isDrinks
          ? {
              'margin-top': '204px',
              'grid-row-gap': '94px',
              'grid-template-columns': 'repeat(6, 1fr)'
            }
          : {}
      ]"
      class="catalog mobile_drinks_catalog"
    >
      <div
        class="cartDrinks mobile_cart_drinks"
        v-for="drinks in drinksCatalog"
        :key="drinks.id"
        :style="[
          drinksMassive.includes(drinks.id) ? { filter: 'grayscale(100%)' } : {}
        ]"
      >
        <img
          class="image"
          :src="'http://eliks.kz' + drinks.image"
          style="top: -94px"
        />
        <h1
          class="cart_title"
          :style="[isDrinks ? { 'margin-bottom': '5px' } : {}]"
        >
          {{ drinks.title }}
        </h1>
        <p class="litres">{{ drinks.litres }} мл</p>
        <div class="price">
          <p>{{ drinks.price }}</p>
          <img src="../assets/img/catalog/tenge.png" />
        </div>
        <button
          v-if="!drinksMassive.includes(drinks.id)"
          class="buy_ice_cream"
          @click.prevent="buyDrinks(drinks)"
          :style="[isDrinks ? { width: '143px', height: '40px' } : {}]"
        >
          Купить
        </button>
        <button
          v-else
          class="buy_ice_cream"
          :style="[
            isDrinks
              ? { width: '143px', height: '40px', 'font-size': '16px' }
              : {}
          ]"
          @click.prevent="sellDrinks(drinks)"
        >
          Заказ принят
          <img src="../assets/img/catalog/check.png" />
        </button>
      </div>
    </div>
    <div
      v-else-if="isKruasan"
      :style="[
        isKruasan
          ? {
              'margin-top': '204px',
              'grid-row-gap': '94px',
              'grid-template-columns': 'repeat(6, 1fr)'
            }
          : {}
      ]"
      class="catalog mobile_drinks_catalog"
    >
      <div
        class="cartDrinks mobile_cart_drinks"
        v-for="kruasan in kruasanCatalog"
        :key="kruasan.id"
        :style="[
          drinksMassive.includes(kruasan.id)
            ? { filter: 'grayscale(100%)' }
            : {}
        ]"
      >
        <img
          class="image"
          :src="'http://eliks.kz' + drinks.image"
          style="top: -94px"
        />
        <h1
          class="cart_title"
          :style="[isDrinks ? { 'margin-bottom': '5px' } : {}]"
        >
          {{ drinks.title }}
        </h1>
        <p class="litres">{{ drinks.litres }} мл</p>
        <div class="price">
          <p>{{ drinks.price }}</p>
          <img src="../assets/img/catalog/tenge.png" />
        </div>
        <button
          v-if="!drinksMassive.includes(drinks.id)"
          class="buy_ice_cream"
          @click.prevent="buyDrinks(drinks)"
          :style="[isDrinks ? { width: '143px', height: '40px' } : {}]"
        >
          Купить
        </button>
        <button
          v-else
          class="buy_ice_cream"
          :style="[
            isDrinks
              ? { width: '143px', height: '40px', 'font-size': '16px' }
              : {}
          ]"
          @click.prevent="sellDrinks(drinks)"
        >
          Заказ принят
          <img src="../assets/img/catalog/check.png" />
        </button>
      </div>
    </div>

    <div v-if="isCart" class="fixed_div">
      <div v-if="step === 1" class="card_order">
        <img
          class="close"
          src="../assets/img/catalog/close.png"
          @click.prevent="closeCart"
        />
        <h1 class="card_order__title">Проверь свой заказ</h1>
        <div class="card_order__content">
          <div class="bill">
            <div class="bill__content" v-for="trd in TRarr" :key="trd.id">
              <p class="bill__content__title">{{ trd.title }}</p>
              <p class="bill__content__price">{{ trd.price }}</p>
            </div>
            <div class="bill__content" v-for="Chi in CHarr" :key="Chi.id">
              <p class="bill__content__title">{{ Chi.title }}</p>
              <p class="bill__content__price">{{ Chi.price }}</p>
            </div>
            <div class="bill__content" v-for="sand in SDarr" :key="sand.id">
              <p class="bill__content__title">{{ sand.title }}</p>
              <p class="bill__content__price">{{ sand.price }}</p>
            </div>
            <div class="bill__content" v-for="desr in DSarr" :key="desr.id">
              <p class="bill__content__title">{{ desr.title }}</p>
              <p class="bill__content__price">{{ desr.price }}</p>
            </div>
            <div class="bill__content" v-for="drin in DRarr" :key="drin.id">
              <p class="bill__content__title">{{ drin.title }}</p>
              <p class="bill__content__price">{{ drin.price }}</p>
            </div>
            <div class="bill__total">
              <p>Всего</p>
              <p>{{ trPrice + chPrice + sdPrice + dsPrice + drPrice }} тг</p>
            </div>
          </div>
          <div class="adress">
            <h1 class="adress__title">
              Выбери откуда сможешь <b>забрать свой</b> <br />
              заказ
            </h1>
            <div class="adress__work_time">
              <img src="../assets/img/calculator/clock.png" />
              <p>Режим работы 10:00 - 22:00</p>
            </div>
            <div
              @click.prevent="selectKabanbay"
              class="adress__kabanbay"
              :style="[
                KabanbayAdress
                  ? {
                      border: '1px solid #FD0BCE',
                      background: 'rgba(125, 222, 205, 0.2)'
                    }
                  : { opacity: 0.3 }
              ]"
            >
              <img src="../assets/img/calculator/radio-btn.png" />
              <p>
                <span>Кабанбай батыра 58а,</span><br />корпус 1 (ЖК EXPO
                Boulevard-6)
              </p>
            </div>
            <div
              @click.prevent="selectAgybay"
              class="adress__kabanbay adress__agybay"
              :style="[
                AgybayAdress
                  ? {
                      border: '1px solid #FD0BCE',
                      background: 'rgba(125, 222, 205, 0.2)'
                    }
                  : { opacity: 0.3 }
              ]"
            >
              <img src="../assets/img/calculator/radio-btn.png" />
              <p><span>Агыбай батыра 4</span><br />(возле набережной)</p>
            </div>
          </div>
        </div>
        <div class="card_order__bottom_btns">
          <div
            class="card_order__bottom_btns__back"
            @click.prevent="addMoreToCart"
          >
            <img src="../assets/img/calculator/back.png" />
            <p>Добавить еще товаров</p>
          </div>
          <div @click.prevent="nextStep" class="card_order__bottom_btns__next">
            <p>Дальше</p>
            <img src="../assets/img/calculator/next.png" />
          </div>
        </div>
      </div>
      <div v-if="step === 2" class="register_girl">
        <img
          class="close"
          @click.prevent="closeCart"
          src="../assets/img/catalog/close.png"
        />
        <h1>Заполните данные</h1>
        <div class="form">
          <form>
            <label for="name">Ваше Имя</label>
            <input v-model="name" type="text" placeholder="Ваше Имя" />
            <label for="name">Ваш номер телефона</label>
            <input v-model="mobile" type="text" placeholder="+7" />
          </form>
          <div>
            <!-- empty for verstka -->
          </div>
        </div>
        <div class="register_girl__girl_bg">
          <!-- girl background position absolute -->
        </div>
        <div class="next_prev_btns">
          <div class="next_prev_btns__back" @click.prevent="goBack">
            <img src="../assets/img/calculator/back.png" />
            <p>НАзад</p>
          </div>
          <div class="next_prev_btns__submit" @click.prevent="nextStep">
            <p>Дальше</p>
            <img src="../assets/img/calculator/next.png" />
          </div>
        </div>
      </div>
      <div v-else-if="step === 3" class="final_man">
        <img
          class="close"
          src="../assets/img/catalog/close.png"
          @click.prevent="closeCart"
        />
        <h1>Заказ успешно оформлен</h1>
        <h2>Спасибо за ваш заказ) Мы будем <b>Вас ждать у нас</b></h2>
        <img src="../assets/img/calculator/success.png" />
        <div class="finish" @click.prevent="closeCart">
          <p>Закрыть</p>
        </div>
      </div>
    </div>
    <transition name="popUpTransition">
      <div class="popup" v-if="showPopup">
        <p class="popup__text">
          Количество товара уточняется у менеджера по телефону
        </p>
      </div>
    </transition>
    <div class="card" @click.prevent="openCart">
      <transition name="card_animation">
        <h4 v-if="goodsAmount">Перейти в корзину</h4>
      </transition>
      <transition name="card_animation">
        <h4 v-if="!goodsAmount">Добавьте товары</h4>
      </transition>
      <p>Добавлено товаров({{ goodsAmount }})</p>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data: () => ({
    step: 1,
    isTrdelnik: true,
    isChimni: false,
    isSandwich: false,
    isDesert: false,
    isDrinks: false,
    isKruasan: false,
    KabanbayAdress: true,
    AgybayAdress: false,
    trdelnikCatalog: [],
    chimniCatalog: [],
    sandwichCatalog: [],
    desertsCatalog: [],
    drinksCatalog: [],
    kruasanCatalog: [],
    indexMassive: [],
    chimniMassive: [],
    sandwichMassive: [],
    desertMassive: [],
    drinksMassive: [],
    kruasanMassive: [],
    TRarr: [],
    CHarr: [],
    SDarr: [],
    DSarr: [],
    DRarr: [],
    isCart: false,
    trPrice: 0,
    chPrice: 0,
    sdPrice: 0,
    dsPrice: 0,
    drPrice: 0,
    // data send to back
    Fromadress: "Кабанбай батыра 58а",
    name: "",
    mobile: "",
    Fromorder: "",
    // POP UP
    showPopup: false,
    executeFunction: true
  }),
  computed: {
    goodsAmount() {
      return (
        this.indexMassive.length +
        this.chimniMassive.length +
        this.sandwichMassive.length +
        this.desertMassive.length +
        this.drinksMassive.length
      );
    }
  },
  mounted() {
    axios
      .get("http://127.0.0.1:8000/api/trdelnik/")
      .then(response => (this.trdelnikCatalog = response.data))
      .catch(error => {
        console.log(error);
      });
    axios
      .get("http://127.0.0.1:8000/api/chimni/")
      .then(response => (this.chimniCatalog = response.data))
      .catch(error => {
        console.log(error);
      });
    axios
      .get("http://127.0.0.1:8000/api/sandwich/")
      .then(response => (this.sandwichCatalog = response.data))
      .catch(error => {
        console.log(error);
      });
    axios
      .get("http://127.0.0.1:8000/api/deserts/")
      .then(response => (this.desertsCatalog = response.data))
      .catch(error => {
        console.log(error);
      });
    axios
      .get("http://127.0.0.1:8000/api/drinks/")
      .then(response => (this.drinksCatalog = response.data))
      .catch(error => {
        console.log(error);
      });
  },
  methods: {
    showTrdelniki() {
      this.isDrinks = false;
      this.isDesert = false;
      this.isSandwich = false;
      this.isChimni = false;
      this.isKruasan = false;
      this.isTrdelnik = true;
    },
    showChimni() {
      this.isDrinks = false;
      this.isDesert = false;
      this.isSandwich = false;
      this.isTrdelnik = false;
      this.isKruasan = false;
      this.isChimni = true;
    },
    showSandwich() {
      this.isDrinks = false;
      this.isDesert = false;
      this.isTrdelnik = false;
      this.isChimni = false;
      this.isKruasan = false;
      this.isSandwich = true;
    },
    showDeserts() {
      this.isDrinks = false;
      this.isTrdelnik = false;
      this.isChimni = false;
      this.isSandwich = false;
      this.isKruasan = false;
      this.isDesert = true;
    },
    showDrinks() {
      this.isTrdelnik = false;
      this.isChimni = false;
      this.isSandwich = false;
      this.isDesert = false;
      this.isKruasan = false;
      this.isDrinks = true;
    },
    showKruasan() {
      this.isTrdelnik = false;
      this.isChimni = false;
      this.isSandwich = false;
      this.isDesert = false;
      this.isDrinks = false;
      this.isKruasan = true;
    },
    buyTrdelnik(tr) {
      if (this.executeFunction) {
        this.showPopup = true;
        setTimeout(() => {
          this.showPopup = false;
        }, 5000);
      }
      this.executeFunction = false;
      this.indexMassive.push(tr.id);
      this.TRarr.push(tr);
    },
    buyChimni(ch) {
      if (this.executeFunction) {
        this.showPopup = true;
        setTimeout(() => {
          this.showPopup = false;
        }, 5000);
      }
      this.executeFunction = false;
      this.chimniMassive.push(ch.id);
      this.CHarr.push(ch);
    },
    buySandwich(sd) {
      if (this.executeFunction) {
        this.showPopup = true;
        setTimeout(() => {
          this.showPopup = false;
        }, 5000);
      }
      this.executeFunction = false;
      this.sandwichMassive.push(sd.id);
      this.SDarr.push(sd);
    },
    buyDesert(ds) {
      if (this.executeFunction) {
        this.showPopup = true;
        setTimeout(() => {
          this.showPopup = false;
        }, 5000);
      }
      this.executeFunction = false;
      this.desertMassive.push(ds.id);
      this.DSarr.push(ds);
    },
    buyDrinks(dr) {
      if (this.executeFunction) {
        this.showPopup = true;
        setTimeout(() => {
          this.showPopup = false;
        }, 5000);
      }
      this.executeFunction = false;
      this.drinksMassive.push(dr.id);
      this.DRarr.push(dr);
    },
    sellDrinks(dr) {
      this.drinksMassive = this.drinksMassive.filter(item => item !== dr.id);
      this.DRarr = this.DRarr.filter(element => element.id !== dr.id);
    },
    sellDesert(ds) {
      this.desertMassive = this.desertMassive.filter(item => item !== ds.id);
      this.DSarr = this.DSarr.filter(element => element.id !== ds.id);
    },
    sellSandwich(sd) {
      this.sandwichMassive = this.sandwichMassive.filter(
        item => item !== sd.id
      );
      this.SDarr = this.SDarr.filter(element => element.id !== sd.id);
    },
    sellChimni(ch) {
      this.chimniMassive = this.chimniMassive.filter(item => item !== ch.id);
      this.CHarr = this.CHarr.filter(element => element.id !== ch.id);
    },
    sellTrdelnik(tr) {
      this.indexMassive = this.indexMassive.filter(item => item !== tr.id);
      this.TRarr = this.TRarr.filter(element => element.id !== tr.id);
    },
    openCart() {
      if (this.goodsAmount) {
        this.isCart = true;
      }

      let TRelement = [];
      for (let i = 0; i < this.TRarr.length; i++) {
        TRelement.push(Number(this.TRarr[i].price));
      }
      this.trPrice = TRelement.reduce((a, b) => a + b, 0);

      let CHelement = [];
      for (let i = 0; i < this.CHarr.length; i++) {
        CHelement.push(Number(this.CHarr[i].price));
      }
      this.chPrice = CHelement.reduce((a, b) => a + b, 0);

      let sdelement = [];
      for (let i = 0; i < this.SDarr.length; i++) {
        sdelement.push(Number(this.SDarr[i].price));
      }
      this.sdPrice = sdelement.reduce((a, b) => a + b, 0);

      let dselement = [];
      for (let i = 0; i < this.DSarr.length; i++) {
        dselement.push(Number(this.DSarr[i].price));
      }
      this.dsPrice = dselement.reduce((a, b) => a + b, 0);

      let drelement = [];
      for (let i = 0; i < this.DRarr.length; i++) {
        drelement.push(Number(this.DRarr[i].price));
      }
      this.drPrice = drelement.reduce((a, b) => a + b, 0);
    },
    closeCart() {
      this.indexMassive = [];
      this.chimniMassive = [];
      this.sandwichMassive = [];
      this.desertMassive = [];
      this.drinksMassive = [];
      (this.name = ""),
        (this.mobile = ""),
        (this.TRarr = []),
        (this.CHarr = []),
        (this.SDarr = []),
        (this.DSarr = []),
        (this.DRarr = []),
        (this.isCart = false);
      this.step = 1;
      this.executeFunction = true;
    },
    addMoreToCart() {
      this.isCart = false;
      this.executeFunction = true;
    },
    nextStep() {
      if ((this.step = 1)) {
        this.step = 2;
      }
      if (this.mobile && this.name) {
        this.step = 3;
        // trdelniki
        let drelement = [];
        for (let i = 0; i < this.TRarr.length; i++) {
          drelement.push(this.TRarr[i].title);
        }
        // chimni
        let ccelement = [];
        for (let i = 0; i < this.CHarr.length; i++) {
          ccelement.push(this.CHarr[i].title);
        }
        // sandwich
        let ssselement = [];
        for (let i = 0; i < this.SDarr.length; i++) {
          ssselement.push(this.SDarr[i].title);
        }
        // deserts
        let dddelement = [];
        for (let i = 0; i < this.DSarr.length; i++) {
          dddelement.push(this.DSarr[i].title);
        }
        // drinks
        let ddrrelement = [];
        for (let i = 0; i < this.DRarr.length; i++) {
          ddrrelement.push(this.DRarr[i].title);
        }
        this.Fromorder =
          drelement.join(", ") +
          " " +
          ccelement.join(", ") +
          " " +
          ssselement.join(", ") +
          " " +
          dddelement.join(", ") +
          " " +
          ddrrelement.join(", ");
        console.log(this.Fromorder);
        axios.post("http://eliks.kz/api/order/", {
          order: this.Fromorder,
          adress: this.Fromadress,
          name: this.name,
          mobile: this.mobile
        });
      }
    },
    goBack() {
      this.step--;
    },
    selectAgybay() {
      this.KabanbayAdress = false;
      this.AgybayAdress = true;
      this.Fromadress = "Агыбай батыра 4";
    },
    selectKabanbay() {
      this.AgybayAdress = false;
      this.KabanbayAdress = true;
      this.Fromadress = "Кабанбай батыра 58а";
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/style/fonts.scss";
@media all and (max-width: 768px) {
  .popup {
    top: 15px !important;
    left: 0 !important;
    right: 0 !important;
    margin-left: auto;
    margin-right: auto;
    text-align: center;
    z-index: 999;
  }
  .card {
    position: fixed !important;
    width: 242px !important;
    height: 83px !important;
    left: 0 !important;
    right: 0 !important;
    margin: 0 auto !important;
    padding-top: 20px !important;
    padding-left: 29px !important;
    h4 {
      font-size: 14px !important;
    }
    p {
      font-size: 13px !important;
    }
  }
  .main {
    padding-top: 10px !important;
    background: url("../assets/img/mobile/Path.png") !important;
    background-size: 100% 100% !important;
    height: auto !important;
    padding-bottom: 148px !important;
    .title {
      text-align: center !important;
      font-size: 34px !important;
    }
  }
  .catalog {
    margin-top: 31px !important;
    display: flex !important;
    justify-content: center !important;
    flex-wrap: wrap !important;
    grid-row-gap: 0px !important;
    grid-column-gap: 0px !important;
  }
  .cart_title {
    text-align: center !important;
    font-size: 16px !important;
  }
  .cart {
    width: 157px !important;
    height: 167px !important;
    .image {
      width: 120px !important;
      top: -124px !important;
    }
    .sandwich_mobile_image {
      top: -78px !important;
    }
    .chimni_mobile_image {
      top: -94px !important;
    }
    .buy_ice_cream {
      margin-top: 5px !important;
      width: 110px !important;
      height: 30px !important;
      font-size: 17px !important;
      img {
        display: none !important;
      }
    }
  }
  .cartDesert {
    width: 143px !important;
    height: 124px !important;
    padding: 0 !important;
    padding-bottom: 5px !important;
    .mobile_cart_desert {
      margin-top: 10px !important;
    }
    .image {
      top: -68px !important;
      width: 93px !important;
    }
    .buy_ice_cream {
      margin-top: 5px !important;
      width: 110px !important;
      height: 30px !important;
      font-size: 17px !important;
      img {
        display: none !important;
      }
    }
  }
  .navigation {
    flex-wrap: wrap !important;
    justify-content: center;
    &__items {
      margin: 0 10px !important;
      margin-bottom: 10px !important;
      .image {
        display: none !important;
      }
    }
  }
  .sandwich_mobile_catalog {
    margin-top: -7px !important;
    display: flex !important;
    justify-content: center !important;
    flex-wrap: wrap !important;
    grid-row-gap: 0px !important;
    grid-column-gap: 0px !important;
  }
  .chimni_mobile_catalog {
    margin-top: 15px !important;
    display: flex !important;
    justify-content: center !important;
    flex-wrap: wrap !important;
    grid-row-gap: 0px !important;
    grid-column-gap: 0px !important;
  }
  .mobile_catalog_desert {
    margin-top: 13px !important;
    display: flex !important;
    justify-content: center !important;
    flex-wrap: wrap !important;
    grid-row-gap: 0px !important;
    grid-column-gap: 0px !important;
  }
  .mobile_drinks_catalog {
    margin-top: 8px !important;
    display: flex !important;
    justify-content: center !important;
    flex-wrap: wrap !important;
    grid-row-gap: 0px !important;
    grid-column-gap: 0px !important;
  }
  .final_man {
    height: 85% !important;
    width: 85% !important;
    padding: 20px !important;
    text-align: center !important;
    img {
      width: 300px !important;
      height: 165px !important;
    }
    .close {
      width: 20px !important;
      height: 20px !important;
    }
  }
  .fixed_div {
    .card_order {
      height: 85% !important;
      width: 85% !important;
      padding: 20px !important;
      .close {
        top: 12px !important;
        right: 8px !important;
        width: 16px !important;
        height: 16px !important;
      }
      &__title {
        display: none !important;
      }
      &__bottom_btns {
        &__back {
          height: 37px !important;
          p {
            font-size: 14px !important;
            line-height: 17px !important;
          }
        }
        &__next {
          width: 118px !important;
          height: 37px !important;
          p {
            font-size: 14px !important;
            line-height: 17px !important;
          }
        }
      }
      &__content {
        .bill {
          width: 240px !important;
          height: 363px !important;
          padding-top: 91px !important;
          &__content {
            width: 150px !important;
          }
          &__total {
            top: 234px !important;
            width: 156px !important;
          }
        }
        flex-direction: column !important;
        align-items: center !important;
        .adress {
          display: none !important;
        }
      }
    }
    .register_girl {
      height: 85% !important;
      width: 85% !important;
      padding: 20px !important;
      .next_prev_btns {
        padding: 0 !important;
        &__submit {
          width: 137px !important;
          height: 30px !important;
          p {
            font-size: 14px !important;
            line-height: 17px !important;
          }
        }
      }
      h1 {
        margin-top: 25px !important;
      }
      .form {
        z-index: 9999;
        width: auto !important;
      }
      &__girl_bg {
        display: none !important;
      }
    }
  }
  .mobile_cart_trdelnik {
    margin-top: 130px !important;
    margin-left: 10px !important;
    margin-right: 10px !important;
  }
  .mobile_cart_chimni {
    margin-top: 91px !important;
    margin-left: 10px !important;
    margin-right: 10px !important;
  }
  .mobile_cart_sandwich {
    margin-top: 86px !important;
    margin-left: 10px !important;
    margin-right: 10px !important;
  }
  .mobile_cart_desertt {
    margin-top: 94px !important;
    margin-left: 10px !important;
    margin-right: 10px !important;
  }
  .mobile_cart_drinks {
    margin-top: 94px !important;
    margin-left: 10px !important;
    margin-right: 10px !important;
  }
}
.main {
  position: relative;
  background: url("../assets/img/catalog/bg.png");
  background-size: 100% 100%;
  padding-top: 60px;
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 1363px;
  .title {
    @include medium;
    font-size: 48px;
    line-height: 59px;
    margin-bottom: 20px;
    color: #123429;
  }
  .navigation {
    display: flex;
    align-items: center;
    &__items {
      position: relative;
      display: flex;
      flex-direction: column;
      align-items: center;
      margin: 0 40px;
      cursor: pointer;
      &:hover {
        a {
          color: #fd0bce;
          opacity: 1;
        }
      }
      a {
        text-decoration: none;
        cursor: pointer;
        @include medium;
        font-size: 18px;
        line-height: 22px;
        color: #123429;
        opacity: 0.3;
        z-index: 999;
      }
      .image {
        position: absolute;
        top: 10px;
        display: flex;
        justify-content: center;
        align-items: flex-end;
        padding-bottom: 7px;
        width: 122px;
        height: 122px;
        border-radius: 50%;
        &:hover {
          background: rgba(98, 213, 192, 0.8);
        }
      }
    }
  }
}
.catalog {
  margin-top: 307px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-column-gap: 20px;
  grid-row-gap: 187px;
}
.popup {
  position: fixed;
  background: #e5e5e5;
  width: 203px;
  top: 40px;
  right: 40px;
  border-radius: 10px;
  padding: 10px;
  &__text {
    @include medium;
    font-size: 14px;
    line-height: 17px;
    color: #123429;
  }
}
.cartDrinks {
  position: relative;
  width: 163px;
  height: 210px;
  background: #ffffff;
  box-shadow: 0px 4px 10px rgba(34, 32, 32, 0.25);
  border-radius: 16px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-end;
  padding-bottom: 20px;
  .buy_ice_cream {
    width: 195px;
    height: 40px;
    background: #fd0bce;
    border-radius: 20px;
    border: none;
    cursor: pointer;
    outline: none;
    font-size: 18px;
    line-height: 22px;
    @include medium;
    color: #ffffff;
    margin-top: 20px;
  }
}
.cartDesert {
  position: relative;
  width: 255px;
  height: 210px;
  background: #ffffff;
  box-shadow: 0px 4px 10px rgba(34, 32, 32, 0.25);
  border-radius: 16px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-end;
  padding-bottom: 20px;
  .buy_ice_cream {
    width: 195px;
    height: 40px;
    background: #fd0bce;
    border-radius: 20px;
    border: none;
    cursor: pointer;
    outline: none;
    font-size: 18px;
    line-height: 22px;
    @include medium;
    color: #ffffff;
    margin-top: 20px;
  }
}
.cart {
  position: relative;
  width: 255px;
  height: 245px;
  background: #ffffff;
  box-shadow: 0px 4px 10px rgba(34, 32, 32, 0.25);
  border-radius: 16px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-end;
  padding-bottom: 20px;
  .buy_ice_cream {
    width: 195px;
    height: 40px;
    background: #fd0bce;
    border-radius: 20px;
    border: none;
    cursor: pointer;
    outline: none;
    font-size: 18px;
    line-height: 22px;
    @include medium;
    color: #ffffff;
    margin-top: 20px;
  }
}
.image {
  position: absolute;
  top: -147px;
}
.cart_title {
  @include medium;
  font-size: 18px;
  line-height: 22px;
  text-transform: uppercase;
  color: #123429;
  margin-bottom: 10px;
}
.price {
  display: flex;
  align-items: center;
  p {
    @include medium;
    font-size: 18px;
    line-height: 22px;
    margin-right: 4px;
    color: #fd0bce;
  }
}
.litres {
  @include normal;
  font-size: 12px;
  line-height: 15px;
  color: #123429;
  margin-bottom: 10px;
}
.fixed_div {
  position: fixed;
  top: 0;
  left: 0;
  height: 100vh;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 999;
  .close {
    position: absolute;
    top: 24px;
    right: 24px;
    cursor: pointer;
    z-index: 999;
  }
  .card_order {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    width: 800px;
    height: 625px;
    background: #ffffff;
    box-shadow: 0px 4px 40px rgba(0, 0, 0, 0.25);
    border-radius: 24px;
    padding: 40px 26px 60px;

    &__title {
      @include medium;
      font-size: 26px;
      line-height: 32px;
      text-align: center;
      color: #fd0bce;
    }
    &__content {
      width: 100%;
      display: flex;
      justify-content: space-between;
      .bill {
        position: relative;
        background: url("../assets/img/calculator/pay-bill.png");
        background-size: 100% 100%;
        width: 292px;
        height: 421px;
        padding-top: 113px;
        display: flex;
        flex-direction: column;
        align-items: center;
        &__content {
          width: 187px;
          display: flex;
          justify-content: space-between;
        }
        &__total {
          position: absolute;
          top: 275px;
          left: 0;
          right: 0;
          margin-left: auto;
          margin-right: auto;
          width: 187px;
          display: flex;
          justify-content: space-between;
        }
      }
      .adress {
        margin-top: 15px;
        &__title {
          @include medium;
          font-size: 18px;
          line-height: 22px;
          color: #123429;
        }
        &__work_time {
          display: flex;
          margin-top: 15px;
          margin-bottom: 40px;
          p {
            @include medium;
            font-size: 18px;
            line-height: 22px;
            margin-left: 8px;
            color: #123429;
            opacity: 0.3;
          }
        }
        &__kabanbay {
          width: 382px;
          height: 68px;
          border-radius: 16px;
          display: flex;
          align-items: center;
          margin-bottom: 40px;
          cursor: pointer;
          border: 1px solid #fff;
          padding-left: 16px;
          p {
            @include medium;
            font-size: 18px;
            line-height: 22px;
            color: #123429;
            margin-left: 16px;
            span {
              color: #fd0bce;
            }
          }
        }
      }
    }
    &__bottom_btns {
      width: 100%;
      display: flex;
      justify-content: space-between;
      &__back {
        display: flex;
        align-items: center;
        cursor: pointer;
        opacity: 0.5;
        p {
          @include medium;
          line-height: 22px;
          text-transform: uppercase;
          margin-left: 11px;
          color: #123429;
        }
        height: 51px;
      }
      &__next {
        background: #fd0bce;
        border-radius: 16px;
        width: 236px;
        height: 51px;
        display: flex;
        align-items: center;
        justify-content: center;
        cursor: pointer;
        p {
          @include bold;
          font-size: 18px;
          line-height: 22px;
          margin-right: 7px;
          text-transform: uppercase;
          color: #ffffff;
        }
      }
    }
  }
  .register_girl {
    position: relative;
    width: 800px;
    height: 625px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    background: #ffffff;
    box-shadow: 0px 4px 40px rgba(0, 0, 0, 0.25);
    border-radius: 24px;
    padding: 40px 80px;
    .form {
      width: 100%;
      display: flex;
      justify-content: space-between;
      form {
        display: flex;
        flex-direction: column;
        label {
          @include medium;
          font-size: 18px;
          line-height: 22px;
          margin-bottom: 4px;
          color: #123429;
        }
        input {
          @include medium;
          width: 260px;
          height: 40px;
          padding-left: 16px;
          font-size: 18px;
          line-height: 22px;
          margin-bottom: 4px;
          color: #123429;
          background: rgba(125, 222, 205, 0.2);
          border: 1px solid #fd0bce;
          border-radius: 16px;
          margin-bottom: 24px;
          outline: none;
        }
      }
    }
    &__girl_bg {
      position: absolute;
      width: 400px;
      height: 100%;
      right: 0;
      top: 0;
      background: url("../assets/img/catalog/girl-register.png");
    }
    h1 {
      @include medium;
      font-size: 26px;
      line-height: 32px;
      color: #fd0bce;
    }
    .next_prev_btns {
      display: flex;
      justify-content: space-between;
      width: 100%;
      padding: 0 50px;
      z-index: 999;
      &__back {
        display: flex;
        align-items: center;
        opacity: 0.5;
        cursor: pointer;
        p {
          @include medium;
          margin-left: 11px;
          font-size: 18px;
          line-height: 22px;
          text-transform: uppercase;
          color: #123429;
        }
      }
      &__submit {
        display: flex;
        align-items: center;
        justify-content: center;
        cursor: pointer;
        width: 236px;
        height: 51px;
        background: #fd0bce;
        border-radius: 16px;
        p {
          @include bold;
          font-size: 18px;
          line-height: 22px;
          text-transform: uppercase;
          margin-right: 7px;
          color: #ffffff;
        }
      }
    }
  }
  .final_man {
    position: relative;
    width: 800px;
    height: 625px;
    background: #ffffff;
    box-shadow: 0px 4px 40px rgba(0, 0, 0, 0.25);
    border-radius: 24px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    padding: 40px 0;
    h1 {
      @include medium;
      font-size: 26px;
      line-height: 32px;
      color: #fd0bce;
    }
    h2 {
      @include medium;
      font-size: 18px;
      line-height: 22px;
      color: #123429;
    }
    .finish {
      background: #fd0bce;
      border-radius: 16px;
      width: 215px;
      height: 51px;
      cursor: pointer;
      display: flex;
      justify-content: center;
      align-items: center;
      p {
        @include bold;
        font-size: 18px;
        line-height: 22px;
        text-transform: uppercase;
        color: #ffffff;
      }
    }
  }
}
.card {
  position: fixed;
  width: 312px;
  height: 102px;
  bottom: 30px;
  right: 30px;
  background: url("../assets/img/korzina.png");
  background-size: 100% 100%;
  cursor: pointer;
  padding-top: 28px;
  padding-left: 38px;
  h4 {
    @include bold;
    font-size: 18px;
    line-height: 22px;
    color: #123429;
  }
  p {
    @include normal;
    font-size: 14px;
    line-height: 17px;
    color: #123429;
  }
}
.popUpTransition-enter-active,
.popUpTransition-leave-active {
  transition: all 0.5s;
}
.popUpTransition-enter,
.popUpTransition-leave-to {
  transform: translateY(-20px);
  opacity: 0;
}
.card_animation-enter {
  opacity: 0;
}
.card_animation-enter-to {
  transition: 1s;
  opacity: 1;
}
.card_animation-leave-active {
  display: none;
}
</style>
