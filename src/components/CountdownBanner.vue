<template>
  <div class="banner">
    <div class="container banner-content">
      <span class="banner-text">
        <span class="vaga-highlight">Garanta sua vaga gratuita</span> 
        <span class="banner-extra-text">, <strong class="highlight-marker">o Treinamento Buttercream sem segredo começa em breve!</strong> Faltam apenas...</span>
      </span>
      <div class="countdown">
        <div class="time-box">
          <span class="time-val">{{ days }}</span>
          <span class="time-label">Dias</span>
        </div>
        <div class="time-box">
          <span class="time-val">{{ hours }}</span>
          <span class="time-label">Hrs</span>
        </div>
        <div class="time-box">
          <span class="time-val">{{ mins }}</span>
          <span class="time-label">Mins</span>
        </div>
        <div class="time-box">
          <span class="time-val">{{ secs }}</span>
          <span class="time-label">Segs</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

// Target date: Feb 23, 2026
const targetDate = new Date('2026-02-23T20:00:00').getTime()

const days = ref('00')
const hours = ref('00')
const mins = ref('00')
const secs = ref('00')

const updateCountdown = () => {
  const now = new Date().getTime()
  const distance = targetDate - now

  if (distance < 0) return

  days.value = Math.floor(distance / (1000 * 60 * 60 * 24)).toString().padStart(2, '0')
  hours.value = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)).toString().padStart(2, '0')
  mins.value = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60)).toString().padStart(2, '0')
  secs.value = Math.floor((distance % (1000 * 60)) / 1000).toString().padStart(2, '0')
}

onMounted(() => {
  updateCountdown()
  setInterval(updateCountdown, 1000)
})
</script>

<style scoped>
.banner {
  background-color: var(--secondary);
  color: var(--white);
  padding: 0.75rem 0;
  font-size: 0.875rem;
}

.banner-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 1rem;
}

.banner-text .highlight-marker {
  position: relative;
  color: var(--white);
  padding: 0 4px;
  z-index: 1;
  display: inline-block;
}

.banner-text .highlight-marker::after {
  content: '';
  position: absolute;
  left: 0;
  bottom: 0;
  height: 100%;
  width: 100%;
  background-color: var(--primary);
  z-index: -1;
  transform: scaleX(0);
  transform-origin: left;
  animation: highlight-draw 1.5s cubic-bezier(0.19, 1, 0.22, 1) forwards;
  animation-delay: 0.5s;
  border-radius: 2px;
}

@keyframes highlight-draw {
  to {
    transform: scaleX(1);
  }
}

.countdown {
  display: flex;
  gap: 1.5rem;
}

.time-box {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.time-val {
  font-size: 1.25rem;
  font-weight: 800;
  line-height: 1;
}

.time-label {
  font-size: 0.625rem;
  font-weight: 600;
  opacity: 0.7;
}

@media (max-width: 994px) {
  .banner {
    padding: 0.6rem 0; /* Slightly more height for better balance */
  }

  .banner-content {
    flex-direction: row;
    flex-wrap: nowrap;
    justify-content: center;
    gap: 0.75rem;
    padding: 0 0.75rem;
  }

  .banner-text {
    font-size: 0.8125rem; /* Better visibility since we have more room now */
    white-space: nowrap;
  }

  .banner-extra-text {
    display: none; /* Remove training title etc. on mobile as requested */
  }

  /* Remove highlight effect from training title on mobile */
  .banner-text .highlight-marker::after {
    display: none;
  }
  
  /* Add highlight effect to "Garanta sua vaga" on mobile */
  .vaga-highlight {
    background-color: var(--primary);
    padding: 1px 4px;
    border-radius: 2px;
    font-weight: 700;
  }

  .no-break {
    white-space: nowrap;
  }

  .countdown {
    gap: 0.5rem;
    flex-shrink: 0;
  }

  .time-box {
    flex-direction: row;
    align-items: baseline;
    gap: 2px;
  }

  .time-val {
    font-size: 0.85rem;
  }

  .time-label {
    font-size: 0.45rem;
    text-transform: lowercase;
  }
}
</style>
