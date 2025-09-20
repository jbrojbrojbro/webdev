<script setup>
import { ref, computed } from 'vue'

const cartItems = ref([])
const showCart = ref(false)

const cartTotal = computed(() => {
  return cartItems.value.reduce((sum, item) => sum + item.price, 0)
})

const addToCart = (planName, price) => {
  // Check if plan is already in cart
  const existingItem = cartItems.value.find(item => item.name === planName)
  
  if (existingItem) {
    alert('This plan is already in your cart!')
    return
  }
  
  const item = {
    id: Date.now() + Math.random(),
    name: planName,
    price: price,
    addedAt: new Date().toISOString()
  }
  
  cartItems.value.push(item)
  alert(`${planName} plan added to cart!`)
}

const removeFromCart = (itemId) => {
  cartItems.value = cartItems.value.filter(item => item.id !== itemId)
}

const clearCart = () => {
  if (confirm('Are you sure you want to clear your cart?')) {
    cartItems.value = []
    showCart.value = false
    alert('Cart has been cleared.')
  }
}

const showCartModal = () => {
  showCart.value = true
}

const closeCartModal = () => {
  showCart.value = false
}

const checkout = () => {
  if (cartItems.value.length === 0) {
    alert('Your cart is empty!')
    return
  }
  
  const total = cartTotal.value
  const planNames = cartItems.value.map(item => item.name).join(', ')
  
  // Clear cart after checkout
  cartItems.value = []
  showCart.value = false
  
  alert(`Thank you for choosing ABC Fitness Studio! You've selected: ${planNames}. Total: $${total}/month. We'll contact you to complete your membership registration.`)
}

const formatDate = (dateString) => {
  return new Date(dateString).toLocaleDateString()
}
</script>

<template>
  <section id="pricing" class="section pricing">
    <div class="container">
      <h2 class="section-title">Membership Plans</h2>
      <p class="section-subtitle">
        Choose the perfect plan that fits your lifestyle and fitness goals
      </p>
      
      <div class="pricing-grid">
        <div class="pricing-card">
          <div class="pricing-header">
            <h3>Basic</h3>
            <div class="price">
              <span class="currency">$</span>
              <span class="amount">29</span>
              <span class="period">/month</span>
            </div>
          </div>
          <ul class="features">
            <li>Gym access during off-peak hours</li>
            <li>Basic cardio and strength equipment</li>
            <li>Locker room access</li>
            <li>Free fitness assessment</li>
          </ul>
          <button class="btn btn-secondary" @click="addToCart('Basic', 29)">Choose Plan</button>
        </div>
        
        <div class="pricing-card popular">
          <div class="popular-badge">Most Popular</div>
          <div class="pricing-header">
            <h3>Premium</h3>
            <div class="price">
              <span class="currency">$</span>
              <span class="amount">59</span>
              <span class="period">/month</span>
            </div>
          </div>
          <ul class="features">
            <li>24/7 gym access</li>
            <li>All equipment and facilities</li>
            <li>Unlimited group classes</li>
            <li>2 personal training sessions/month</li>
            <li>Nutrition consultation</li>
            <li>Guest passes (2/month)</li>
          </ul>
          <button class="btn btn-primary" @click="addToCart('Premium', 59)">Choose Plan</button>
        </div>
        
        <div class="pricing-card">
          <div class="pricing-header">
            <h3>Elite</h3>
            <div class="price">
              <span class="currency">$</span>
              <span class="amount">99</span>
              <span class="period">/month</span>
            </div>
          </div>
          <ul class="features">
            <li>Everything in Premium</li>
            <li>Unlimited personal training</li>
            <li>Priority class booking</li>
            <li>Massage therapy (2/month)</li>
            <li>Meal planning service</li>
            <li>VIP locker room access</li>
          </ul>
          <button class="btn btn-secondary" @click="addToCart('Elite', 99)">Choose Plan</button>
        </div>
      </div>
      
      <div class="pricing-note">
        <p>All memberships include a 7-day free trial. No setup fees. Cancel anytime.</p>
      </div>
      
      <!-- Floating Cart Button -->
      <button class="floating-cart" @click="showCartModal" v-show="cartItems.length > 0">
        View Cart <span class="cart-count">{{ cartItems.length }}</span>
      </button>

      <!-- Cart Modal -->
      <div v-if="showCart" class="cart-modal" @click="closeCartModal">
        <div class="cart-modal-content" @click.stop>
          <div class="cart-header">
            <h3 class="cart-title">Membership Cart</h3>
            <button class="close-cart-btn" @click="closeCartModal">&times;</button>
          </div>
          
          <div class="cart-items">
            <div v-if="cartItems.length === 0" class="empty-cart">
              Your cart is empty.
            </div>
            <div v-else>
              <div v-for="item in cartItems" :key="item.id" class="cart-item">
                <div class="cart-item-details">
                  <h4>{{ item.name }} Plan</h4>
                  <p>Added: {{ formatDate(item.addedAt) }}</p>
                </div>
                <div class="cart-item-actions">
                  <span class="cart-item-price">${{ item.price }}/month</span>
                  <button class="remove-item" @click="removeFromCart(item.id)">Remove</button>
                </div>
              </div>
            </div>
          </div>
          
          <div v-if="cartItems.length > 0" class="cart-total">
            <h3>Total: ${{ cartTotal }}/month</h3>
          </div>
          
          <div class="cart-actions">
            <button v-if="cartItems.length > 0" class="cart-btn primary" @click="checkout">Proceed to Checkout</button>
            <button v-if="cartItems.length > 0" class="cart-btn secondary" @click="clearCart">Clear Cart</button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.pricing {
  background: white;
}

