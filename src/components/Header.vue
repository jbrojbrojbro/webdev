<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)
const isMobileMenuOpen = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value
}

const scrollToSection = (sectionId) => {
  const element = document.getElementById(sectionId)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
    isMobileMenuOpen.value = false
  }
}

const navigateToPage = (url) => {
  window.location.href = url
  isMobileMenuOpen.value = false
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <header :class="['header', { 'scrolled': isScrolled }]">
    <div class="container">
      <nav class="nav">
        <div class="logo">
          <h2>ABC Fitness Studio</h2>
        </div>
        
        <ul :class="['nav-links', { 'mobile-open': isMobileMenuOpen }]">
          <li><a href="#home" @click="scrollToSection('home')">Home</a></li>
          <li><a href="#about" @click="scrollToSection('about')">About</a></li>
          <li><a href="#services" @click="scrollToSection('services')">Services</a></li>
          <li><a href="/class-schedule.html" @click.prevent="navigateToPage('/class-schedule.html')">Class Schedule</a></li>
          <li><a href="/merchandise.html" @click.prevent="navigateToPage('/merchandise.html')">Merchandise</a></li>
          <li><a href="#trainers" @click="scrollToSection('trainers')">Trainers</a></li>
          <li><a href="#pricing" @click="scrollToSection('pricing')">Pricing</a></li>
          <li><a href="/contact.html" @click.prevent="navigateToPage('/contact.html')">Contact</a></li>
        </ul>
        
        <button class="mobile-toggle" @click="toggleMobileMenu">
          <span></span>
          <span></span>
          <span></span>
        </button>
      </nav>
    </div>
  </header>
</template>

<style scoped>
.header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  background: #D3D3D3;
  backdrop-filter: blur(10px);
  transition: all 0.3s ease;
}

.header.scrolled {
  background: #D3D3D3;
  box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);
}

.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 0;
}

.logo h2 {
  font-family: 'Arial', sans-serif;
  color: #00231C;
  font-weight: bold;
  font-size: 25px;
}

.logo-image {
  height: 50px;
  width: auto;
  object-fit: contain;
  transition: transform 0.3s ease;
}

.logo-image:hover {
  transform: scale(1.05);
}

.nav-links {
  display: flex;
  list-style: none;
  gap: 2rem;
}

.nav-links a {
  font-family: 'Calibri', sans-serif;
  text-decoration: none;
  color: #00231C;
  font-weight: bold;
  font-size: 16px;
  line-height: 1.6;
  letter-spacing: 0.02em;
  transition: color 0.3s ease;
  position: relative;
}

.nav-links a:hover {
  color: #155EBC;
}

.nav-links a::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 0;
  height: 2px;
  background: #155EBC;
  transition: width 0.3s ease;
}

.nav-links a:hover::after {
  width: 100%;
}

.nav-links a:focus {
  outline: 2px solid #155EBC;
  outline-offset: 2px;
  color: #155EBC;
}

.nav-links a:focus::after {
  width: 100%;
}

.mobile-toggle {
  display: none;
  flex-direction: column;
  background: none;
  border: none;
  cursor: pointer;
  padding: 5px;
}

.mobile-toggle span {
  width: 25px;
  height: 3px;
  background: #00231C;
  margin: 3px 0;
  transition: 0.3s;
}

.mobile-toggle:focus {
  outline: 2px solid #155EBC;
  outline-offset: 2px;
}

@media (max-width: 768px) {
  .header {
    padding: 0.75rem 0;
  }
  
  .logo h2 {
    font-size: 20px;
  }
  
  .nav-links {
    position: fixed;
    top: 65px;
    left: 0;
    right: 0;
    background: #D3D3D3;
    flex-direction: column;
    padding: 1.5rem;
    gap: 1rem;
    box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
    transform: translateY(-100%);
    opacity: 0;
    visibility: hidden;
    transition: all 0.3s ease;
  }
  
  .nav-links.mobile-open {
    transform: translateY(0);
    opacity: 1;
    visibility: visible;
  }
  
  .mobile-toggle {
    display: flex;
  }
  
  .nav-links a {
    font-size: 16px;
    padding: 0.5rem 0;
  }
}
</style>