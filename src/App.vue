<template>
  <MainPage />
</template>

<script>
import MainPage from "./components/MainPage.vue";

export default {
  name: "App",
  components: {
    MainPage,
  },
};
</script>

<style>
@font-face {
  font-family: "EarlyFontDiary";
  src: url("https://cdn.jsdelivr.net/gh/projectnoonnu/noonfonts_220508@1.0/EarlyFontDiary.woff2")
    format("woff2");
  font-weight: normal;
  font-style: normal;
}

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

html {
  width: 100vw;
  height: 100vh;
  background: #36d1dc; /* fallback for old browsers */
  background: -webkit-linear-gradient(
    to right,
    #5b86e5,
    #36d1dc
  ); /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(
    to right,
    #5b86e5,
    #36d1dc
  ); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}

#app {
  font-family: "EarlyFontDiary", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
