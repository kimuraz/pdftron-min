<template>
  <div id="app">
    <div>
      <button @click="ready = true">Start</button>
      <button @click="showIframe = true">Iframe</button>
    </div>
    <PdfTronView v-if="ready"/>

    <iframe id="pdftron-nested" width="100%" height="100%" v-if="showIframe" src="/pdftron_iframe.html"/>
  </div>
</template>

<script>
import PdfTronView from "./components/PdfTronView";

export default {
  name: "App",
  components: {
    PdfTronView,
  },
  data() {
    return {
      ready: false,
      showIframe: false,
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
