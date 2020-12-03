<template>
  <div class="contacts">
    <div class="fon"></div>
    <h1 class="js-splitme">Контакты</h1>
  </div>
</template>


<script>
import Splitter from 'split-html-to-chars';
import { TweenLite, TimelineMax } from 'gsap';

export default {

  mounted() {

    let App = document.querySelector('.fon');
    let tl = new TimelineMax();
    let els = document.querySelectorAll(".js-splitme");

    [].forEach.call(els, function(el) {
        el.outerHTML = Splitter(el.outerHTML, '<span class="letter">$</span>');
    });
    
    tl.staggerFromTo(".letter", 0.2, {opacity: 0}, {opacity: 1}, 0.03);
    tl.fromTo(".fon", 1, {scale: 1}, {scale: 1.5});
    tl.fromTo(".navbar", 0.5, {y: -100}, {y: 0});
  }

}
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

</style>