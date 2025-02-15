<template>
  <footer class="footer-section">
    <div class="footer-top">
      <div class="footer-left">
        <div class="logo-box">
          <div class="logo-outline">
            <span class="logo-text">GAME<br />PLAN</span>
          </div>
          <div class="tagline">YOUR VISION,<br />OUR GAMEPLAN.</div>
        </div>
      </div>
      <div class="footer-center">
        <h3>COMPANY</h3>
        <ul>
          <li><a href="#tocuh">Our Mission</a></li>
          <li><a href="#tocuh">For Athletes</a></li>
          <li><a href="#tocuh">For Brands</a></li>
          <li><a href="#tocuh">For Investors</a></li>
        </ul>
      </div>
      <div class="footer-right">
        <div class="social-icons">
          <img src="/icons.png" alt="" />
        </div>
      </div>
    </div>
    <div class="footer-divider"></div>
    <div class="footer-bottom">
      <p>© 2024 Gameplan. All Rights Reserved.</p>
      <div class="footer-links">
        <a href="#">Privacy Policy</a>
        <a href="#">Cookie Policy</a>
      </div>
    </div>
  </footer>
  <div class="ffoter">get in touch with us</div>
</template>

<script>
export default {
  name: "FooterSection",
};
</script>

<style scoped>

.footer-section {
  margin-top: -70px;
  background: black;
  color: #fff;
  padding: 8rem 1rem;
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

.logo-box {
  display: inline-block;
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
  flex: 1;
  min-width: 180px;
  margin-bottom: 1rem;
  text-align: center;
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
  display: inline-flex;
  gap: 1rem;
}

.social-icons a img {
  width: 24px;
  height: 24px;
  filter: invert(100%);
  transition: filter 0.2s;
}

.social-icons a:hover img {
  filter: brightness(0) saturate(100%) invert(49%) sepia(83%) saturate(1312%)
    hue-rotate(66deg) brightness(99%) contrast(94%);
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
  padding: 10px;
}

@media (max-width: 768px) {
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
