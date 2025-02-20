<template>
  <section class="sports-section2">
    <h2>Our Sports</h2>
    <div class="sports-container">
      <div class="sport">
        <div class="sport-title squash">Squash</div>
        <!-- <div class="sport-img"> -->
          <img src="/squash-img.png" alt="Squash court" />
        <!-- </div> -->
      </div>

      <div class="sport">
        <div class="sport-title fencing">Fencing</div>
        <!-- <div class="sport-img"> -->
          <img src="/fence.png" alt="Fencing equipment" />
        <!-- </div> -->
      </div>

      <div class="sport">
        <div class="sport-title table-tennis">Table Tennis</div>
        <!-- <div class="sport-img"> -->
          <img src="/handball.png" alt="Table tennis paddle" />
        <!-- </div> -->
      </div>

      <div class="sport">
        <div class="sport-title olympic-sports">All Olympic Sports</div>
        <!-- <div class="sport-img">     -->
          <img src="/olymbic.png" alt="Olympic rings" />
        <!-- </div>  -->
      </div>
    </div>
  </section>
  <section class="sports-section">
    <h2>We Work With</h2>
    <div class="img">
      <!-- <div class="logos-container"> -->
      <div class="logos-grid">
        <div class="item">
          <img src="/butterfly.png" alt="Butterfly" />
        </div>
        <div class="item">
          <img src="/egyptair.png" alt="EgyptAir" />
        </div>
        <div class="item">
          <img src="/ahly.png" alt="Al Ahly" />
        </div>
        <div class="item">
          <img src="/deutsch.png" alt="Deutscher Tischtennis Bund" />
        </div>
        <div class="item">
          <img src="/ittihad.png" alt="Ittihad Club" />
        </div>
        <div class="item">
          <img src="/vodafone.png" alt="Vodafone" />
        </div>
        <div class="item">
          <img src="/gb.png" alt="Global Brands Group" />
        </div>
        <div class="item">
          <img src="/bdc.png" alt="Banque du Caire" />
        </div>
        <img src="/borussia.png" alt="Borussia Düsseldorf" />
        <div class="item">
          <img src="/enppi.png" alt="Zamalek" />
        </div>
      </div>
      <!-- </div>  -->

      <!-- <img src="/logos.png" alt="" /> -->
    </div>
  </section>
</template>

<style scoped>
.sports-section {
  max-width: 1130px;
  margin: 0 auto;
  padding: 3rem 2rem;
  display: flex;
  flex-direction: column;
  /* gap: 9rem; */
}
.sports-section img {
  width: 100%;
}
.sports-section h2 {
  font-weight: 700;
  font-size: 120px;
  line-height: 99px;
  padding: 0;
  margin-bottom: 30px;
  letter-spacing: 0%;
}
.sports-section h2 {
  font-weight: 700;
  font-size: 50px;
  line-height: 80px;
}
.logos-grid {
  display: grid;
  background: #f3f3f3;
  margin: 0 auto;
  opacity: 0.8;
  border-radius: 37px;
  grid-template-columns: repeat(5, 1fr);
  gap: 2rem;
  justify-items: center;
  align-items: center;
  width: 90%;
  height: 100%;
  padding: 20px;
  padding-top: 30px;
}
@media (max-width: 768px) {
  .logos-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}
@media (max-width: 442px) {
  .logos-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}
.item {
  /* width: 110px; */
}
.logos-grid img {
  /* width: 100%; */
  /* height: auto; */
  display: block;
}
/* Container Styling */
.sports-section2 {
    max-width: 1130px;
    margin: 0 auto;
    text-align: center;
    color: white;
}

.sports-section2 h2 {
    font-size: 50px;
    font-weight: bold;
    margin-bottom: 20px;
}

/* Sports Items Container */
.sports-section2 .sports-container {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    justify-content: center;
    gap: 40px;
    padding: 3rem 2rem;
}

/* Each Sport Block */
.sport {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    max-width: 280px; /* Adjust width to match title */
}

/* Title Styling */
.sport-title {
    display: flex;
    align-items: center;      
    /* padding: 10px; */
    justify-content: center; 
    font-weight: 700;
    font-size: 30px;
    /* line-height: 40px; */
    text-transform: uppercase;
    color: white;
    margin-bottom: 10px;
    border-top-right-radius: 55px;
    width: 100%;
    height: 104px;
    text-align: center;
}

.sport img {
    width: 100%;
    height: auto;
    border-radius: 10px;
}

/* Color Themes */
.squash {
    background-color: #72b01d;
}

.fencing {
    background-color: #1a2b64;
}

.table-tennis {
    background-color: #1e3a7a;
}

.olympic-sports {
    background-color: #03062B;
    border-top:7px solid #1e3a7a;
    border-right: 7px solid #1e3a7a;
    box-sizing: border-box;
}

/* Responsive Design */
@media (max-width: 768px) {
    .sports-section2 .sports-container {
       grid-template-columns: 1fr 1fr;
    }

    .sport {
        width: 100%;
        max-width: 90%;
    }
}
</style>
