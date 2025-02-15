<template>
  <div class="landing-page">
    <header class="top-header">
      <div class="header-content">
        <div class="logo">GAME<br />PLAN.</div>
        <nav class="menu">
          <ul>
            <li><a href="#">FOR ATHLETES</a></li>
            <li><a href="#">FOR BRANDS</a></li>
            <li><a href="#">FOR INVESTORS</a></li>
            <li><a href="#">GET IN TOUCH</a></li>
          </ul>
        </nav>
      </div>
    </header>

    <section class="hero-section">
      <div class="hero-text">
        <span>YOUR VISION</span>
      </div>
      <div
        data-aos="fade-up"
        :data-aos-duration="550"
        :data-aos-delay="300"
        class="animated-text"
      >
        OUR GAMEPLAN
      </div>
    </section>
    
    <services-section />
    <agency-section />
    <stats-section />
    <globe-section />
    <contact-section />
    <footer-section />
  </div>
</template>

<script>
import AOS from "aos";
import "aos/dist/aos.css";
import ContactSection from "./components/ContactSection.vue";
import FooterSection from "./components/FooterSection.vue";
import ServicesSection from "./components/ServicesSection.vue";
import AgencySection from "./components/AgencySection.vue";
import StatsSection from "./components/StatsSection.vue";
import GlobeSection from "./components/GlobeSection.vue";

export default {
  components: {
    ContactSection,
    FooterSection,
    ServicesSection,
    AgencySection,
    StatsSection,
    GlobeSection,
  },
  name: "LandingPage",

  mounted() {
    AOS.init();
  },
};
</script>

<style scoped>
.landing-page {
  margin: 0 !important;
  padding: 0 !important;
  min-height: 100vh;
  color: #fff;
  font-family: "Anton", sans-serif;
}

.top-header {
  box-sizing: border-box;
  padding-top: 70px;
}

.header-content {
  border: 4px solid transparent;
  border-radius: 15px;
  background: linear-gradient(#0b1120, #0b1120) padding-box,
    linear-gradient(to left, #5bb507, #1859bb) border-box;
  background-clip: padding-box, border-box;
  display: flex;
  align-items: center;
  justify-content: space-between;
  max-width: 983px;
  height: 59px;
  margin: 0 auto;
  padding: 1rem 2rem;
}

.logo {
  font-size: 1.5rem;
  line-height: 1.1;
  font-weight: 700;
  color: #fff;
  text-transform: uppercase;
}

.menu ul {
  list-style: none;
  display: flex;
  gap: 2rem;
  margin: 0;
  padding: 0;
}

.menu li a {
  color: #fff;
  text-decoration: none;
  text-transform: uppercase;
  font-weight: 400;
  font-size: 0.9rem;
}

.hero-section {
  text-align: center;
  padding: 14rem 1rem;
}

.hero-text {
  margin: 0;
  font-size: 10vw;
  font-weight: 900;
  line-height: 0.9;
  text-transform: uppercase;
  background: linear-gradient(180deg, #ffffff 0%, #cccccc 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.animated-text {
  display: block;
  margin-top: 25vh;
  font-size: 10vw;
  font-weight: 900;
  line-height: 0.9;
  text-transform: uppercase;
  background: linear-gradient(180deg, #ffffff 0%, #cccccc 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

/* Responsive Styles */

@media (max-width: 768px) {
  .header-content {
    max-width: 90%;
    padding: 0.5rem 1rem;
    height: auto;
    flex-wrap: wrap;
  }
  .logo {
    font-size: 1.2rem;
  }
  .menu ul {
    gap: 1rem;
  }
  .menu li a {
    font-size: 0.8rem;
  }
  .hero-section {
    padding: 8rem 1rem;
  }
  .hero-text,
  .animated-text {
    font-size: 12vw;
  }
}

@media (max-width: 480px) {
  .header-content {
    /* flex-direction: column; */
    align-items: center;
    height: auto;
  }
  .logo {
    margin-bottom: 1rem;
  }
  .menu ul {
    flex-direction: column;
    gap: 0.5rem;
  }
  .hero-section {
    padding: 6rem 1rem;
  }
  .hero-text,
  .animated-text {
    font-size: 16vw;
  }
}
</style>
