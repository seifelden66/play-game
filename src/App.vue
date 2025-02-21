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
    <div class="hero-section">
      <!-- <img src="/your-vision.png" alt="" /> -->
      YOUR VISION
      <div>
        <section
          class="gameplan"
          data-aos="zoom-in"
          data-aos-duration="370"
          data-aos-delay="100"
        >
          OUR GAMEPLAN
        </section>
      </div>
    </div>

    <section class="services-section">
      <div class="services-left">
        <ul class="services-bullets">
          <li
            :class="{ active: activeTab === 'athletes' }"
            @click="activeTab = 'athletes'"
          >
            FOR ATHLETES
          </li>
          <li :class="{ active: activeTab === 'brands' }" @click="activeTab = 'brands'">
            FOR BRANDS
          </li>
          <li
            :class="{ active: activeTab === 'investors' }"
            @click="activeTab = 'investors'"
          >
            FOR INVESTORS
          </li>
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
        Our unique athlete management system continuously aligns your message with the
        right athlete at the right time. As your brand and the world evolves, we help you
        pivot—maximizing impact and minimizing risk.
      </span>
      <span v-else-if="activeTab === 'investors'">
        We leverage our global network and unparalleled expertise to identify and invest
        in high-potential ventures across these thriving sectors. Our portfolio spans
        cutting-edge technology, sports nutrition, wellness, and beyond.
      </span>
    </div>
    <agency-section v-if="activeTab === 'athletes'" />
    <stats-section />
    <sports-section />

    <globe-section />
    <contact-section id="touch" />
    <footer class="footer-section">
      <div class="footer-top">
        <div class="footer-left">
          <div class="logo-box">
            <!-- <div class="logo-outline">
            <span class="logo-text">GAME<br />PLAN</span>
          </div> -->
            <!-- <div class="tagline">YOUR VISION,<br />OUR GAMEPLAN.</div> -->
            <img src="/logo-footer.png" alt="" />
          </div>
        </div>
        <div class="footer-center">
          <h3>COMPANY</h3>
          <ul>
            <li>
              <a href="#tocuh" @click.prevent="scrollToServices('athletes')"
                >For Athletes</a
              >
            </li>
            <li>
              <a href="#tocuh" @click.prevent="scrollToServices('brands')">For Brands</a>
            </li>
            <li>
              <a href="#tocuh" @click.prevent="scrollToServices('investors')"
                >For Investors</a
              >
            </li>
          </ul>
        </div>
        <div class="footer-right">
          <div class="social-icons">
            <a
              href=" https://www.facebook.com/share/15WJRqwyGF/?mibextid=wwXIfr"
              class="icon"
            target="_blank"
            >
              <IconsFace />
            </a>
            <a
              href="https://www.instagram.com/gameeplan?igsh=NnBlNDljZnpvNDV3"
              class="icon"
            target="_blank"
            >
              <IconsInsta />
            </a>
            <a
              href="https://www.tiktok.com/@gameeplan?_t=ZS-8tSB3EiKl2m&_r=1&fbclid=PAZXh0bgNhZW0CMTEAAaaNE64ESJ-0jPRlkuXYzCHMKtuj6IVZxkTngrx0-fVS9sn8xYXfPIXjUJM_aem_g-azUlocdmEr1vwgLqwdjQ"
              class="icon"
            target="_blank"
            >
              <IconsTiktok />
            </a>
            <a
            target="_blank"
              href="https://www.tiktok.com/@gameeplan?_t=ZS-8tSB3EiKl2m&_r=1&fbclid=PAZXh0bgNhZW0CMTEAAaaNE64ESJ-0jPRlkuXYzCHMKtuj6IVZxkTngrx0-fVS9sn8xYXfPIXjUJM_aem_g-azUlocdmEr1vwgLqwdjQ"
              class="icon"
            >
              <IconsLinked />
            </a>
            <!-- <img src="/icons.png" alt="" /> -->
          </div>
        </div>
      </div>
      <div class="footer-divider"></div>
      <div class="footer-bottom">
        <p>© 2025 Gameplan. All Rights Reserved.</p>
        <div class="footer-links">
          <a href="#">Privacy Policy</a>
          <a href="#">Cookie Policy</a>
        </div>
      </div>
    </footer>
    <div class="ffoter">
      <a href="#touch"> GET IN TOUCH WITH US </a>
    </div>
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
import SportsSection from "./components/SportsSection.vue";
import IconsFace from "./components/Icons/Face.vue";
import IconsInsta from "./components/Icons/Insta.vue";
import IconsTiktok from "./components/Icons/Tiktok.vue";
import IconsLinked from "./components/Icons/Linked.vue";

