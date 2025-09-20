<template>
  <section id="about" class="section about">
    <div class="container">
      <h2 class="section-title">About ABC Fitness Studio</h2>
      <p class="section-subtitle">
        Your premier destination for fitness, wellness, and personal transformation
      </p>
      
      <div class="promo-section">
        <h3 style="font-family: 'Arial', sans-serif; font-size: 25px; font-weight: bold; color: white; margin-bottom: 1rem;">Featured Classes</h3>
        <p style="font-family: 'Calibri', sans-serif; font-size: 16px; font-weight: normal; color: white; opacity: 0.9; margin-bottom: 1.5rem;">Join our most popular fitness classes designed for all levels</p>
        <div class="class-images">
          <img src="https://i.postimg.cc/vg9KCP9g/spin-bike.jpg" alt="Spin Cycle Bike" class="class-image" />
          <img src="https://i.postimg.cc/18k2MhVh/heavy-bag.jpg" alt="Heavy Bag" class="class-image" />
        </div>
      </div>
      
      <div class="about-content">
        <div class="about-text">
          <div class="about-item">
            <div class="about-icon">🏋️</div>
            <div>
              <h3>Expert Training</h3>
              <p>Our certified trainers bring years of experience and passion to help you reach your fitness goals safely and effectively.</p>
            </div>
          </div>
          
          <div class="about-item">
            <div class="about-icon">🎯</div>
            <div>
              <h3>Personalized Programs</h3>
              <p>Every member gets a customized workout plan tailored to their fitness level, goals, and lifestyle preferences.</p>
            </div>
          </div>
          
          <div class="about-item">
            <div class="about-icon">🏆</div>
            <div>
              <h3>Proven Results</h3>
              <p>With over 500 success stories, we've helped members lose weight, build muscle, and transform their lives.</p>
            </div>
          </div>
          
          <div class="about-item">
            <div class="about-icon">🌟</div>
            <div>
              <h3>Community Focus</h3>
              <p>More than just a gym, we're a supportive community that celebrates every milestone and encourages every member.</p>
            </div>
          </div>
          
          <div class="equipment-section">
            <div class="equipment-accent">
              <h3>State-of-the-Art Equipment</h3>
              <p>Our facility features the latest fitness technology and equipment to help you achieve your goals efficiently and safely.</p>
            </div>
          </div>
        
        <div class="about-image">
          <img src="https://images.pexels.com/photos/1552106/pexels-photo-1552106.jpeg?auto=compress&cs=tinysrgb&w=600&h=800&fit=crop" alt="Modern gym interior" />
        </div>
      </div>
      
      <div class="business-hours">
        <h3 style="font-family: 'Arial', sans-serif; font-size: 25px; font-weight: bold; color: #00231C; margin-bottom: 1rem;">Business Hours</h3>
        <table class="hours-table">
          <thead>
            <tr>
              <th>Day</th>
              <th>Hours</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>Monday - Friday</td>
              <td>5:00 AM - 11:00 PM</td>
            </tr>
            <tr>
              <td>Saturday - Sunday</td>
              <td>6:00 AM - 10:00 PM</td>
            </tr>
            <tr>
              <td>Holidays</td>
              <td>8:00 AM - 8:00 PM</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
      
      <div class="stats">
        <div class="stat">
          <h3>500+</h3>
          <p>Happy Members</p>
        </div>
        <div class="stat">
          <h3>10+</h3>
          <p>Expert Trainers</p>
        </div>
        <div class="stat">
          <h3>40+</h3>
          <p>Weekly Classes</p>
        </div>
        <div class="stat">
          <h3>5</h3>
          <p>Years Experience</p>
        </div>
        <div class="stat">
          <h3>24/7</h3>
          <p>Access Available</p>
        </div>
        <div class="stat">
          <h3>2020</h3>
          <p>Year Founded</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about {
  background: white;
}

.company-history {
  margin-bottom: 4rem;
}

.facilities-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
  margin-bottom: 2rem;
}

.facility-item {
  display: flex;
  gap: 1.5rem;
  background: #f8f9fa;
  padding: 2rem;
  border-radius: 15px;
  border: 1px solid #e9ecef;
  transition: all 0.3s ease;
}

.facility-item:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.08);
}

.facility-icon {
  font-size: 2.5rem;
  flex-shrink: 0;
}

.facility-item h4 {
  font-family: 'Arial', sans-serif;
  font-size: 20px;
  font-weight: bold;
  margin-bottom: 0.5rem;
  color: #00231C;
}

