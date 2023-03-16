<template>
  <Circle />
</template>

<script>
import Circle from './components/Circle.vue';

export default {
  name: 'App',
  components: { Circle },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "GHEA Grapalat";
}

@font-face {
  font-family: "GHEA Grapalat";
  font-style: normal;
  font-weight: 400;
  src: url("./assets/fonts/GHEAGrpalatReg.otf") format("opentype");
}

#app {
  width: 100%;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
