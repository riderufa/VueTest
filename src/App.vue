<template>
  <div id="app">
    <div>
      <NavBar />
    </div>
    <transition v-on:enter="enter" v-on:leave="leave">
      <router-view />
    </transition>
  </div>
</template>

<script>

import NavBar from "@/components/navbar.vue";
import { TweenLite, TimelineMax } from "gsap";

let tl = new TimelineMax();

export default {
  
  methods: {
    enter: function(el, done) {
      tl.fromTo(el, 0.3, { opacity: 0 }, { opacity: 1, onComplete: done });
    },

    leave: function(el, done) {
      tl.fromTo(el, 0.3, { opacity: 1 }, { opacity: 0, onComplete: done });
    }
  },

  components: {
    NavBar
  }
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";

.fon {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url(./assets/lens-1209823_1920.jpg);
  background-repeat: no-repeat;
  background-size: cover;
  z-index: -1;
  opacity: 0.5;
}

body {
  background: #000;
}

a {
  color: #fff;
  text-decoration: none;
}

a:hover {
  color: #fff;
  text-decoration: none;
}
</style>
