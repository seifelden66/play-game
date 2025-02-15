<template>
  <section class="global-section" ref="globalSection">
    <div class="global-container">
      <h2 class="global-heading">Truly Global, <br> Always Local.</h2>
      <p class="offices-subheading">With five offices spanning</p>

      <div class="center-stage">
        <!-- Location text (dynamically updated based on scroll thresholds) -->
        <div class="location-text">
          {{ currentLocation }}
        </div>
        <!-- Globe graphic (rotates as you scroll) -->
        <div class="globe-graphic">
          <img :src="globeSource" alt="Globe" :style="globeStyle" />
        </div>
      </div>
      <div class="sustainability-box">Sustainability <br> at Our Core</div>
      <p class="bottom-text">
        <span>
            We empower brands and investors
        </span> <br>
         to use their capital in ways that help athletes
        thrive and achieve their goals while enriching local communities through enhanced
        health, sports, and lifestyle initiatives.
      </p>
    </div>
  </section>
</template>

<script setup>
import { ref, computed, onMounted, onUnmounted } from "vue";

const globeSource = "/globe-ball.png";

const locations = [
  "North America (North Carolina)",
  "Europe (Germany)",
  "Asia (Indonesia)",
  "The Middle East (Egypt and Dubai)",
];

const angles = [-22.15, -6.17, 13.64, 19.78];

const currentIndex = ref(0);
const currentLocation = computed(() => locations[currentIndex.value]);
const currentAngle = computed(() => angles[currentIndex.value]);

const globeStyle = computed(() => ({
  transform: `rotate(${currentAngle.value}deg)`,
  transition: "transform 0.8s ease",
}));

// Reference to the section element
const globalSection = ref(null);

/**
 * Compute absolute scroll thresholds relative to the section’s top.
 *
 * Thresholds:
 * - North America: window.scrollY < sectionTop + (0.20 × vh)
 * - Europe:        sectionTop + (0.20 × vh) ≤ window.scrollY < sectionTop + (0.55 × vh)
 * - Asia:          sectionTop + (0.55 × vh) ≤ window.scrollY < sectionTop + (0.70 × vh)
 * - Middle East:   window.scrollY ≥ sectionTop + (0.70 × vh)
 */
function handleScroll() {
  if (!globalSection.value) return;
  const sectionTop = globalSection.value.offsetTop;
  const vh = window.innerHeight;

  // Updated thresholds: first threshold is now 0.20 * vh instead of 0.30 * vh.
  const threshold0 = sectionTop + 0.0 * vh;
  const threshold1 = sectionTop + 0.15 * vh;
  const threshold2 = sectionTop + 0.3 * vh;

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
  // Run initially in case the section is already in view
  handleScroll();
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>

<style scoped>
.global-section {
  margin-top: 200px;
  display: flex;
  align-items: center;
  height: 120vh;
  position: relative;
  padding: 1rem;
  color: #fff;
}

.global-container {
  max-width: 1200px;
  margin: 0 auto;
}

.global-heading {
  font-family: "Anton", sans-serif;
  font-size: 130px;
  text-align: center;
  margin: 0 0 0.5rem;
  line-height: 1.2;
}

.offices-subheading {
  font-family: "Poppins", sans-serif;
  font-size: 55px;
  text-align: center;
  margin: 0 0 3rem;
  color: #ccc;
}

.center-stage {
  position: relative;
  height: 400px;
}

.location-text {
  height: 60px;
  font-family: "Anton", sans-serif;
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
  right: -450px;
  width: 450px;
  height: auto;
}

.sustainability-box {
  border: 4px solid transparent;
  border-radius: 8px;
  padding:.5rem 8rem;
  background: linear-gradient(#070E58, #070E58) padding-box,
  linear-gradient(to left, #5bb507, #1859bb) border-box;
  color: #fff;
  font-family: "Poppins", sans-serif;
  font-size: 50px;
  font-weight: 700;
  /* text-transform: uppercase; */
  text-align: center;
  display: block; 
  margin: 5rem auto;
  width: fit-content;
}


.bottom-text {
  font-family: "Poppins", sans-serif;
  font-size: 1rem;
  color: #ccc;
  line-height: 1.5;
  max-width: 900px;
  margin: 5rem auto;
  text-align: center;
}
.bottom-text span{
    font-size: 2rem;
}
/* ========== Responsive Styles ========== */

@media (max-width: 768px) {
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
  .globe-graphic img {
    right: -200px;
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
  }
}

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
    right: -100px;
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
