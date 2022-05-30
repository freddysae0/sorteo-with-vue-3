<template>
  <div class="centered">
    <h3>{{ x }}</h3>
    <button class="btn-31" @click="toTruePara">
      <span class="text-container">
        <span class="text">{{ this.para ? "Comenzar" : "Parar" }}</span>
      </span>
    </button>
    <div class="winers-container">
      <div class="winers">
        <ul>
          <li v-for="winer in winers">
            <p>{{ winer }}</p>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>



export default {
  data() {
    return {
      x: 0,
      para: false,
      winers: [],
    };
  },
  props: {
    min: Number,
    max: Number,
  },
  mounted() {
    this.numberLoop();
    /* this.Cooonfetti(); */
  },
  methods: {
    Cooonfetti() {
      setInterval(() => {
        this.initConfetti();
      }, 3500);
    },


    initConfetti() {
      const jsConfetti = new JSConfetti()
      jsConfetti.addConfetti()
    },
    randNumber() {
      this.x = Math.random() * (this.max - this.min) + this.min;
      this.x = parseInt(this.x);
    },
    toTruePara() {
      this.para = !this.para;
      if (this.para == false) {
        this.numberLoop();
      }
      if (this.para == true) {
        this.initConfetti();
      }
    },
    numberLoop() {
      let timeInterval = setInterval(() => {
        this.randNumber();
        if (this.para) {
          this.winers.push(this.x);
          console.log(this.winers[0]);
          clearInterval(timeInterval);
        }
      }, 50);
    },
  },
};
</script>

<style scoped>
div {
  font-size: 20vh;
}

.centered {
  width: 600px;
  /* padding-top: 20vh; */
  /* margin-bottom: 200vh; */
  height: fit-content;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  /* justify-content: space-evenly; */
}

.winers-container {
  width: 50vh;
}

h3 {
  font-size: 18vh;
  margin: 0;
  margin: 20vh 0 40px;
}

.winers {
  font-size: medium;
}

ul {
  list-style: none;
  display: flex;
  flex-direction: column;
  align-items: center;

  margin: 0;
  padding: 0;
}

p {
  font-size: 2vh;
}

.btn-31 {
  margin-left: 20%;
  margin-right: 20%;
  margin-bottom: 25px;
  cursor: pointer;
  display: flex;
  justify-content: center;
  box-sizing: border-box;
  /* height: 10vh;
  width: 30vh; */
  /* padding: 1.5rem 3.5rem; */

  position: relative;

  background: none;
  color: white;

  text-transform: uppercase;
  border: 1px solid currentColor;

  --progress: 100%;
}

.btn-31:before {
  content: "";
  z-index: -1;

  position: absolute;
  inset: 0;

  background: white;
  clip-path: polygon(100% 0,
      var(--progress) var(--progress),
      0 100%,
      100% 100%);
  transition: clip-path 0.2s;
}

.btn-31:hover {
  --progress: 0%;
  color: black;
}

.btn-31 .text-container {
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  overflow: hidden;
  padding: 10px;
  width: 30vh;
}

.btn-31 .text {
  display: flex;
  position: relative;
  font-size: 5vh;
  font-weight: 900;
  /* mix-blend-mode: difference; */
}

.btn-31:hover .text {
  animation: move-up-alternate 0.3s forwards;
  will-change: transform;
}

@keyframes move-up-alternate {
  from {
    transform: translateY(0%);
  }

  50% {
    transform: translateY(80%);
  }

  51% {
    transform: translateY(-80%);
  }

  100% {
    transform: translateY(0%);
  }
}
</style>
