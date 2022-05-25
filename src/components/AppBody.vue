<template>
  <div id="body">
    <section id="uno" class="muestra">
      <regresive-count :timex="1" @terminado="eventStart()"></regresive-count>
    </section>

    <section id="dos">
      <body-carousel :min="0" :max="100000"></body-carousel>
    </section>
  </div>
</template>

<script>
import RegresiveCount from "./RegresiveCount.vue";
import BodyCarousel from "./BodyCarousel.vue";
export default {
  el: "#body",
  name: "Body",
  components: {
    RegresiveCount,
    BodyCarousel,
  },
  data() {
    return {
      z: 0,
    };
  },
  methods: {
    eventStart() {
      console.log(" el evento funciona");
      var x = document.getElementById("uno");
      x.className = "";
      var x = document.getElementById("dos");
      x.className = "muestra";

      this.time_to_rifa = true;
    },
  },
};
</script>

<style scoped>
div {
  height: 100vh;
 /*  display: flex;
  justify-content: center;
  align-items: center; */
}

h1 {
  font-family: Impact, Haettenschweiler, "Arial Narrow Bold", sans-serif;
  font-size: 25vh;
  color: brown;
}

html,
body,
#uno {
  height: 100%;
  
  width: 100%;
  overflow: hidden;
  margin: 0;
  padding: 0;
  background-color: #0099cc;
  color: #fff;
  font-family: Helvetica;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  height: fit-content;
}

#dos {
  height: 100%;
  
  width: 100%;
  overflow: hidden;
  margin: 0;
  padding: 0;
  background-color: #0099cc;
  color: #fff;
  font-family: Helvetica;
  display: flex;
  justify-content: center;
  text-align: center;
  height: fit-content;
}



h1 {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  text-align: center;
  width: 100%;
  font-size: 90px;
  margin: 0;
}

a {
  position: absolute;
  color: #0099cc;
  background-color: #fff;
  text-decoration: none;
  padding: 5px 15px;
  border-radius: 10px;
  font-size: 20px;
  bottom: 20px;
  left: 50%;
  transform: translateX(-50%);
}

#dos {
  background-color: #15b22f;
}

#dos a {
  color: #15b22f;
}

#uno.muestra,
#dos.muestra {
  position: absolute;
  top: 0;
  z-index: 1;
  transform-origin: top center;
  animation: iconosani 1.2s forwards;
}

@keyframes iconosani {
  0% {
    transform: perspective(800px) rotateX(-90deg);
    opacity: 1;
  }
  40% {
    transform: perspective(800px) rotateX(30deg);
    opacity: 1;
  }
  70% {
    transform: perspective(800px) rotateX(-10deg);
  }
  100% {
    transform: perspective(800px) rotateX(0deg);
    opacity: 1;
  }
}
</style>
