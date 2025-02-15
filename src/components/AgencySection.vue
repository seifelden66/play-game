<template>
  <section class="agency-section">
    <div class="agency-container">
      <!-- Top Title -->

      <div class="agency-inner">
        <!-- Left: Big "WE" -->

        <!-- Right: 7 Items in Two Columns -->
        <div class="agency-right">
          <!-- Left Column Items -->
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
              Our team of physical, mental, and tactical coaches—along with top
              nutritionists and physiotherapists—helps you perform at the highest level.
            </p>
          </div>

          <!-- Right Column Items -->
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

/* Gradient-Bordered Container */
.agency-container {
  max-width: 1130px;
  margin: 0 auto;
  border: 4px solid transparent;
  border-radius: 15px;

  padding: 2rem;
}

/* Top Title */
.agency-title {
  font-family: "Anton", sans-serif;
  font-size: 2rem;
  color: #fff;
  text-transform: uppercase;
  text-align: center;
  margin: 0 0 2rem;
  line-height: 1.2;
}

/* Inner Layout: Big WE + Grid of Items */
.agency-inner {
  display: flex;
  gap: 2rem;
}

/* Left: Big WE */
.agency-left {
  flex-shrink: 0; /* Keep the "WE" from shrinking when window resizes */
}

.big-we {
  font-family: "Anton", sans-serif;
  font-size: 299px;
  color: #fff;
  margin: 0;
  line-height: 0.9;
}

/* Right: 2-Column Grid for Items */
.agency-right {
  display: grid;
  grid-template-columns: 1fr 1fr; /* Two columns */
  grid-template-rows: repeat(4, auto); /* Four rows total */
  gap: 3rem 6rem; /* Row gap, column gap */
  flex: 1;
}

/* Each Item */
.agency-item {
  color: #fff;
}

.agency-item h3 {
  font-family: "Anton", sans-serif;
  font-size: 60px;
  margin: 0 0 0.5rem;
  text-transform: uppercase;
  /* Subtle line under heading, as in the screenshot */
  border-bottom: 1px solid #fff;
  padding-bottom: 0.5rem;
}

.agency-item p {
  font-family: "Poppins", sans-serif;
  font-size: 1rem;
  line-height: 1.4;
  margin: 0;
}

/* Explicitly place items in the grid to match the screenshot’s left & right columns */
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
/* Only apply single-column for screens <= 768px */
@media (max-width: 768px) {
  .agency-inner {
    flex-direction: column;
    /* or switch to a single-column grid if desired */
  }

  .big-we {
    font-size: 150px; /* smaller on mobile */
  }

  .agency-right {
    grid-template-columns: 1fr; /* single column for bullet items */
    gap: 2rem;
  }
}

/* If you want further tweaks for very small screens <= 480px */
@media (max-width: 480px) {
  .big-we {
    font-size: 120px;
  }

  .agency-item h3 {
    font-size: 32px;
  }
}

</style>
