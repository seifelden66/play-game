<template>
  <section class="global-section" ref="globalSection">
    <div class="global-container">
      <h2 class="global-heading">
        Truly Global, <br />
        Always Local.
      </h2>
      <p class="offices-subheading">With five offices spanning</p>

      <div class="center-stage">
        <div class="location-text" v-html="currentLocation"></div>
        <div class="globe-graphic">
          <img :src="globeSource" alt="Globe" :style="globeStyle" />
        </div>
      </div>
      <div class="cont">
        <img src="/top-sust.png" alt="" />
        <div class="sus2">
          <img src="/sus-top2.png" alt="" />
        </div>
      </div>
      <div class="sus-mid">
        <img src="/sus-mid.png" alt="" />
      </div>
      <div class="sus-last">
        We Empower Brands <br /> And Investors
        <div class="inside">
          to use their capital in ways that help athletes thrive and achieve their goals
          while enriching local communities through enhanced health, sports, and lifestyle
          initiatives.
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, computed, onMounted, onUnmounted } from "vue";

const globeSource = "/globe-ball.png";

const locations = [
  "North America<br>(North Carolina)",
  "Europe<br>(Germany)",
  "Asia<br>(Indonesia)",
  "The Middle East<br>(Egypt and Dubai)",
];

const angles = [-22.15, -6.17, 13.64, 19.78];

const currentIndex = ref(0);
const currentLocation = computed(() => locations[currentIndex.value]);
const currentAngle = computed(() => angles[currentIndex.value]);

const globeStyle = computed(() => ({
  transform: `rotate(${currentAngle.value}deg)`,
  transition: "transform 0.8s ease",
}));

const globalSection = ref(null);

function handleScroll() {
  if (!globalSection.value) return;
  const sectionTop = globalSection.value.offsetTop;
  const vh = window.innerHeight;

  // Thresholds for four regions
  const threshold0 = sectionTop + 0.1 * vh;
  const threshold1 = sectionTop + 0.25 * vh;
  const threshold2 = sectionTop + 0.35 * vh;
  const scrollY = window.scrollY;

  if (scrollY < threshold0) {
    currentIndex.value = 0;
  } else if (scrollY < threshold1) {
    currentIndex.value = 1;
  } else if (scrollY < threshold2) {
    currentIndex.value = 2;
  } else {
    currentIndex.value = 3;
  }
}

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
  handleScroll();
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>

<style scoped>
.cont {
  margin-top: 200px;
  /* height: 400px; */
  width: 120%;
  margin-left: -150px;
  position: relative;
}
.cont img {
  left: 0;
  width: 100%;
}
.global-section {
  margin-top: 200px;
  display: flex;
  align-items: center;
  /* height: 120vh; */
  position: relative;
  padding: 1rem;
  color: #fff;
}

.global-container {
  /* max-width: 1200px; */
  margin: 0 auto;
}

.global-heading {
  font-size: 144px;
  text-align: center;
  margin: 0 0 0.5rem;
  line-height: 1.2;
}

.offices-subheading {
  font-size: 55px;
  text-align: center;
  margin: 0 0 3rem;
  color: #ccc;
}

.center-stage {
  position: relative;
  height: 200px;
}
.sus2{
  margin-top: -250px;
  margin-bottom: 100px;
  /* color: #F0EFEF; */
  opacity: .5;
  z-index: -9999;
}
.location-text {
  height: 60px;
  font-size: 95px;
  margin: 0;
  line-height: 1.2;
  position: absolute;
  left: 0;
  top: 50%;
  transform: translateY(-50%);
}

.globe-graphic img {
  position: absolute;
  right: -300px;
  width: 450px;
  height: auto;
}

.sus-last {
  /* Large white box */
  background: #fff;
  color: #000; /* black text */
  font-size: clamp(32px, 4vw, 56.5px);
  font-weight: 700;
  text-align: center;
  line-height: 1.2;
  letter-spacing: 0;
  border-radius: 37px;
  
  /* Remove hard-coded width/height/positioning; make it responsive */
  max-width: 963px; /* or any suitable max-width */
  margin: 4rem auto; /* center horizontally with spacing above/below */
  padding: 3rem 2rem; /* spacing inside the box */
  
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
}