export default {
  name: "LandingPage",
  components: {
    ContactSection,
    FooterSection,
    AgencySection,
    StatsSection,
    GlobeSection,
    SportsSection,
    IconsFace,
    IconsInsta,
    IconsTiktok,
    IconsLinked,
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
  /* background: #0b1120; */
  overflow-x: hidden;
}

.top-header {
  box-sizing: border-box;
  padding-top: 20px;
}

.header-content {
  border: 4px solid transparent;
  border-radius: 15px;
  background: linear-gradient(#000, #000) padding-box,
    linear-gradient(to left, #5bb507, #1859bb) border-box;
  background-clip: padding-box, border-box;
  display: flex;
  align-items: center;
  justify-content: space-between;
  max-width: 983px;
  height: 50px;
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
  font-weight: 700;
  /* font-size: 0.9rem; */
}
.menu li a:hover {
  color: #5bb507;
}

.hero-section {
  text-align: center;
  padding: 10rem 1rem;
  font-family: "Glacial Indifference", sans-serif !important; /* Force override */
  font-weight: 700;
  font-size: 106.13px;
  line-height: 155px;
}

section.gameplan {
  display: block;
  margin-top: 55px;
  display: inline-block;
  font-weight: 700;
  font-size: clamp(100px, 10vw, 150px);
  line-height: 143px;
  text-align: center;
  background: linear-gradient(180deg, #ffffff 0%, #4f5076 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.hero-section img:nth-child(2) {
  width: 100%;
}

.services-section {
  max-width: 1130px;
  margin: 0 auto;
  padding: 3rem 2rem;
  display: flex;
  gap: 9rem;
}

.text-from-sercvices {
  text-align: center;
  /* text-transform: uppercase; */
  width: 100%;
  max-width: 1130px;
  margin: 0 auto;
  color: #fff;
  font-size: 37px;
  padding: 2rem 0.5rem;
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
  position: relative; /* Required for the pseudo-element positioning */
  z-index: 0;
  border-radius: 8px;
  padding: 5px 10px;
  cursor: pointer;
  font-size: 27px;
  margin-bottom: 1rem;
  text-transform: uppercase;
  font-weight: 700;
  color: rgba(124, 124, 124, 0.51);
  transition: color 0.2s;
  background: transparent; /* Preserve the original background */
}

/* Create a pseudo-element to simulate the gradient border */
/* Remove the general ::before from all li */
.services-bullets li::before {
  content: none;
}

/* Style the active item itself */
.services-bullets li.active {
  position: relative; /* Needed for absolutely positioned ::before */
  margin-left: 20px;
  color: #fff;
  font-size: 37px;

  /* Increase padding as desired */
  /* padding: 0.5rem; */
  width: 283px;
  height: 67px;
  /* Apply a 15px border radius to the active item */
  border-radius: 15px;
}

.services-bullets li.active::before {
  content: "";
  position: absolute;
  inset: 0; /* top: 0; right: 0; bottom: 0; left: 0; */
  border-radius: inherit; /* Inherit the 15px radius from the parent */
  padding: 2px; /* Border thickness (keep the same if you want the same thickness) */
  background: linear-gradient(to right, #0032ff, #00ff3c);

  -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  -webkit-mask-composite: xor;
  mask-composite: exclude;

  z-index: -1;
}

.services-right {
  flex: 3;
}

.services-right h2 {
  margin-top: -0.5rem;
  font-size: 62px;
  color: #fff;
  margin-bottom: 1rem;
}

.services-right p {
  font-size: 37px;
  color: #ccc;
  line-height: 1.5;
  margin: 0;
}

@media (max-width: 768px) {
  .logos-grid {
    max-width: 90%;
    grid-template-columns: repeat(3, 1fr);
    gap: 2rem;
  }
  .logos-grid img {
    width: 100%;
  }
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
    padding: 7rem 1rem;
    font-size: 40px;
  }
  section.gameplan {
    line-height: 80px;
    font-size: 60px;
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
    justify-content: center;
    align-items: center;
    height: auto;
  }
  .logo {
    margin-bottom: 1rem;
  }
  .menu ul {
    /* flex-direction: column; */
    gap: 0.5rem;
  }
  .hero-text {
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
.footer-section {
  /* margin-top: -60px; */
  background: black;
  color: #fff;
  padding: 0.5rem 1rem;
}

.footer-top {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: flex-start;
  max-width: 1200px;
  margin: 0 auto 1rem;
}

.footer-left {
  flex: 1;
  min-width: 220px;
  margin-bottom: 1rem;
}

.logo-box img {
  width: 100%;
  /* display: flex; */
  /* justify-content: flex-start; */
  /* align-items: flex-start; */
  position: relative;
}

.logo-outline {
  border: 2px solid #5bb507;
  display: inline-block;
  padding: 0.5rem 1rem;
  border-radius: 4px;
}

.logo-text {
  font-size: 3.5rem;
  line-height: 1.2;
  text-transform: uppercase;
  display: block;
  color: #fff;
}

.tagline {
  margin-top: 0.5rem;
  font-size: 22px;
  text-align: center;
  line-height: 1.4;
}

.footer-center {
  display: flex;
  flex-direction: column;
  flex: 1;
  min-width: 180px;
  margin-bottom: 1rem;
  align-items: center;
  /* text-align: center; */
}

.footer-center h3 {
  font-size: 25px;
  margin-bottom: 1rem;
}

.footer-center ul {
  font-size: 18px;
  list-style: none;
  padding: 0;
  margin: 0;
}

.footer-center li {
  margin: 0.5rem 0;
}

.footer-center a {
  color: #fff;
  text-decoration: none;
  font-size: 18px;
  transition: color 0.2s;
}

.footer-center a:hover {
  color: #5bb507;
}

.footer-right {
  flex: 1;
  min-width: 220px;
  margin-bottom: 1rem;
  text-align: right;
}

.social-icons {
  display: flex;
  height: 150px;
  gap: 15px;
  align-items: center;
  justify-content: center;
}

.icon {
  width: 50px;
  height: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #111;
  border-radius: 10px;
  text-decoration: none;
  font-size: 24px;
  color: #ccc;
  transition: 0.3s;
}
.footer-divider {
  width: 100%;
  height: 1px;
  background-color: #333;
  max-width: 1200px;
  margin: 1rem auto;
}

.footer-bottom {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
}

.footer-bottom p {
  margin: 0.5rem 0;
  font-size: 0.8rem;
  color: #ccc;
}

.footer-links {
  display: flex;
  gap: 1rem;
  margin: 0.5rem 0;
}

.footer-links a {
  color: #ccc;
  text-decoration: none;
  font-size: 0.8rem;
  transition: color 0.2s;
}

.footer-links a:hover {
  color: #5bb507;
}

.ffoter {
  background: white;
  color: #0a1271;
  text-align: center;
  font-size: clamp(1.5rem, 2.5vw, 41px);
  font-weight: 700;
  padding: 15px;
}
.ffoter a {
  text-decoration: none;
  color: inherit;
}
@media (max-width: 768px) {
  .footer-section {
    margin-top: -130px;
  }
  .footer-top {
    align-items: center;
    justify-items: center;
  }
  .footer-right {
    text-align: center;
  }
  .footer-left {
    text-align: center;
  }
}
@media (min-width: 768px) {
  .footer-left {
    padding: 0 1rem;
    border-right: 1px solid #333;
  }
  .footer-center {
    padding: 0 1rem;
    border-left: 1px solid #333;
    border-right: 1px solid #333;
  }
  .footer-right {
    padding: 0 1rem;
    border-left: 1px solid #333;
  }
}
</style>
