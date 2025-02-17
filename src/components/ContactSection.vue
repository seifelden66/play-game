<template>
  <section class="contact-section">
    <div class="contact-content">
      <div class="contact-left">
        <h2>
          Get in touch <br />
          with us
        </h2>
        <p>
          To help us to best communicate with you, please provide us with your details.
        </p>
      </div>

      <div class="contact-right">
        <form @submit.prevent>
          <div class="form-grid">
            <div class="form-group">
              <input type="text" placeholder="First Name*" id="firstName" required />
            </div>

            <div class="form-group">
              <input type="text" placeholder="Last Name*" id="lastName" required />
            </div>

            <div class="form-group">
              <input type="email" placeholder="Email*" id="email" required />
            </div>

            <div class="form-group">
              <input placeholder="Mobile*" type="tel" id="mobile" required />
            </div>

            <div class="form-group full-width">
              <textarea id="enquiry" placeholder="Please write us your enquiry*" required></textarea>
            </div>
          </div>

          <div class="btn">
            <button type="submit">SUBMIT</button>
          </div>
        </form>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "ContactSection",
};
</script>

<style scoped>
.contact-section {
  background: url("/green-shape.png") no-repeat top left / cover,
    linear-gradient(to bottom, #080c54, #000);
  margin-top: 90px;
  color: #000;
  min-height: 100vh;
}

.btn {
  display: flex;
  justify-content: flex-end;
}

.btn button {
  margin-left: auto;
  font-size: 16px;
  color: #abf149;
  width: 124px;
  height: 42px;
  padding: 10px;
  border-radius: 0 24px 0 0;
  background: #1c3901;
}

.contact-content {
  height: 100vh;
  z-index: 999999999;
  max-width: 1200px;
  margin: 0 auto;
  align-items: center;
  display: flex;
  gap: 4rem;
}

.contact-left {
  flex: 1;
  padding-top: 2rem;
}

.contact-left h2 {
  font-size: 46px;
  font-weight: 700;
  margin-bottom: 1.5rem;
  letter-spacing: 0.5px;
}

.contact-left p {
  font-size: 1.1rem;
  line-height: 1.6;
  max-width: 400px;
}

.contact-right {
  flex: 1;
  padding: 2.5rem;
  border-radius: 12px;
}

.form-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1.5rem;
}

.form-group label {
  display: block;
  margin-bottom: 0.5rem;
  font-size: 0.95rem;
  font-weight: 500;
}

.form-group input,
.form-group textarea {
  width: 100%;
  background: transparent;
  border: none;
  border-bottom: 2px solid #2d3448;
  color: #fff;
  padding: 0.75rem 0;
  font-size: 1rem;
  transition: border-color 0.3s ease;
}

/* 
   1) Make placeholders black. 
   2) Use vendor prefixes for broader browser support if needed.
*/
.form-group input::placeholder,
.form-group textarea::placeholder {
  color: #000;
}

.form-group input:focus,
.form-group textarea:focus {
  border-bottom-color: #5bb507;
  outline: none;
}

.full-width {
  grid-column: 1 / -1;
}

@media (max-width: 768px) {
  .contact-section {
    display: flex;
    align-items: center;
    height: 200vh;
    margin-top: 0px;
  }
  .contact-content {
    flex-direction: column;
    gap: 2rem;
  }
  .contact-left {
    text-align: center;
    padding-top: 0;
  }
  .contact-left p {
    max-width: 100%;
  }
  .form-grid {
    grid-template-columns: 1fr;
  }
  .full-width {
    grid-column: 1;
  }
}
</style>
