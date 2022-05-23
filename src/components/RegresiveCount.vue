<template>
  <div>
    <div>
      <h1>{{ x }}</h1>
    </div>
    <h1>:</h1>
    <div>
      <h1>{{ y }}</h1>
    </div>
  </div>
</template>

<script>
export default {
  name: "RegresiveCount",

  data() {
    return {
      x: this.timex,
      y: "00",
      s: "",

      bool: true,
    };
  },

  props: {
    timex: Number,
  },
  mounted() {
    this.time(this.timex);
  },

  methods: {
    time(x) {
      if (this.bool == true) {
        let i = x - 1;
        let j = 59;
        const timeInterval = setInterval(() => {
          if (j < 0) {
            i -= 1;

            j = 59;
          }

          if (j == 0 && i <= 0) {
            i = "POOO PO POO";
            j = "POOO PO POO";
            clearInterval(timeInterval);
          }

          console.log(" lol ");
          this.x = i;
          this.y = j;

          if (this.y < 10) {
            this.y = "0" + this.y;
          }
          j--;
        }, 1000);
      }
      this.bool = false;
    },
  },
};

/*  setTimeout(function () {
            console.log("Hola Mundo");
          }, 1000); */
</script>

<style scoped>
h1 {
  color: aliceblue;
  font-size: 40vh;
}
</style>
