<template>
  <div>
    <img src=" " />

    <RegresiveCount timex="5"></RegresiveCount>
  </div>
</template>

<script>
import RegresiveCount from "./RegresiveCount.vue";

export default {
  name: "Header",
  components: {
    RegresiveCount,
  },
};
</script>

<style scoped>
div {
  height: 100vh;

  background: linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.7)),
    url("/Freddy/Sites/portafolio/src/assets/img/CocoHeaderBackground.jpg");
  background-repeat: no-repeat;
  background-position: center;
  background-size: 200vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: black;
}

h1 {
  font-family: Impact, Haettenschweiler, "Arial Narrow Bold", sans-serif;
  font-size: 25vh;
  color: brown;
}
</style>
