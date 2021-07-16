<template>
  <div>
    <div class="button" @click="ActiveBtn=!ActiveBtn">
      <span class="icon-bar" :class="{'icon-bar':ActiveBtn}"></span>
      <span class="icon-bar" :class="{'icon-bar':ActiveBtn}"></span>
      <span class="icon-bar" :class="{'icon-bar':ActiveBtn}"></span>
    </div>
    <transition name="slide">
      <div class="change" v-show="ActiveBtn">この文字が切り替わるはず</div>
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      ActiveBtn: false,
      linkUrl1: "/community/1",
      linkUrl2: "/community/2",
      linkUrl3: "/community/3",
      linkUrl4: "/community/4"
    }
  }
};
</script>

<style scoped>
.button {
  position: absolute;
  height: 30px;
  width: 30px;
  border: solid 1px black;
  cursor: pointer;
  z-index: 100;
}
.change {
  position: absolute;
  padding-top: 50px;
  background-color: gray;
  max-width: 80%;
}
.slide-enter-active, .slide-leave-active {
  transform: translate(0px, 0px); 
  transition: transform 225ms cubic-bezier(0.2, 1, 0.2, 1) 0ms;
}

.slide-enter, .slide-leave-to {
  transform: translateY(0) translateX(-100vh);
}
</style>
