<template>
    <section class="global-section">
      <div class="global-container">
        <h2 class="global-heading">Truly Global, Always Local.</h2>
        <p class="offices-subheading">With five offices spanning</p>
  
        <div class="center-stage">
          <!-- Location text (dynamically updated) -->
          <div class="location-text">
            {{ currentLocation }}
          </div>
          <!-- Globe graphic (rotates on click) -->
          <div class="globe-graphic">
            <img
              :src="globeSource"
              alt="Globe"
              @click="handleGlobeClick"
              :style="globeStyle"
            />
          </div>
        </div>
        <div class="sustainability-box">SUSTAINABILITY AT OUR CORE</div>
        <p class="bottom-text">
          We empower brands and investors to use their capital in ways that help athletes
          thrive and achieve their goals while enriching local communities through enhanced
          health, sports, and lifestyle initiatives.
        </p>
      </div>
    </section>
  </template>
  
  <script setup>
  import { ref, computed } from 'vue';
  
  /* Use one globe image file */
  const globeSource = '/globe-ball.png';
  
  /* Array of location labels */
  const locations = [
    'North America (North Carolina)',
    'Europe (Germany)',
    'Asia (Indonesia)',
    'The Middle East (Egypt and Dubai)',
  ];
  
  /* Array of rotation angles (in degrees) corresponding to each region */
  const angles = [-22.15, -6.17, 13.64, 19.78];
  
  /* Track the current index */
  const currentIndex = ref(0);
  
  /* On each click, move to the next state (wrap around via modulo) */
  function handleGlobeClick() {
    currentIndex.value = (currentIndex.value + 1) % locations.length;
  }
  
  /* Computed properties for current location and angle */
  const currentLocation = computed(() => locations[currentIndex.value]);
  const currentAngle = computed(() => angles[currentIndex.value]);
  
  /* Computed style for the globe that only applies rotation */
  const globeStyle = computed(() => ({
    transform: `rotate(${currentAngle.value}deg)`,
    transition: 'transform 0.8s ease',
    cursor: 'pointer',
  }));
  </script>
  
  <style scoped>
  .global-section {
    margin-top: 50px;
    display: flex;
    align-items: center;
    height: 120vh;
    position: relative;
    padding: 1rem 1rem;
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
    height: 300px; /* Adjust if needed */
  }
  
  .location-text {
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
    /* Fixed position: always at right -450px and top 15% on desktop */
    right: -450px;
    top: 15%;
    width: 450px;
    height: auto;
  }
  
  .sustainability-box {
    border: 4px solid #5bb507;
    border-radius: 8px;
    padding: 1rem 2rem;
    font-family: "Anton", sans-serif;
    font-size: 100px;
    font-weight: 700;
    text-transform: uppercase;
    color: #fff;
    text-align: center;
    display: inline-block;
    margin: 150px auto 2rem;
    width: fit-content;
  }
  
  .bottom-text {
    font-family: "Poppins", sans-serif;
    font-size: 1rem;
    color: #ccc;
    line-height: 1.5;
    max-width: 900px;
    margin: 0 auto;
    text-align: center;
  }
  
  /* ========== Responsive Styles ========== */
  
  /* Tablets (max-width: 768px) */
  @media (max-width: 768px) {
    .global-section {
      height: auto; /* Let content define the height */
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
  
  /* Mobile (max-width: 480px) */
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
  