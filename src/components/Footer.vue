<script setup>
import { ref } from 'vue'

const email = ref('')

const subscribeNewsletter = () => {
  if (email.value) {
    alert('Thank you for subscribing!')
    email.value = ''
  }
}
</script>

<template>
  <footer class="footer">
    <div class="container">
      <div class="footer-content">
        <div class="footer-section">
          <h3>ABC Fitness Studio</h3>
          <p>Transform your body, transform your life. Join our community of fitness enthusiasts and achieve your goals with expert guidance.</p>
          
          <div class="newsletter-signup">
            <h4>Subscribe to Our Newsletter</h4>
            <div class="newsletter-form">
              <input 
                v-model="email" 
                type="email" 
                placeholder="Enter your email" 
                class="newsletter-input"
                @keyup.enter="subscribeNewsletter"
              />
              <button 
                @click="subscribeNewsletter" 
                class="newsletter-btn"
              >
                Subscribe
              </button>
            </div>
          </div>
          
          <div class="social-links">
            <a href="#" aria-label="Facebook">📘</a>
            <a href="#" aria-label="Instagram">📷</a>
            <a href="#" aria-label="Twitter">🐦</a>
            <a href="#" aria-label="YouTube">📺</a>
          </div>
        </div>
        
        <div class="footer-section">
          <h4>Quick Links</h4>
          <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#services">Services</a></li>
            <li><a href="#trainers">Trainers</a></li>
            <li><a href="#pricing">Pricing</a></li>
          </ul>
        </div>
        
        <div class="footer-section">
          <h4>Services</h4>
          <ul>
            <li><a href="#">Personal Training</a></li>
            <li><a href="#">Group Classes</a></li>
            <li><a href="#">Nutrition Coaching</a></li>
            <li><a href="#">Wellness Programs</a></li>
          </ul>
        </div>
        
        <div class="footer-section">
          <h4>Contact Info</h4>
          <div class="contact-info">
            <p>📍 123 Fitness Street, Wellness City, WC 12345</p>
            <p>📞 (555) 123-4567</p>
            <p>✉️ info@abcfitnessstudio.com</p>
          </div>
        </div>
      </div>
      
      <div class="footer-bottom">
        <p>&copy; 2025 ABC Fitness Studio. All rights reserved.</p>
        <div class="footer-links">
          <a href="#">Privacy Policy</a>
          <a href="#">Terms of Service</a>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background: #D3D3D3;
  color: #00231C;
  padding: 3rem 0 1rem;
}

.footer-content {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr 1.5fr;
  gap: 3rem;
  margin-bottom: 2rem;
}

.footer-section h3 {
  font-family: 'Arial', sans-serif;
  font-size: 25px;
  font-weight: bold;
  color: #00231C;
  margin-bottom: 1rem;
}

.footer-section h4 {
  font-family: 'Arial', sans-serif;
  font-size: 25px;
  font-weight: bold;
  color: #00231C;
  margin-bottom: 1rem;
}

.footer-section p {
  font-family: 'Calibri', sans-serif;
  font-size: 16px;
  font-weight: normal;
  color: #00231C;
  opacity: 0.7;
  line-height: 1.6;
  letter-spacing: 0.02em;
  margin-bottom: 1.5rem;
}

.newsletter-signup {
  margin-bottom: 2rem;
}

.newsletter-signup h4 {
  font-size: 20px;
  margin-bottom: 1rem;
}

.newsletter-form {
  display: flex;
  gap: 0.5rem;
  margin-bottom: 1rem;
}

.newsletter-input {
  font-family: 'Calibri', sans-serif;
  font-size: 16px;
  line-height: 1.6;
  letter-spacing: 0.02em;
  flex: 1;
  padding: 0.75rem;
  border: 2px solid #00231C;
  border-radius: 5px;
  background: white;
  color: #00231C;
}

.newsletter-input:focus {
  outline: none;
  border-color: #155EBC;
  box-shadow: 0 0 0 3px rgba(21, 94, 188, 0.3);
}

.newsletter-btn {
  font-family: 'Calibri', sans-serif;
  font-size: 16px;
  font-weight: bold;
  line-height: 1.6;
  letter-spacing: 0.02em;
  padding: 0.75rem 1.5rem;
  background: #00231C;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.newsletter-btn:hover {
  background: #155EBC;
}

.newsletter-btn:focus {
  outline: 2px solid #155EBC;
  outline-offset: 2px;
  box-shadow: 0 0 0 3px rgba(21, 94, 188, 0.3);
}

.social-links {
  display: flex;
  gap: 1rem;
}

.social-links a {
  font-size: 1.5rem;
  transition: transform 0.3s ease;
}

.social-links a:hover {
  transform: scale(1.2);
}

.social-links a:focus {
  outline: 2px solid #155EBC;
  outline-offset: 2px;
  transform: scale(1.2);
}

.footer-section ul {
  list-style: none;
}

.footer-section ul li {
  margin-bottom: 0.5rem;
}

.footer-section ul li a {
  font-family: 'Calibri', sans-serif;
  font-size: 16px;
  font-weight: normal;
  line-height: 1.6;
  letter-spacing: 0.02em;
  color: #00231C;
  opacity: 0.7;
  text-decoration: none;
  transition: all 0.3s ease;
  position: relative;
}

.footer-section ul li a:hover {
  color: #155EBC;
  text-decoration: underline;
}

.footer-section ul li a:focus {
  outline: 2px solid #155EBC;
  outline-offset: 2px;
  color: #155EBC;
  text-decoration: underline;
}

.contact-info p {
  font-family: 'Calibri', sans-serif;
  font-size: 16px;
  font-weight: normal;
  line-height: 1.6;
  letter-spacing: 0.02em;
  margin-bottom: 0.5rem;
  color: #00231C;
  opacity: 0.7;
}

.footer-bottom {
  border-top: 1px solid #00231C;
  padding-top: 1.5rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.footer-bottom p {
  font-family: 'Comfortaa', sans-serif;
  font-size: 15px;
  font-weight: normal;
  line-height: 1.6;
  letter-spacing: 0.02em;
  color: #00231C;
  opacity: 0.7;
  margin: 0;
}

.footer-links {
  display: flex;
  gap: 2rem;
}

.footer-links a {
  font-family: 'Calibri', sans-serif;
  font-size: 16px;
  font-weight: normal;
  line-height: 1.6;
  letter-spacing: 0.02em;
  color: #00231C;
  opacity: 0.7;
  text-decoration: none;
  transition: all 0.3s ease;
}

.footer-links a:hover {
  color: #155EBC;
  text-decoration: underline;
}

.footer-links a:focus {
  outline: 2px solid #155EBC;
  outline-offset: 2px;
  color: #155EBC;
  text-decoration: underline;
}

@media (max-width: 768px) {
  .footer-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .footer-bottom {
    flex-direction: column;
    gap: 1rem;
    text-align: center;
  }
  
  .footer-links {
    justify-content: center;
  }
  
  .newsletter-form {
    flex-direction: column;
  }
  
  .footer-section h3 {
    font-size: 20px;
  }
  
  .footer-section h4 {
    font-size: 18px;
  }
  
  .footer-section p {
    font-size: 15px;
  }
  
  .footer-section ul li a {
    font-size: 15px;
  }
  
  .contact-info p {
    font-size: 15px;
  }
  
  .footer-bottom p {
    font-size: 14px;
  }
  
  .footer-links a {
    font-size: 15px;
  }
}
</style>