.pricing-card button:focus {
  outline: 2px solid #155EBC;
  outline-offset: 2px;
  box-shadow: 0 0 0 3px rgba(21, 94, 188, 0.3);
}

.pricing-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-bottom: 3rem;
}

.pricing-card {
  background: white;
  border: 2px solid #f0f0f0;
  border-radius: 20px;
  padding: 2.5rem;
  text-align: center;
  position: relative;
  transition: all 0.3s ease;
}

.pricing-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
}

.pricing-card.popular {
  border-color: #155EBC;
  transform: scale(1.05);
}

.popular-badge {
  font-family: 'Arial', sans-serif;
  font-size: 11px;
  font-weight: bold;
  position: absolute;
  top: -15px;
  left: 50%;
  transform: translateX(-50%);
  background: linear-gradient(135deg, #155EBC, #20458E);
  color: white;
  padding: 0.5rem 1.5rem;
  border-radius: 20px;
}

.pricing-header h3 {
  font-family: 'Arial', sans-serif;
  font-size: 25px;
  font-weight: bold;
  line-height: 1.6;
  letter-spacing: 0.02em;
  margin-bottom: 1rem;
  color: #00231C;
}

.price {
  margin-bottom: 2rem;
}

.currency {
  font-family: 'Calibri', sans-serif;
  font-size: 20px;
  font-weight: normal;
  line-height: 1.6;
  letter-spacing: 0.02em;
  color: #00231C;
  opacity: 0.7;
  vertical-align: top;
}

.amount {
  font-family: 'Arial', sans-serif;
  font-size: 30px;
  font-weight: bold;
  color: #155EBC;
}

.period {
  font-family: 'Calibri', sans-serif;
  font-size: 16px;
  font-weight: normal;
  line-height: 1.6;
  letter-spacing: 0.02em;
  color: #00231C;
  opacity: 0.7;
}

.features {
  list-style: none;
  margin-bottom: 2rem;
  text-align: left;
}

.features li {
  font-family: 'Calibri', sans-serif;
  font-size: 16px;
  font-weight: normal;
  line-height: 1.6;
  letter-spacing: 0.02em;
  padding: 0.5rem 0;
  color: #00231C;
  opacity: 0.7;
  position: relative;
  padding-left: 1.5rem;
}

.features li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: #155EBC;
  font-weight: bold;
}

