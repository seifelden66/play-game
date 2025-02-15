<template>
  <section class="contact-section">
    <div class="contact-content">
      <!-- LEFT COLUMN: Heading + Subheading -->
      <div class="contact-left">
        <h2>Get in touch with us</h2>
        <p>
          To help us to best communicate with you, please provide us with your details.
        </p>
      </div>

      <!-- RIGHT COLUMN: Form -->
      <div class="contact-right">
        <form @submit.prevent>
          <div class="form-grid">
            <!-- First Name -->
            <div class="form-group">
              <label for="firstName">First Name*</label>
              <input type="text" id="firstName" required />
            </div>

            <!-- Last Name -->
            <div class="form-group">
              <label for="lastName">Last Name*</label>
              <input type="text" id="lastName" required />
            </div>

            <!-- Email -->
            <div class="form-group">
              <label for="email">Email*</label>
              <input type="email" id="email" required />
            </div>

            <!-- Mobile -->
            <div class="form-group">
              <label for="mobile">Mobile*</label>
              <input type="tel" id="mobile" required />
            </div>

            <!-- Enquiry (spans full width) -->
            <div class="form-group full-width">
              <label for="enquiry">Please write us your enquiry*</label>
              <textarea id="enquiry" rows="4" required></textarea>
            </div>
          </div>

          <!-- Submit Button -->
          <button type="submit">SUBMIT</button>
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
  margin-top: 180px;
  border-radius: 0px 30% 0px 0px;
  background-color: #8AC13C;
  color: #000;
  padding: 6rem 2rem 8rem;
  clip-path: polygon(0% 12.5%, 100% -7%, 100% 88.5%, 0% 100.3%);

  font-family: "Poppins", sans-serif;
}

.contact-content {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  gap: 4rem;
}

.contact-left {
  flex: 1;
  padding-top: 2rem;
}

.contact-left h2 {
  font-family: "Anton", sans-serif;
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

.form-group input:focus,
.form-group textarea:focus {
  border-bottom-color: #5bb507;
  outline: none;
}

.full-width {
  grid-column: 1 / -1;
}

button[type="submit"] {
  width: 100%;
  margin-top: 2rem;
  padding: 1.25rem;
  background-color: #8AC13C;
  color: #000;
  border: none;
  border-radius: 6px;
  font-family: "Anton", sans-serif;
  font-size: 1.1rem;
  letter-spacing: 0.5px;
  cursor: pointer;
  transition: all 0.3s ease;
}

button[type="submit"]:hover {
  background-color: #4da006;
  transform: translateY(-2px);
}

@media (max-width: 768px) {
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
