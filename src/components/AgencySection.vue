<template>
  <section class="agency-section">
    <div class="agency-container">
      <div class="agency-inner">
        <div class="agency-right">
          <div class="agency-item we">
            <div class="agency-left">
              <h1 class="big-we">WE</h1>
            </div>
          </div>
          <div class="agency-item build">
            <h3>BUILD</h3>
            <p>
              We help you invest and develop in sustainable brands, extending your legacy
              beyond the game.
            </p>
          </div>
          <div class="agency-item cheer">
            <h3>CHEER</h3>
            <p>No one champions your success like we do. We are your biggest fans.</p>
          </div>
          <div class="agency-item train">
            <h3>TRAIN</h3>
            <p>
              Our team of physical, mental, and tactical coaches along with top
              nutritionists and physiotherapists helps you perform at the highest level.
            </p>
          </div>
          <div class="agency-item manage">
            <h3>MANAGE</h3>
            <p>
              We manage your career on and beyond, so you can focus entirely on the game.
            </p>
          </div>
          <div class="agency-item market">
            <h3>MARKET</h3>
            <p>We amplify the reach of your Brand through expert marketing strategies.</p>
          </div>
          <div class="agency-item tech">
            <h3>TECH</h3>
            <p>
              Our in-house data science unit employs cutting-edge technologies to give you
              a competitive edge.
            </p>
          </div>
          <div class="agency-item empower">
            <h3>EMPOWER CEOs</h3>
            <p>
              We empower you to become the CEO of your brand, fully in control of your
              future.
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup></script>

<style scoped>
.agency-section {
  padding: 2rem 1rem;
}

.agency-container {
  max-width: 1130px;
  margin: 0 auto;
  border: 4px solid transparent;
  border-radius: 15px;
  padding: 2rem;
}

.agency-inner {
  display: flex;
  gap: 2rem;
}

/* Desktop: 2-column grid with explicit placements */
.agency-right {
  display: grid;
  align-items:center ;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: repeat(4, auto);
  gap: 3rem 6rem;
  flex: 1;
}

/* Each Item */
.agency-item {
  color: #fff;
}
.agency-item h3 {
  font-size: 60px;
  margin: 0 0 0.5rem;
  text-transform: uppercase;
  border-bottom: 1px solid #fff;
  padding-bottom: 0.5rem;
}
.agency-item p {
  font-size: 23px;
  line-height: 1.4;
  margin: 0;
}

/* Explicit grid placement for desktop */
.we {
  grid-row: 1;
  grid-column: 1;
}
.build {
  grid-row: 2;
  grid-column: 1;
}
.cheer {
  grid-row: 3;
  grid-column: 1;
}
.train {
  grid-row: 4;
  grid-column: 1;
}
.manage {
  grid-row: 1;
  grid-column: 2;
}
.market {
  grid-row: 2;
  grid-column: 2;
}
.tech {
  grid-row: 3;
  grid-column: 2;
}
.empower {
  grid-row: 4;
  grid-column: 2;
}

/* Big "WE" Styling */
.agency-left {
  flex-shrink: 0;
}
.big-we {
  font-size: 299px;
  color: #fff;
  margin: 0;
  line-height: 0.9;
}

/* Responsive Styles for screens ≤768px */
@media (max-width: 768px) {
  .agency-inner {
    flex-direction: column;
  }
  .big-we {
    font-size: 150px;
  }
  .agency-right {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  /* Remove explicit grid placements on small screens */
  .agency-right > .agency-item {
    grid-column: auto;
    grid-row: auto;
  }
}

/* Further tweaks for screens ≤480px */
@media (max-width: 480px) {
  .big-we {
    font-size: 120px;
  }
  .agency-item h3 {
    font-size: 32px;
  }
}
</style>
