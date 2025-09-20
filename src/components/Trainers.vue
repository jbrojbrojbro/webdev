<template>
  <section id="trainers" class="section trainers">
    <div class="container">
      <h2 class="section-title">Meet Our Expert Trainers</h2>
      <p class="section-subtitle">
        Our certified professionals are here to guide, motivate, and support you every step of the way
      </p>
      
      <div class="trainers-grid">
        <div class="trainer-card">
          <div class="trainer-image">
            <img src="https://images.pexels.com/photos/3768916/pexels-photo-3768916.jpeg?auto=compress&cs=tinysrgb&w=400&h=400&fit=crop" alt="Sarah Johnson" />
          </div>
          <div class="trainer-info">
            <h3>Sarah Johnson</h3>
            <p class="trainer-title">Head Personal Trainer</p>
            <p class="trainer-bio">10+ years experience in strength training and nutrition. Specializes in weight loss and muscle building programs.</p>
            <div class="trainer-certifications">
              <span>NASM-CPT</span>
              <span>Nutrition Specialist</span>
            </div>
          </div>
        </div>
        
        <div class="trainer-card">
          <div class="trainer-image">
            <img src="https://images.pexels.com/photos/1552252/pexels-photo-1552252.jpeg?auto=compress&cs=tinysrgb&w=400&h=400&fit=crop" alt="Mike Rodriguez" />
          </div>
          <div class="trainer-info">
            <h3>Mike Rodriguez</h3>
            <p class="trainer-title">Strength & Conditioning Coach</p>
            <p class="trainer-bio">Former athlete with expertise in functional training and sports performance. Passionate about helping clients reach their peak.</p>
            <div class="trainer-certifications">
              <span>CSCS</span>
              <span>FMS Certified</span>
            </div>
          </div>
        </div>
        
        <div class="trainer-card">
          <div class="trainer-image">
            <img src="https://images.pexels.com/photos/3757942/pexels-photo-3757942.jpeg?auto=compress&cs=tinysrgb&w=400&h=400&fit=crop" alt="Emma Chen" />
          </div>
          <div class="trainer-info">
            <h3>Emma Chen</h3>
            <p class="trainer-title">Yoga & Wellness Instructor</p>
            <p class="trainer-bio">Certified yoga instructor and wellness coach focused on mind-body connection and holistic health approaches.</p>
            <div class="trainer-certifications">
              <span>RYT-500</span>
              <span>Wellness Coach</span>
            </div>
          </div>
        </div>
        
        <div class="trainer-card">
          <div class="trainer-image">
            <img src="https://images.pexels.com/photos/1552106/pexels-photo-1552106.jpeg?auto=compress&cs=tinysrgb&w=400&h=400&fit=crop" alt="David Kim" />
          </div>
          <div class="trainer-info">
            <h3>David Kim</h3>
            <p class="trainer-title">HIIT & Group Fitness</p>
            <p class="trainer-bio">High-energy trainer specializing in HIIT workouts and group fitness classes. Known for making workouts fun and challenging.</p>
            <div class="trainer-certifications">
              <span>ACE-CPT</span>
              <span>Group Fitness</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.trainers {
  background: #D3D3D3;
}

.trainers-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
}

.trainer-card {
  background: white;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
}

.trainer-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.12);
}

.trainer-image {
  position: relative;
  overflow: hidden;
}

.trainer-image img {
  width: 100%;
  height: 300px;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.trainer-card:hover .trainer-image img {
  transform: scale(1.05);
}

.trainer-info {
  padding: 2rem;
}

.trainer-info h3 {
  font-family: 'Arial', sans-serif;
  font-size: 25px;
  font-weight: bold;
  line-height: 1.6;
  letter-spacing: 0.02em;
  margin-bottom: 0.5rem;
  color: #00231C;
}

.trainer-title {
  font-family: 'Comfortaa', sans-serif;
  font-size: 15px;
  font-weight: normal;
  line-height: 1.6;
  letter-spacing: 0.02em;
  color: #634E99;
  margin-bottom: 1rem;
}

.trainer-bio {
  font-family: 'Calibri', sans-serif;
  font-size: 16px;
  font-weight: normal;
  color: #00231C;
  opacity: 0.7;
  line-height: 1.6;
  letter-spacing: 0.02em;
  margin-bottom: 1.5rem;
}

.trainer-certifications {
  display: flex;
  gap: 0.5rem;
  flex-wrap: wrap;
}

.trainer-certifications span {
  background: linear-gradient(135deg, #155EBC, #20458E);
  color: white;
  font-family: 'Arial', sans-serif;
  font-size: 11px;
  font-weight: bold;
  padding: 0.3rem 0.8rem;
  border-radius: 20px;
}

@media (max-width: 768px) {
  .trainers-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .trainer-info {
    padding: 1.5rem;
  }
  
  .trainer-info h3 {
    font-size: 20px;
  }
  
  .trainer-title {
    font-size: 14px;
  }
  
  .trainer-bio {
    font-size: 15px;
  }
  
  .trainer-certifications span {
    font-size: 10px;
    padding: 0.25rem 0.6rem;
  }
}
</style>