.pricing-note {
  font-family: 'Comfortaa', sans-serif;
  font-size: 15px;
  font-weight: normal;
  line-height: 1.6;
  letter-spacing: 0.02em;
  text-align: center;
  color: #00231C;
  opacity: 0.7;
  font-style: italic;
}

/* Floating Cart Styles */
.floating-cart {
  position: fixed;
  bottom: 2rem;
  right: 2rem;
  background: #155EBC;
  color: white;
  border: none;
  border-radius: 50px;
  padding: 1rem 1.5rem;
  font-family: 'Calibri', sans-serif;
  font-size: 14px;
  font-weight: bold;
  cursor: pointer;
  box-shadow: 0 4px 15px rgba(21, 94, 188, 0.3);
  transition: all 0.3s ease;
  z-index: 1500;
}

.floating-cart:hover {
  background: #634E99;
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(21, 94, 188, 0.4);
}

.floating-cart:focus {
  outline: 2px solid #155EBC;
  outline-offset: 2px;
  box-shadow: 0 0 0 3px rgba(21, 94, 188, 0.3);
}

.cart-count {
  background: #dc3545;
  color: white;
  border-radius: 50%;
  width: 20px;
  height: 20px;
  font-size: 12px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  margin-left: 0.5rem;
}

/* Cart Modal Styles */
.cart-modal {
  position: fixed;
  z-index: 2000;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 2rem;
}

.cart-modal-content {
  background-color: white;
  padding: 2rem;
  border-radius: 15px;
  width: 90%;
  max-width: 600px;
  max-height: 80vh;
  overflow-y: auto;
  position: relative;
}

.cart-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1.5rem;
  border-bottom: 2px solid #155EBC;
  padding-bottom: 1rem;
}

.cart-title {
  font-family: 'Arial', sans-serif;
  font-size: 25px;
  font-weight: bold;
  color: #00231C;
  margin: 0;
}

.close-cart-btn {
  background: none;
  border: none;
  font-size: 2rem;
  cursor: pointer;
  color: #00231C;
  padding: 0;
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  transition: all 0.3s ease;
}

.close-cart-btn:hover {
  background-color: #f0f0f0;
  color: #155EBC;
}

.close-cart-btn:focus {
  outline: 2px solid #155EBC;
  outline-offset: 2px;
  box-shadow: 0 0 0 3px rgba(21, 94, 188, 0.3);
}

.cart-items {
  margin-bottom: 2rem;
}

