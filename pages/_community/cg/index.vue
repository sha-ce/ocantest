<template>
  <div class="back">
    <Menu/>
    <div class="back1" id="back1">
    CG
    </div>
    <Footer/>
  </div>
</template>

<script>
import Footer from '~/components/Footer.vue'
import Menu from '~/components/Menu.vue'

export default {
  components: {
    Menu,
    Footer
  }
}
</script>

<style>
.back1 {
  background: black;
  height: 1080px;
  color: white;
  font-size: 500%;
  padding: 50px 0 0 350px;
}
.back {
  scroll-behavior: smooth;
  height: 1080px;
}
</style>

