<template>
    <section class="services-section">
      <div class="services-left">
        <ul class="services-bullets">
          <li :class="{ active: activeTab === 'athletes' }" @click="activeTab = 'athletes'">
            FOR ATHLETES
          </li>
          <li :class="{ active: activeTab === 'brands' }" @click="activeTab = 'brands'">
            FOR BRANDS
          </li>
          <li :class="{ active: activeTab === 'investors' }" @click="activeTab = 'investors'">
            FOR INVESTORS
          </li>
        </ul>
      </div>
  
      <div class="services-right">
        <div v-if="activeTab === 'athletes'">
          <h2>We Are Not Just Sports Agency We Are Your Partners In Succes.</h2>
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
        Our unique athlete management system continuously aligns your message with the right
        athlete at the right time. As your brand and the world evolves, we help you
        pivot—maximizing impact and minimizing risk.
      </span>
      <span v-else-if="activeTab === 'investors'">
        We leverage our global network and unparalleled expertise to identify and invest in
        high-potential ventures across these thriving sectors. Our portfolio spans
        cutting-edge technology, sports nutrition, wellness, and beyond.
      </span>
    </div>
  </template>
  
  <script setup>
  import { ref } from "vue";
  
  const activeTab = ref("brands");
  </script>
  
  <style scoped>
  .services-section {
    max-width: 1130px;
    margin: 0 auto;
    padding: 3rem 2rem;
    display: flex;
    gap: 9rem;
  }
  
  .text-from-sercvices {
    text-align: center;
    text-transform: uppercase;
    width: 100%;
    max-width: 1130px;
    margin: 0 auto;
    color: white;
    font-size: 37px;
    padding: 2rem 0.5rem;
    margin-bottom: 1rem;
    text-transform: uppercase;
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
    color: #7c7c7c82;
    transition: color 0.2s;
  }
  
  .services-bullets li::before {
    content: "— ";
  }
  
  .services-bullets li.active {
    color: white;
    font-size: 37px;
    margin-left: 20px;
  }
  
  .services-right {
    flex: 3;
  }
  
  .services-right h2 {
    font-size: 2rem;
    color: #fff;
    margin-bottom: 1rem;
  }
  
  .services-right p {
    font-size: 1rem;
    color: #ccc;
    line-height: 1.5;
    margin: 0;
  }
  
  /* Responsive Styles */
  @media (max-width: 768px) {
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
  