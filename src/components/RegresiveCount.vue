<template>
  <div>
    <div>
      <h1>{{ x }}</h1>
    </div>
    <h1>:</h1>
    <div>
      <h1>
        {{ y }}
      </h1>
    </div>

    <Transition>
      <h3 v-if="show">{{ s }}</h3>
    </Transition>
  </div>
</template>

<script>
export default {
  name: "RegresiveCount",

  data() {
    return {
      show: false,
      x: this.timex,
      y: "00",
      s: "",
      porgusto: "",
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
            this.show = true;
            this.s = "La rifa comenzará en breve...";
            setTimeout(() => {
              this.$emit("terminado");
            }, 2000);

            clearInterval(timeInterval);
          }

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

.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>