.inside {
  /* Smaller green box inside */
  background: #5bb507;
  color: #fff;
  font-weight: 400;
  font-size: clamp(16px, 2vw, 24px);
  line-height: 1.4;
  letter-spacing: 0;
  text-align: center;
  
  /* Rounded corners */
  border-radius: 63.5px;
  
  /* Responsive sizing */
  max-width: 860px; /* narrower than .sus-last so it looks inset */
  width: 100%;
  margin: 0 auto; /* center inside .sus-last */
  padding: 2rem; /* space around the text */
}

.sustainability-box {
  border: 4px solid transparent;
  border-radius: 8px;
  padding: 0.5rem 8rem;
  background: linear-gradient(#070e58, #070e58) padding-box,
    linear-gradient(to left, #5bb507, #1859bb) border-box;
  color: #fff;
  font-size: 50px;
  font-weight: 700;
  text-align: center;
  display: block;
  margin: 15rem auto;
  margin-bottom: 135px;
  width: fit-content;
}

.bottom-text {
  font-size: 38.75px;
  color: #ccc;
  line-height: 1.4;
  /* max-width: 900px; */
  margin: 5rem auto;
  text-align: center;
}

.bottom-text span {
  font-size: 52px;
}

/* Responsive for medium screens (up to 1024px) */
@media (min-width: 1440px) {
  .globe-graphic img {
    /* right: -300px; */
  }
}
@media (max-width: 1024px) {
  .global-heading {
    font-size: 120px;
  }
  .offices-subheading {
    font-size: 45px;
    margin-bottom: 2rem;
  }
  .center-stage {
    height: 250px;
  }
  .location-text {
    font-size: 80px;
    left: 1rem;
  }
  .globe-graphic img {
    right: -250px;
    top: 10%;
    width: 350px;
  }
  .sustainability-box {
    font-size: 45px;
    margin: 80px auto 1rem;
    padding: 0.8rem 1.5rem;
  }
  .bottom-text {
    font-size: 0.95rem;
    max-width: 95%;
  }
}

/* Responsive for small screens (up to 768px) */
@media (max-width: 768px) {
  .sus-mid img{
    width: 100%;
  }
  .global-section {
    overflow-x: hidden;
    height: auto;
    padding: 2rem 1rem;
  }
  .global-heading {
    font-size: 80px;
  }
  .offices-subheading {
    font-size: 35px;
    margin-bottom: 2rem;
  }
  .center-stage {
    height: 220px;
  }
  .location-text {
    font-size: 50px;
    left: 1rem;
  }
  .sus2{
  margin-top: 0px;
  margin-bottom: 0px;
  /* color: #F0EFEF; */
  opacity: .5;
  z-index: -9999;
}
  .inside{
    padding: 20px;
    width: auto;
  }
  .cont {
  margin-top: 200px;
  /* height: 400px; */
  margin-bottom: 200px;
  width: 150%;
  margin-left: -100px;
  position: relative;
}
.cont img {
  left: 0;
  width: 100%;
}
  .globe-graphic img {
    right: -250px;
    top: 10%;
    width: 300px;
  }
  .sustainability-box {
    font-size: 60px;
    margin: 80px auto 1rem;
    padding: 0.8rem 1.5rem;
  }
  .bottom-text {
    font-size: 0.9rem;
    max-width: 90%;
    margin: 1rem auto;
  }
}

/* Responsive for extra small screens (up to 480px) */
@media (max-width: 480px) {
  .global-heading {
    font-size: 60px;
  }
  .offices-subheading {
    font-size: 28px;
    margin-bottom: 1.5rem;
  }
  .center-stage {
    height: 180px;
  }
  .location-text {
    font-size: 35px;
    left: 0.5rem;
  }
  .globe-graphic img {
    right: -150px;
    top: 8%;
    width: 220px;
  }
  .sustainability-box {
    font-size: 45px;
    margin: 60px auto 1rem;
    padding: 0.5rem 1rem;
  }
  .bottom-text {
    font-size: 0.8rem;
    max-width: 95%;
  }
}
</style>
