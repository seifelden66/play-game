<template>
  <footer class="footer-section">
    <!-- Top row: logo/brand, nav links, social icons -->
    <div class="footer-top">
      <!-- Left: Logo & Tagline -->
      <div class="footer-left">
        <div class="logo-box">
          <div class="logo-outline">
            <!-- The "GAME PLAN" text with an outline -->
            <span class="logo-text">GAME<br />PLAN</span>
          </div>
          <div class="tagline">YOUR VISION,<br />OUR GAMEPLAN.</div>
        </div>
      </div>

      <!-- Center: Company Links -->
      <div class="footer-center">
        <h3>COMPANY</h3>
        <ul>
          <li><a href="#">Our Mission</a></li>
          <li><a href="#">For Athletes</a></li>
          <li><a href="#">For Brands</a></li>
          <li><a href="#">For Investors</a></li>
        </ul>
      </div>

      <!-- Right: Social Icons -->
      <div class="footer-right">
        <div class="social-icons">
          <!-- Replace # with your actual social links -->
          <img src="/icons.png" alt="" />
        </div>
      </div>
    </div>

    <!-- Divider line (optional) -->
    <div class="footer-divider"></div>

    <!-- Bottom row: copyright & policies -->
    <div class="footer-bottom">
      <p>© 2024 Gameplan. All Rights Reserved.</p>
      <div class="footer-links">
        <a href="#">Privacy Policy</a>
        <a href="#">Cookie Policy</a>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "FooterSection",
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Anton&family=Poppins:wght@400;700&display=swap");

/* Overall Footer */
.footer-section {
  color: #fff;
  font-family: "Poppins", sans-serif;
  padding: 2rem 1rem;
}

/* ========== TOP ROW ========== */
.footer-top {
  display: flex;
  flex-wrap: wrap; /* Stacks on smaller screens */
  justify-content: space-between;
  align-items: flex-start;
  max-width: 1200px;
  margin: 0 auto 1rem;
}

/* Left Column: Logo + Tagline */
.footer-left {
  flex: 1;
  min-width: 220px;
  margin-bottom: 1rem;
}

.logo-box {
  display: inline-block;
  position: relative;
}

/* The green outline behind the logo text */
.logo-outline {
  border: 2px solid #5bb507; /* Green outline */
  display: inline-block;
  padding: 0.5rem 1rem;
  border-radius: 4px;
}

/* The text inside the outline */
.logo-text {
  font-family: "Anton", sans-serif;
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

/* Center Column: COMPANY + links */
.footer-center {
  flex: 1;
  min-width: 180px;
  margin-bottom: 1rem;
  text-align: center; /* or left, if preferred */
}

.footer-center h3 {
  font-family: "Anton", sans-serif;
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

/* Right Column: Social Icons */
.footer-right {
  flex: 1;
  min-width: 220px;
  margin-bottom: 1rem;
  text-align: right; /* or center/left as desired */
}

.social-icons {
  display: inline-flex;
  gap: 1rem;
}

.social-icons a img {
  width: 24px; /* Adjust icon size */
  height: 24px;
  filter: invert(100%); /* If your icons are black, invert them to white */
  transition: filter 0.2s;
}

.social-icons a:hover img {
  filter: brightness(0) saturate(100%) invert(49%) sepia(83%) saturate(1312%)
    hue-rotate(66deg) brightness(99%) contrast(94%);
  /* This filter changes color to the same green (#5bb507). 
       You can replace with a simpler effect if you prefer. */
}

/* ========== DIVIDER ========== */
.footer-divider {
  width: 100%;
  height: 1px;
  background-color: #333;
  max-width: 1200px;
  margin: 1rem auto;
}

/* ========== BOTTOM ROW ========== */
.footer-bottom {
  display: flex;
  flex-wrap: wrap; /* Stacks on mobile */
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
</style>
