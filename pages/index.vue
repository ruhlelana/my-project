<template>
  <div class="container">
    <h1>Welcome Prys dan Ervin!</h1>
    <h2>Yoiiii</h2>
    <p>Lorem ipsum doroth sit amet</p>
    <p><nuxt-link to="/product">Product page</nuxt-link></p>
    <p><nuxt-link to="/product">Contact page</nuxt-link></p>
  </div>
</template>

<style>
.container {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  padding: 60px;
}
.page-enter-active, .page-leave-active {
  transition: all .25s ease-out;
}
.page-enter, .page-leave-active {
  opacity: 0;
  transform-origin: 50% 50%;
} html, body {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  background: #222;
  color: white;
  width: 100vw;
  height: 100vh;
}

a, a:visited {
  color: #3edada;
  text-decoration: none;
}

.container {
  padding: 60px;
  width: 100vw;
  height: 100vh;
  background: #444;
}
.page-enter-active {
  animation: acrossIn .45s ease-out both;
}

.page-leave-active {
  animation: acrossOut .65s ease-in both;
}

@keyframes acrossIn {
  0% {
    transform: translate3d(-100%, 0, 0);
  }
  100% {
    transform: translate3d(0, 0, 0);
  }
}

@keyframes acrossOut {
  0% {
    transform: translate3d(0, 0, 0);
  }
  100% {
    transform: translate3d(100%, 0, 0);
  }
}
</style>

<transition
  @before-enter="beforeEnter"
  @enter="enter"
  @after-enter="afterEnter"
  @enter-cancelled="enterCancelled"

  @before-Leave="beforeLeave"
  @leave="leave"
  @after-leave="afterLeave"
  @leave-cancelled="leaveCancelled"
  :css="false">

 </transition>

 <script>
 import { TweenMax, Back } from 'gsap'

export default {
  transition: {
    mode: 'out-in',
    css: false,
    beforeEnter (el) {
      TweenMax.set(el, {
        transformPerspective: 600,
        perspective: 300,
        transformStyle: 'preserve-3d'
      })
    },
    enter (el, done) {
      TweenMax.to(el, 1, {
        rotationY: 360,
        transformOrigin: '50% 50%',
        ease: Back.easeOut
      })
      done()
    },
    leave (el, done) {
      TweenMax.to(el, 1, {
        rotationY: 0,
        transformOrigin: '50% 50%',
        ease: Back.easeIn
      })
      done()
    }
  }
}
</script>
