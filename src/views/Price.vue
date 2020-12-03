<template>
  <div>
    <div class="contacts">
      <div class="fon"></div>
      <h1 class="js-splitme">Цены</h1>

      <div class="price-list">
        <div class="container">
          <div class="row">
            <div class="col price-item">
              <h2>Фото 3x4</h2>
              <div class="price-img"></div>
              <p class="price-item-desc">
                от
                <strong>250 рублей</strong>
              </p>
              <a class="price-item-btn" href="tel:89999999">Позвонить</a>
            </div>
            <div class="col price-item">
              <h2>Фото 3x4</h2>
              <div class="price-img"></div>
              <p class="price-item-desc">
                от
                <strong>250 рублей</strong>
              </p>
              <a class="price-item-btn" href>Позвонить</a>
            </div>
            <div class="col price-item">
              <h2>Фото 3x4</h2>
              <div class="price-img"></div>
              <p class="price-item-desc">
                от
                <strong>250 рублей</strong>
              </p>
              <a class="price-item-btn" href>Позвонить</a>
            </div>
            <div class="col price-item">
              <h2>Фото 3x4</h2>
              <div class="price-img"></div>
              <p class="price-item-desc">
                от
                <strong>250 рублей</strong>
              </p>
              <a class="price-item-btn" href>Позвонить</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
import Splitter from "split-html-to-chars";
import { TweenLite, TimelineMax } from "gsap";

export default {
  mounted() {
    let App = document.querySelector(".fon");
    let tl = new TimelineMax();
    let els = document.querySelectorAll(".js-splitme");

    [].forEach.call(els, function(el) {
      el.outerHTML = Splitter(el.outerHTML, '<span class="letter">$</span>');
    });

    tl.staggerFromTo(".letter", 0.2, { opacity: 0 }, { opacity: 1 }, 0.03);
    tl.fromTo(".fon", 1, { scale: 1 }, { scale: 1.5 });
    tl.fromTo(".navbar", 0.5, { y: -100 }, { y: 0 });
    tl.fromTo(".price-list", 0.8, { x: "200%" }, { x: "0%" });
  }
};
</script>


<style lang="scss">
.contacts {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
  max-height: 667;
  opacity: 1;
  position: relative;
  overflow: hidden;
}

h1 {
  color: #fff;
  padding-left: 20px;
  font-size: 100px;
  font-weight: 600;
}

.price-list {
  position: absolute;
  top: 100px;
  left: 50px;
  right: 50px;
  padding: 20px;
  border-radius: 10px;
  background-color: #fff;
}

.price-img {
  width: 150px;
  height: 100px;
  background: #000;
  border-radius: 10px;
  margin-top: 20px;
}

.price-item {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.price-item-btn {
  background-color: #c8644a;
  padding: 20px;
  border-radius: 10px;
}

.price-item-desc {
  padding: 20px;
  margin: 0;
}
</style>