.cart-item {
  background: #f8f9fa;
  border: 1px solid #e9ecef;
  border-radius: 10px;
  padding: 1rem;
  margin-bottom: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.cart-item-details h4 {
  font-family: 'Arial', sans-serif;
  font-size: 18px;
  font-weight: bold;
  color: #00231C;
  margin: 0 0 0.5rem 0;
}

.cart-item-details p {
  font-family: 'Calibri', sans-serif;
  font-size: 14px;
  color: #00231C;
  opacity: 0.7;
  margin: 0;
  line-height: 1.6;
  letter-spacing: 0.02em;
}

.cart-item-actions {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.cart-item-price {
  font-family: 'Arial', sans-serif;
  font-size: 18px;
  font-weight: bold;
  color: #155EBC;
}

.remove-item {
  background: #dc3545;
  color: white;
  border: none;
  border-radius: 5px;
  padding: 0.5rem 1rem;
  cursor: pointer;
  font-family: 'Calibri', sans-serif;
  font-size: 12px;
  font-weight: bold;
  transition: all 0.3s ease;
}

.remove-item:hover {
  background: #c82333;
  transform: translateY(-1px);
}

.remove-item:focus {
  outline: 2px solid #155EBC;
  outline-offset: 2px;
  box-shadow: 0 0 0 3px rgba(21, 94, 188, 0.3);
}

.cart-total {
  border-top: 2px solid #155EBC;
  padding-top: 1rem;
  margin-bottom: 2rem;
  text-align: right;
}

.cart-total h3 {
  font-family: 'Arial', sans-serif;
  font-size: 24px;
  font-weight: bold;
  color: #00231C;
  margin: 0;
}

.cart-actions {
  display: flex;
  gap: 1rem;
  justify-content: center;
  flex-wrap: wrap;
}

.cart-btn {
  font-family: 'Calibri', sans-serif;
  font-size: 16px;
  font-weight: bold;
  line-height: 1.6;
  letter-spacing: 0.02em;
  padding: 1rem 2rem;
  border: none;
  border-radius: 10px;
  cursor: pointer;
  transition: all 0.3s ease;
}

.cart-btn.primary {
  background: #155EBC;
  color: white;
}

.cart-btn.primary:hover {
  background: #634E99;
  transform: translateY(-2px);
  box-shadow: 0 10px 25px rgba(21, 94, 188, 0.3);
}

.cart-btn.secondary {
  background: #6c757d;
  color: white;
}

.cart-btn.secondary:hover {
  background: #545b62;
  transform: translateY(-2px);
  box-shadow: 0 10px 25px rgba(108, 117, 125, 0.3);
}

.cart-btn:focus {
  outline: 2px solid #155EBC;
  outline-offset: 2px;
  box-shadow: 0 0 0 3px rgba(21, 94, 188, 0.3);
}

.empty-cart {
  text-align: center;
  padding: 2rem;
  color: #6c757d;
  font-family: 'Calibri', sans-serif;
  font-size: 16px;
  line-height: 1.6;
  letter-spacing: 0.02em;
}

@media (max-width: 768px) {
  .floating-cart {
    bottom: 1rem;
    right: 1rem;
    padding: 0.75rem 1rem;
    font-size: 12px;
  }
  
  .cart-count {
    width: 18px;
    height: 18px;
    font-size: 10px;
  }
  
  .cart-modal {
    padding: 1rem;
  }
  
  .cart-modal-content {
    padding: 1.5rem;
    width: 95%;
    max-height: 90vh;
  }
  
  .cart-title {
    font-size: 20px;
  }
  
  .cart-btn {
    padding: 0.75rem 1.5rem;
    font-size: 14px;
  }
  
  .cart-item {
    flex-direction: column;
    align-items: flex-start;
    gap: 1rem;
  }
  
  .cart-item-actions {
    justify-content: space-between;
    width: 100%;
  }
  
  .pricing-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
    padding: 0 1rem;
  }
  
  .pricing-card.popular {
    transform: none;
    margin: 0;
  }
  
  .pricing-card {
    padding: 2rem;
    margin: 0;
  }
  
  .pricing-header h3 {
    font-size: 20px;
  }
  
  .amount {
    font-size: 28px;
  }
  
  .features li {
    font-size: 15px;
  }
  
  .pricing-note {
    font-size: 14px;
  }
}

@media (max-width: 480px) {
  .cart-modal-content {
    padding: 1rem;
    margin: 0.5rem;
  }
  
  .cart-title {
    font-size: 18px;
  }
  
  .cart-btn {
    padding: 0.75rem 1.25rem;
    font-size: 13px;
    width: 100%;
  }
  
  .cart-actions {
    flex-direction: column;
    gap: 0.75rem;
  }
  
  .pricing-card {
    padding: 1.5rem;
  }
  
  .pricing-header h3 {
    font-size: 18px;
  }
  
  .amount {
    font-size: 24px;
  }
  
  .features li {
    font-size: 14px;
  }
  
  .popular-badge {
    font-size: 10px;
    padding: 0.4rem 1rem;
  }
}
</style>