<script setup>
import Typed from "typed.js";
import { onMounted, ref } from "vue";

const typedTarget = ref(null);

onMounted(() => {
  new Typed(typedTarget.value, {
    strings: [
      "Back-End Developer",
      "Software Developer",
      "Data Analyst",
      "Cryptanalyst",
    ],
    typeSpeed: 50,
    backSpeed: 30,
    loop: true,
  });
});
</script>

<template>
  <section class="home-section" id="home">
    <div class="overlay"></div>
    <div class="container" data-aos="fade-up" data-aos-delay="100">
      <h2>I am Billy Terante</h2>
      <p><span ref="typedTarget" class="typed"></span></p>
    </div>
  </section>
</template>

<style scoped>
.home-section {
  position: relative;
  height: 100vh;
  width: 100vw;
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
  background-image: url("/src/assets/img/Technology background 2.jpg");
  background-size: cover;
  background-position: center;
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.7);
  z-index: 1;
}

.container {
  position: relative;
  z-index: 2;
  color: white;
  text-align: center;
  padding: 0 20px;
  max-width: 90%;
}

h2 {
  font-size: 3vw;
  margin: 0;
}

.typed {
  font-size: 2vw;
  color: white;
}

@media (max-width: 1024px) {
  .home-section {
    background-size: cover;
  }

  h2 {
    font-size: 6vw;
  }
  .typed {
    font-size: 5vw;
  }
}

@media (max-width: 768px) {
  .home-section {
    background-size: scroll;
  }

  h2 {
    font-size: 5vw;
  }
  .typed {
    font-size: 4vw;
  }
}

@media (max-width: 480px) {
  .home-section {
    background-size: cover;
    background-position: center top;
  }

  h2 {
    font-size: 4vw;
  }
  .typed {
    font-size: 3vw;
  }
}
</style>