.facility-item p {
  font-family: 'Calibri', sans-serif;
  font-size: 16px;
  font-weight: normal;
  color: #00231C;
  opacity: 0.7;
  line-height: 1.6;
}

.about-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
  margin-bottom: 4rem;
}

.promo-section {
  background: #001F3F;
  border: 2px solid #001F3F;
  border-radius: 15px;
  padding: 2rem;
  margin-bottom: 3rem;
  color: white;
}

.class-images {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
  margin: 2rem 0;
}

.class-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
  border-radius: 10px;
}

.class-label {
  font-family: 'Arial', sans-serif;
  font-size: 18px;
  font-weight: bold;
  color: white;
  text-align: center;
  margin-top: 0.5rem;
  margin-bottom: 0;
}

.equipment-section {
  margin-top: 3rem;
}

.equipment-accent {
  color: #634E99;
  border-left: 4px solid #634E99;
  padding-left: 1rem;
}

.business-hours {
  background: #D3D3D3;
  border: 2px solid #00231C;
  border-radius: 10px;
  padding: 2rem;
  margin: 2rem auto;
  max-width: 500px;
  text-align: center;
}

.hours-table {
  width: 100%;
  border-collapse: collapse;
}

.hours-table th,
.hours-table td {
  font-family: 'Calibri', sans-serif;
  font-size: 16px;
  font-weight: normal;
  line-height: 1.6;
  letter-spacing: 0.02em;
  padding: 0.75rem;
  text-align: left;
  border-bottom: 1px solid #00231C;
  color: #00231C;
}

.hours-table th {
  font-family: 'Arial', sans-serif;
  font-weight: bold;
}

.about-item {
  display: flex;
  gap: 1.5rem;
  margin-bottom: 2.5rem;
}

.about-icon {
  font-size: 2.5rem;
  flex-shrink: 0;
}

.about-item h3 {
  font-family: 'Arial', sans-serif;
  font-size: 25px;
  font-weight: bold;
  line-height: 1.6;
  letter-spacing: 0.02em;
  margin-bottom: 0.5rem;
  color: #00231C;
}

.about-item p {
  font-family: 'Calibri', sans-serif;
  font-size: 16px;
  font-weight: normal;
  color: #00231C;
  opacity: 0.7;
  line-height: 1.6;
  letter-spacing: 0.02em;
}

.about-image {
  position: relative;
}

.about-image img {
  width: 100%;
  height: 500px;
  object-fit: cover;
  border-radius: 20px;
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
}

.stats {
  display: grid;
  grid-template-columns: repeat(6, 1fr);
  gap: 2rem;
  text-align: center;
}

.stat h3 {
  font-family: 'Arial', sans-serif;
  font-size: 30px;
  font-weight: bold;
  color: #155EBC;
  margin-bottom: 0.5rem;
}

.stat p {
  font-family: 'Comfortaa', sans-serif;
  font-size: 15px;
  font-weight: normal;
  line-height: 1.6;
  letter-spacing: 0.02em;
  color: #00231C;
  opacity: 0.7;
}

@media (max-width: 768px) {
  .about-content {
    grid-template-columns: 1fr;
    gap: 2.5rem;
  }
  
  .facilities-grid {
    grid-template-columns: 1fr;
  }
  
  .facility-item {
    padding: 1.5rem;
  }
  
  .class-images {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .class-image {
    height: 250px;
  }
  
  .about-image {
    order: -1;
  }
  
  .about-image img {
    height: 280px;
  }
  
  .stats {
    grid-template-columns: repeat(2, 1fr);
    gap: 1.5rem;
    margin-top: 2rem;
  }
  
  .stat h3 {
    font-size: 24px;
  }
  
  .stat p {
    font-size: 14px;
  }
  
  .about-item h3 {
    font-size: 20px;
  }
  
  .about-item p {
    font-size: 15px;
  }
  
  .promo-section {
    padding: 1.5rem;
    margin-bottom: 2rem;
  }
  
  .business-hours {
    padding: 1.5rem;
    margin: 1.5rem auto;
  }
  
  .hours-table th,
  .hours-table td {
    padding: 0.5rem;
    font-size: 14px;
  }
}

@media (max-width: 480px) {
  .about-item {
    flex-direction: column;
    text-align: center;
    gap: 1rem;
  }
  
  .about-icon {
    align-self: center;
  }
  
  .stats {
    grid-template-columns: 1fr;
    gap: 1rem;
  }
  
  .promo-section {
    padding: 1rem;
  }
}
</style>