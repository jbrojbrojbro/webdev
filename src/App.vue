<script setup>
import Header from './components/Header.vue'
import Hero from './components/Hero.vue'
import About from './components/About.vue'
import Services from './components/Services.vue'
import Trainers from './components/Trainers.vue'
import Pricing from './components/Pricing.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <div class="app">
    <Header />
    <Hero />
    <About />
    <Services />
    <Trainers />
    <Pricing />
    <Footer />
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Calibri', sans-serif;
  line-height: 1.6;
  letter-spacing: 0.02em;
  color: #00231C;
  overflow-x: hidden;
}

.app {
  min-height: 100vh;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.section {
  padding: 80px 0;
}

.section-title {
  font-family: 'Arial', sans-serif;
  font-size: 30px;
  font-weight: bold;
  text-align: center;
  margin-bottom: 20px;
  color: #00231C;
}

.section-subtitle {
  font-family: 'Comfortaa', sans-serif;
  font-size: 15px;
  font-weight: normal;
  text-align: center;
  color: #00231C;
  opacity: 0.7;
  line-height: 1.6;
  letter-spacing: 0.02em;
  margin-bottom: 60px;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
}

.btn {
  font-family: 'Calibri', sans-serif;
  display: inline-block;
  padding: 14px 32px;
  border: none;
  border-radius: 50px;
  font-weight: bold;
  font-size: 16px;
  line-height: 1.6;
  letter-spacing: 0.02em;
  text-decoration: none;
  cursor: pointer;
  transition: all 0.3s ease;
}

.btn-primary {
  background: linear-gradient(135deg, #155EBC, #20458E);
  color: white;
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 10px 25px rgba(21, 94, 188, 0.3);
}

.btn-secondary {
  background: transparent;
  color: #155EBC;
  border: 2px solid #155EBC;
}

.btn-secondary:hover {
  background: #155EBC;
  color: white;
}

.btn:focus {
  outline: 2px solid #155EBC;
  outline-offset: 2px;
}

.btn-primary:focus {
  box-shadow: 0 0 0 3px rgba(21, 94, 188, 0.3);
}

.btn-secondary:focus {
  background: #155EBC;
  color: white;
  box-shadow: 0 0 0 3px rgba(21, 94, 188, 0.3);
}

@media (max-width: 768px) {
  .section {
    padding: 40px 0;
  }
  
  .section-title {
    font-size: 24px;
    line-height: 1.4;
    margin-bottom: 16px;
  }
  
  .section-subtitle {
    font-size: 14px;
    margin-bottom: 40px;
  }
  
  .container {
    padding: 0 16px;
  }
  
  .btn {
    padding: 12px 24px;
    font-size: 14px;
  }
}

@media (max-width: 480px) {
  .section {
    padding: 30px 0;
  }
  
  .section-title {
    font-size: 20px;
    margin-bottom: 12px;
  }
  
  .section-subtitle {
    font-size: 13px;
    margin-bottom: 30px;
  }
  
  .container {
    padding: 0 12px;
  }
  
  .btn {
    padding: 10px 20px;
    font-size: 13px;
    width: 100%;
    max-width: 250px;
  }
}
</style>