<template>
  <div class="landing-page">
    <header class="top-header">
      <div class="header-content">
        <div class="logo">
          <img src="/gameplay.png" alt="" />
        </div>
        <nav class="menu">
          <ul>
            <li>
              <a href="#" @click.prevent="scrollToServices('athletes')">FOR ATHLETES</a>
            </li>
            <li>
              <a href="#" @click.prevent="scrollToServices('brands')">FOR BRANDS</a>
            </li>
            <li>
              <a href="#" @click.prevent="scrollToServices('investors')">FOR INVESTORS</a>
            </li>
            <li>
              <a href="#touch">GET IN TOUCH</a>
            </li>
          </ul>
        </nav>
      </div>
    </header>

    <section data-aos="zoom-in" :data-aos-duration="550" :data-aos-delay="200" class="hero-section">
      <img src="/vision.png" alt="" />
    </section>

    <section class="services-section">
      <div class="services-left">
        <ul class="services-bullets">
          <li :class="{ active: activeTab === 'athletes' }" @click="activeTab = 'athletes'">FOR ATHLETES</li>
          <li :class="{ active: activeTab === 'brands' }" @click="activeTab = 'brands'">FOR BRANDS</li>
          <li :class="{ active: activeTab === 'investors' }" @click="activeTab = 'investors'">FOR INVESTORS</li>
        </ul>
      </div>
      <div class="services-right">
        <div v-if="activeTab === 'athletes'">
          <h2>We Are Not Just Sports Agency; We Are Your Partners In Success.</h2>
        </div>
        <div v-else-if="activeTab === 'brands'">
          <h2>De-risk Your Athlete Sponsorships</h2>
        </div>
        <div v-else-if="activeTab === 'investors'">
          <h2>Invest in the Future of Sport, Wellness, and Lifestyle</h2>
        </div>
      </div>
    </section>
    <div class="text-from-sercvices">
      <span v-if="activeTab === 'brands'">
        Our unique athlete management system continuously aligns your message with the right athlete at the right time. As your brand and the world evolves, we help you pivot—maximizing impact and minimizing risk.
      </span>
      <span v-else-if="activeTab === 'investors'">
        We leverage our global network and unparalleled expertise to identify and invest in high-potential ventures across these thriving sectors. Our portfolio spans cutting-edge technology, sports nutrition, wellness, and beyond.
      </span>
    </div>
    <agency-section />
    <stats-section />
    <globe-section />
    <contact-section id="touch" />
    <footer-section />
  </div>
</template>

<script>
import AOS from "aos";
import "aos/dist/aos.css";
import ContactSection from "./components/ContactSection.vue";
import FooterSection from "./components/FooterSection.vue";
import AgencySection from "./components/AgencySection.vue";
import StatsSection from "./components/StatsSection.vue";
import GlobeSection from "./components/GlobeSection.vue";

export default {
  name: "LandingPage",
  components: {
    ContactSection,
    FooterSection,
    AgencySection,
    StatsSection,
    GlobeSection,
  },
  data() {
    return {
      activeTab: "brands",
    };
  },
  mounted() {
    AOS.init();
  },
  methods: {
    scrollToServices(tab) {
      this.activeTab = tab;
      const servicesEl = this.$el.querySelector(".services-section");
      if (servicesEl) {
        servicesEl.scrollIntoView({
          behavior: "smooth",
          block: "start",
        });
      }
    },
  },
};
</script>

<style scoped>
@font-face {
  font-family: "Heading Now Trial";
  src: url("./assets/fonts/HeadingNowTrial-Black.woff2") format("woff2"),
      url("./assets/fonts/HeadingNowTrial-Black.woff") format("woff");
  font-weight: 900;
  font-style: normal;
}

.landing-page {
  margin: 0 !important;
  padding: 0 !important;
  min-height: 100vh;
  color: #fff;
  font-family: "Anton", sans-serif;
  /* background: #0b1120; */
  overflow-x: hidden;
}

.top-header {
  box-sizing: border-box;
  padding-top: 70px;
}

.header-content {
  border: 4px solid transparent;
  border-radius: 15px;
  background: linear-gradient(#0b1120, #0b1120) padding-box, linear-gradient(to left, #5bb507, #1859bb) border-box;
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
  width: 200px;
  text-transform: uppercase;
}
.logo img {
  width: 100%;
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
  padding: 5rem 1rem;
}
.hero-section img {
  width: 100%;
  max-width: 800px;
  display: block;
  margin: 0 auto;
}

.hero-text {
  margin: 0;
  font-family: "Heading Now Trial", sans-serif;
  font-size: clamp(4rem, 10vw, 523px);
  font-weight: 900;
  line-height: 547px;
  text-transform: uppercase;
  background: linear-gradient(180deg, #ffffff 0%, #cccccc 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.animated-text {
  display: block;
  font-family: "Heading Now Trial", sans-serif;
  font-size: clamp(3rem, 15vw, 837px);
  font-weight: 900;
  line-height: 0.9;
  text-transform: uppercase;
  background: linear-gradient(180deg, #ffffff 0%, #cccccc 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.services-section {
  max-width: 1130px;
  margin: 0 auto;
  padding: 3rem 2rem;
  display: flex;
  gap: 9rem;
  font-family: "Poppins", sans-serif;
}

.text-from-sercvices {
  text-align: center;
  text-transform: uppercase;
  width: 100%;
  max-width: 1130px;
  margin: 0 auto;
  color: #fff;
  font-size: 37px;
  padding: 2rem 0.5rem;
  font-family: "Poppins", sans-serif;
  margin-bottom: 1rem;
  font-weight: 400;
  transition: color 0.2s;
}

.services-left {
  flex: 1;
}

.services-bullets {
  list-style: none;
  margin: 0;
  padding: 0;
  line-height: 1.8;
  white-space: nowrap;
  overflow: hidden;
}

.services-bullets li {
  cursor: pointer;
  font-size: 27px;
  margin-bottom: 1rem;
  text-transform: uppercase;
  font-weight: 400;
  color: rgba(124, 124, 124, 0.51);
  transition: color 0.2s;
}

.services-bullets li::before {
  content: "— ";
}

.services-bullets li.active {
  color: #fff;
  font-size: 37px;
  margin-left: 20px;
}

.services-right {
  flex: 3;
}

.services-right h2 {
  font-family: "Anton", sans-serif;
  font-size: 2rem;
  color: #fff;
  margin-bottom: 1rem;
}

.services-right p {
  font-family: "Poppins", sans-serif;
  font-size: 1rem;
  color: #ccc;
  line-height: 1.5;
  margin: 0;
}

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
  .services-section {
    flex-direction: column;
    gap: 2rem;
    padding: 2rem 1rem;
  }
  .services-bullets li {
    font-size: 22px;
    margin-bottom: 0.75rem;
  }
  .services-bullets li.active {
    font-size: 30px;
    margin-left: 10px;
  }
  .services-right h2 {
    font-size: 1.8rem;
  }
  .text-from-sercvices {
    font-size: 30px;
    padding: 1.5rem 0.5rem;
  }
}
@media (max-width: 480px) {
  .header-content {
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
  .services-section {
    padding: 1.5rem 1rem;
  }
  .services-bullets li {
    font-size: 18px;
    margin-bottom: 0.5rem;
  }
  .services-bullets li.active {
    font-size: 26px;
    margin-left: 8px;
  }
  .services-right h2 {
    font-size: 1.6rem;
  }
  .text-from-sercvices {
    font-size: 24px;
    padding: 1rem 0.5rem;
  }
}
</style>
