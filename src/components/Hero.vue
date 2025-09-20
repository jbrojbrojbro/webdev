<script setup>
const scrollToSection = (sectionId) => {
  const element = document.getElementById(sectionId)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}

const navigateToPage = (url) => {
  window.location.href = url
}
</script>

<template>
  <section id="home" class="hero">
    <div class="hero-background">
      <img src="https://images.pexels.com/photos/1552242/pexels-photo-1552242.jpeg?auto=compress&cs=tinysrgb&w=1920&h=1080&fit=crop" alt="Fitness Studio" />
      <div class="hero-overlay"></div>
    </div>
    
    <div class="container">
      <div class="hero-content">
        <h1 class="hero-title">
          Transform Your Body,<br>
          <span class="highlight">Transform Your Life</span>
        </h1>
        <p class="hero-subtitle">
          Join ABC Fitness Studio and discover the strongest version of yourself. 
          Our expert trainers and state-of-the-art equipment will help you achieve your fitness goals.
        </p>
        <div class="hero-buttons">
          <a href="/contact.html" @click.prevent="navigateToPage('/contact.html')" class="btn btn-primary">Start Your Journey</a>
          <a href="#services" @click="scrollToSection('services')" class="btn btn-secondary">Our Services</a>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  position: relative;
  height: 100vh;
  display: flex;
  align-items: center;
  overflow: hidden;
}

.hero-background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: -2;
}

.hero-background img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.hero-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(135deg, rgba(0, 31, 63, 0.8), rgba(21, 94, 188, 0.7));
  z-index: -1;
}

.hero-content {
  text-align: center;
  color: white;
  max-width: 800px;
  margin: 0 auto;
}

.hero-title {
  font-family: 'Arial', sans-serif;
  font-size: 30px;
  font-weight: bold;
  line-height: 1.6;
  letter-spacing: 0.02em;
  margin-bottom: 1.5rem;
}

.highlight {
  color: #fff;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
}

.hero-subtitle {
  font-family: 'Calibri', sans-serif;
  font-size: 20px;
  font-weight: normal;
  line-height: 1.6;
  letter-spacing: 0.02em;
  margin-bottom: 2.5rem;
  opacity: 0.95;
}

.hero-buttons {
  display: flex;
  gap: 1.5rem;
  justify-content: center;
  flex-wrap: wrap;
}

@media (max-width: 768px) {
  .hero {
    min-height: calc(100vh - 65px);
    margin-top: 65px;
    padding: 0 1rem;
  }
  
  .hero-content {
    padding: 1rem 0;
    text-align: center;
  }
  
  .hero-title {
    font-size: 28px;
    line-height: 1.4;
    margin-bottom: 1rem;
  }
  
  .hero-subtitle {
    font-size: 18px;
    line-height: 1.5;
    margin-bottom: 2rem;
  }
  
  .hero-buttons {
    flex-direction: column;
    align-items: center;
    gap: 1rem;
  }
  
  .hero-buttons .btn {
    width: 100%;
    max-width: 300px;
    padding: 16px 24px;
    font-size: 16px;
  }
}

@media (max-width: 480px) {
  .hero-title {
    font-size: 24px;
  }
  
  .hero-subtitle {
    font-size: 16px;
  }
  
  .hero-buttons .btn {
    max-width: 250px;
  }
}
</style>