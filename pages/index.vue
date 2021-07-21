<template>
  <div class="back">
    <Menu/>
    <div class="back1" id="back1">
    </div>
    <AboutC3/>
    <div class="back2" id="back2">
    </div>
    <MyMessage/>
    <div class="back3" id="back3">
    </div>
    <div class="back4" id="back4">
    </div>
    <div class="back5" id="back5">
    </div>
    <Footer2/>
    <Footer/>
  </div>
</template>

<script>
import Footer from '~/components/Footer.vue'
import Menu from '~/components/Menu.vue'
import AboutC3 from '~/components/AboutC3.vue'
import MyMessage from '~/components/MyMessage.vue'
import Footer2 from '~/components/Footer2.vue'

export default {
  components: {
    Menu,
    Footer,
    AboutC3,
    MyMessage,
    Footer2
  }
}
</script>

<style>
.back1 {
  background: lightcyan;
  height: 1080px;
}
.back2 {
  background: lightpink;
  height: 1080px;
}
.back3 {
  background: lightblue;
  height: 1080px;
}
.back4 {
  background: lightgreen;
  height: 1080px;
}
.back5 {
  background: lightyellow;
  height: 1080px;
}
.back {
  scroll-behavior: smooth;
  height: 1080px;
}
</style>

