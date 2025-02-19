<template>
  <section class="stats-section">
   <img src="/info-in-shapes.png" alt="">
  </section>
</template>

<script setup>
/* No additional script needed */
</script>

<style scoped>
.stats-section {
  display: flex;
  align-items: center;
  justify-items: center;
  padding: 3rem 1rem;
  max-width: 986px;
  max-height: 626px;
  margin: 0 auto;

}
.stats-section img{
  width: 100%;
}
/* 2×2 grid */
.stats-grid {
  margin: 0 auto;
  display: grid;
  grid-template-columns: 300px 491px; /* Adjust widths to match your layout */
  gap: 2rem;
  justify-content: center;
}

/* Base box styles */
.stats-box {
  position: relative;
  z-index: 0;
  border: none;
  border-radius: 0; /* We'll add corners selectively below */
  background: transparent;
  color: #fff;
  text-align: center;

  /* Layout & spacing */
  padding: 2rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

/* Default gradient border (blue → green) via pseudo-element */
.stats-box::before {
  content: "";
  position: absolute;
  inset: 0;
  border-radius: inherit;
  padding: 11px; /* “Border” thickness */
  background: linear-gradient(to right, #0032ff, #00ff3c);
  -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  -webkit-mask-composite: xor;
  mask-composite: exclude;
  z-index: -1;
}

/* ========== Make the top two boxes BLUE only ========== */
.stats-grid > div:nth-child(1)::before,
.stats-grid > div:nth-child(2)::before {
  /* Override the default gradient for top boxes */
  background: #0032ff;
}

/* ===== Rounded Corners for “Outer” Edges ===== */
/* Top-left box: round top-left corner */
.stats-grid > div:nth-child(1) {
  border-top-left-radius: 121px;
}

/* Top-right box: round top-right corner */
.stats-grid > div:nth-child(2) {
  border-top-righleftt-radius: 121px;
}

/* Bottom-left box: round bottom-left corner */
.stats-grid > div:nth-child(3) {
  border-top-right-radius: 121px;
}

/* Bottom-right box: round bottom-right corner */
.stats-grid > div:nth-child(4) {
  border-top-right-radius: 121px;
}

/* Headings & text inside each box */
.stats-box h3 {
  font-size: 123px;
  margin: 0;
  line-height: 1.2;
  font-weight: 700;
}

.stats-box p {
  font-size: 44px;
  margin: 0.5rem 0 0;
}

/* ========== Responsive Styles ========== */
@media (max-width: 768px) {
  .stats-section {
    padding: 2rem 1rem;
  }
  .stats-grid {
    grid-template-columns: 1fr 1fr;
    gap: 1.5rem;
  }
  .stats-box h3 {
    font-size: 80px;
  }
  .stats-box p {
    font-size: 30px;
  }
}

@media (max-width: 480px) {
  .stats-section {
    padding: 1.5rem 1rem;
  }
  .stats-grid {
    grid-template-columns: 1fr; /* single column on mobile */
  }
  .stats-box {
    margin: 0 auto;
    width: 200px; /* optional, to avoid overly wide boxes */
  }
  .stats-box h3 {
    font-size: 60px;
  }
  .stats-box p {
    font-size: 24px;
  }
}
</style>
