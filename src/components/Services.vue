<template>
  <section id="services" class="section services">
    <div class="container">
      <h2 class="section-title">Our Services</h2>
      <p class="section-subtitle">
        Comprehensive fitness solutions designed to meet all your health and wellness needs
      </p>
      
      <div class="services-grid">
        <div class="service-card">
          <div class="service-icon">💪</div>
          <h3>Personal Training</h3>
          <p>One-on-one sessions with certified trainers to maximize your results and ensure proper form.</p>
          <ul>
            <li>Customized workout plans</li>
            <li>Nutrition guidance</li>
            <li>Progress tracking</li>
          </ul>
        </div>
        
        <div class="service-card">
          <div class="service-icon">👥</div>
          <h3>Group Classes</h3>
          <p>High-energy group workouts that combine fitness with fun in a motivating community environment.</p>
          <ul>
            <li>HIIT & Cardio</li>
            <li>Strength Training</li>
            <li>Yoga & Pilates</li>
          </ul>
        </div>
        
        <div class="service-card">
          <div class="service-icon">🥗</div>
          <h3>Nutrition Coaching</h3>
          <p>Expert nutritional guidance to complement your fitness journey and optimize your results.</p>
          <ul>
            <li>Meal planning</li>
            <li>Dietary assessments</li>
            <li>Supplement advice</li>
          </ul>
        </div>
        
        <div class="service-card">
          <div class="service-icon">🏃</div>
          <h3>Cardio Zone</h3>
          <p>State-of-the-art cardio equipment with entertainment systems and heart rate monitoring.</p>
          <ul>
            <li>Treadmills & Ellipticals</li>
            <li>Rowing machines</li>
            <li>Stationary bikes</li>
          </ul>
        </div>
        
        <div class="service-card">
          <div class="service-icon">🏋️</div>
          <h3>Strength Training</h3>
          <p>Complete free weights and machine areas designed for all fitness levels and goals.</p>
          <ul>
            <li>Free weights</li>
            <li>Cable machines</li>
            <li>Functional training</li>
          </ul>
        </div>
        
        <div class="service-card">
          <div class="service-icon">🧘</div>
          <h3>Wellness Programs</h3>
          <p>Holistic approach to health including recovery, flexibility, and mental wellness services.</p>
          <ul>
            <li>Massage therapy</li>
            <li>Stretching sessions</li>
            <li>Meditation classes</li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.services {
  background: white;
}

.class-schedule {
  background: white;
  padding: 2rem;
  border-radius: 15px;
  margin-bottom: 3rem;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
}

.schedule-filters {
  display: flex;
  gap: 1rem;
  margin-bottom: 2rem;
  flex-wrap: wrap;
}

.filter-btn {
  font-family: 'Calibri', sans-serif;
  font-size: 16px;
  font-weight: bold;
  padding: 0.75rem 1.5rem;
  border: 2px solid #155EBC;
  background: white;
  color: #155EBC;
  border-radius: 25px;
  cursor: pointer;
  transition: all 0.3s ease;
}

.filter-btn:hover,
.filter-btn.active {
  background: #155EBC;
  color: white;
}

.schedule-table-container {
  overflow-x: auto;
}

.schedule-table {
  width: 100%;
  border-collapse: collapse;
  border: 3px solid #20458E;
  border-radius: 10px;
  overflow: hidden;
}

.schedule-table th,
.schedule-table td {
  font-family: 'Calibri', sans-serif;
  font-size: 16px;
  font-weight: normal;
  padding: 1rem;
  text-align: center;
  border: 1px solid #20458E;
  color: #00231C;
}

.schedule-table th {
  font-family: 'Arial', sans-serif;
  font-weight: bold;
  background: #20458E;
  color: white;
}

.schedule-table tbody tr:nth-child(even) {
  background: #f8f9fa;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
}

.service-card {
  background: white;
  padding: 2.5rem;
  border-radius: 20px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
  border: 1px solid #f0f0f0;
}

.service-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.12);
}

.service-icon {
  font-size: 3rem;
  margin-bottom: 1.5rem;
}

.service-card h3 {
  font-family: 'Arial', sans-serif;
  font-size: 25px;
  font-weight: bold;
  line-height: 1.6;
  letter-spacing: 0.02em;
  margin-bottom: 1rem;
  color: #00231C;
}

.service-card p {
  font-family: 'Calibri', sans-serif;
  font-size: 16px;
  font-weight: normal;
  color: #00231C;
  opacity: 0.7;
  margin-bottom: 1.5rem;
  line-height: 1.6;
  letter-spacing: 0.02em;
}

.service-card ul {
  list-style: none;
}

.service-card li {
  font-family: 'Calibri', sans-serif;
  font-size: 16px;
  font-weight: normal;
  color: #00231C;
  opacity: 0.7;
  line-height: 1.6;
  letter-spacing: 0.02em;
  margin-bottom: 0.5rem;
  position: relative;
  padding-left: 1.5rem;
}

.service-card li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: #155EBC;
  font-weight: bold;
}

@media (max-width: 768px) {
  .services-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .service-card {
    padding: 1.5rem;
    text-align: center;
  }
  
  .service-card h3 {
    font-size: 20px;
  }
  
  .service-card p {
    font-size: 15px;
  }
  
  .service-card li {
    font-size: 15px;
  }
  
  .schedule-filters {
    justify-content: center;
  }
  
  .filter-btn {
    font-size: 14px;
    padding: 0.5rem 1rem;
  }
}

@media (max-width: 480px) {
  .service-card {
    padding: 1rem;
  }
  
  .service-icon {
    font-size: 2.5rem;
  }
  
  .service-card h3 {
    font-size: 18px;
  }
  
  .service-card p,
  .service-card li {
    font-size: 14px;
  }
}
</style>