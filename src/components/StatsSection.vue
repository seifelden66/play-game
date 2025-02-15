<template>
    <section class="stats-section">
      <div class="stats-grid">
        <!-- Top-left box -->
        <div class="stats-box">
          <h3>20+</h3>
          <p>Athletes</p>
        </div>
  
        <!-- Top-right box -->
        <div class="stats-box stts1">
          <h3>€1.5M+</h3>
          <p>Under Management</p>
        </div>
  
        <!-- Bottom-left box -->
        <div class="stats-box">
          <h3>7</h3>
          <p>Sports</p>
        </div>
  
        <!-- Bottom-right box -->
        <div class="stats-box stts1">
          <h3>4</h3>
          <p>Olympic Participations</p>
        </div>
      </div>
    </section>
  </template>
  
  <script setup>
  /* No additional script needed */
  </script>
  
  <style scoped>
  .stats-section {
    height: 100vh;
    display: flex;
    align-items: center;
    padding: 3rem 1rem;
  }
  
  /* ========== Base Layout ========== */
  /* 2×2 grid with fixed column widths for large screens */
  .stats-grid {
    margin: 0 auto;
    display: grid;
    grid-template-columns: 300px 491px; /* 2 columns: 300px & 491px */
    gap: 2rem;
    justify-content: center;
  }
  
  .stats-box {
    border: 2px solid #5bb507;
    border-radius: 8px;
    padding: 2rem;
    color: #5bb507;
    text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  
  /* Larger, bold number */
  .stats-box h3 {
    font-family: "Anton", sans-serif;
    font-size: 123px;
    margin: 0;
    line-height: 1.2;
    font-weight: 700;
  }
  
  /* Smaller label */
  .stats-box p {
    font-family: "Poppins", sans-serif;
    font-size: 44px;
    margin: 0.5rem 0 0;
  }
  
  /* ========== Responsive Styles ========== */
  
  /* Tablets and small laptops (max-width: 768px) */
  @media (max-width: 768px) {
    .stats-section {
      min-height: auto; /* let content define height on smaller screens */
      padding: 2rem 1rem;
    }
    .stats-grid {
      /* switch to two equal columns */
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
  
  /* Mobile phones (max-width: 480px) */
  @media (max-width: 480px) {
    .stats-section {
      padding: 1.5rem 1rem;
    }
    .stats-grid {
      /* one column on mobile */
      grid-template-columns: 1fr;
    }
    .stats-box {
      margin: 0 auto;
      max-width: 400px; /* optional, to keep boxes from stretching too wide */
    }
    .stats-box h3 {
      font-size: 60px;
    }
    .stats-box p {
      font-size: 24px;
    }
  }
  </style>
  