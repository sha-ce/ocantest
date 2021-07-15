<template>
  <div class="nav-wrap">
    <div class="nav-container">
      <div class="button" tabindex="0">
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
      </div>
      <div class="nav-content">
        <ul>
          <li>
            <div class="home">
              <a href="./">Home</a>
            </div>
          </li>
          <li><p>作品を見る</p></li>
          <li>
            <div class="list">
              <a href="./commmunity/game/">GAME</a>
            </div>
          </li>
          <li>
            <div class="list">
              <a href="./commmunity/cg/">CG</a>
            </div>
          </li>
          <li>
            <div class="list">
              <a href="./commmunity/hack/">HACK</a>
            </div>
          </li>
          <li>
            <div class="list">
              <a href="./commmunity/media_art/">MEDIA_ART</a>
            </div>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style scoped>
.nav-wrap {
  position: relative;
  z-index: 99;
}
.nav-container {
  position: fixed;
  height: 100vh;
  width: 100%;
  pointer-events: none;
}
.button {
  position: fixed;
  display: flex;
  flex-direction: column;
  justify-content: center;
  z-index: 100;
  -webkit-appearance: none;
  border: 0;
  border-radius: 0;
  height: 40px;
  width: 30px;
  cursor: pointer;
  pointer-events: auto;
  margin: 10px;
  touch-action: manipulation;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
}
.icon-bar {
  display: block;
  width: 100%;
  height: 2px;
  background: white;
  transition: 0.3s;
}
.icon-bar + .icon-bar {
  margin-top: 7px;
}

.nav-container:focus-within .button {
  pointer-events: none;
}
.nav-container:focus-within .icon-bar:nth-of-type(1) {
  transform: translate3d(0, 9px, 0) rotate(-45deg);
}
.nav-container:focus-within .icon-bar:nth-of-type(2) {
  opacity: 0;
}
.nav-container:focus-within .icon-bar:nth-of-type(3) {
  transform: translate3d(0, -9px, 0) rotate(45deg);
}
.nav-content {
  padding: 60px 0 0 20px;
  max-width: 300px;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: #4a4a4a;
  pointer-events: auto;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
  transform: translateX(-100%);
  transition: transform 0.3s;
  will-change: transform;
  contain: paint;
  flex-direction: column;
  z-index: 99;
}
.home {
  margin-bottom: 10px;
}
.list {
  padding-left: 20px;
}
.nav-content li a,
.nav-content li p {
  padding: 5px 5px;
  display: block;
  text-transform: uppercase;
  transition: color 0.1s;
  color: white;
}

.nav-content li a:hover {
  color: #bf7497;
}
.nav-container:focus-within .nav-content {
  transform: none;
}
html,
body {
  height: 100%;
}
a,
a:visited,
a:focus,
a:active,
a:link {
  text-decoration: none;
  outline: 0;
}
a {
  color: currentColor;
  transition: 0.2s ease-in-out;
}
h1,
h2,
h3,
h4 {
  margin: 0;
}
ul {
  padding: 0;
  list-style: none;
}
</style>

<script>
export default {
  data() {
    return {
      buttonActive: true,
      scroll: 0,
    };
  },
  mounted() {
    window.addEventListener("scroll", this.scrooWindow)
  },
  methods: {
    returnTop() {
      window.scrollTo({
        top: 0,
        behavior: "smooth",
      });
    },
    scrollTo(hashName) {
      const rect = this.$refs.back2.getBoundingClientRect();
      window.scrollTo({
        top: rect.top,
        behavior: "smooth",
      });
    },
  },
  scrollWindow() {
    const top = 100;
    this.scroll = window.scrollY;
    if (top <= this.scroll) {
      this.buttonActive = true;
    } else {
      this.buttonActive = false;
    }
  },
};
</script>
