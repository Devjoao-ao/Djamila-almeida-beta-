<template>
  <div class="class-card">
    <div class="card-image">
      <img :src="image" :alt="title" />
    </div>
    <div class="card-content">
      <div class="class-meta">
        <span class="calendar-icon">
          <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="4" width="18" height="18" rx="2" ry="2"></rect><line x1="16" y1="2" x2="16" y2="6"></line><line x1="8" y1="2" x2="8" y2="6"></line><line x1="3" y1="10" x2="21" y2="10"></line></svg>
        </span>
        <span class="date-text">Aula {{ number }}</span>
      </div>
      <p class="date-full">{{ dateText }}</p>
      <h3 class="class-title">{{ title }}</h3>
    </div>
  </div>
</template>

<script setup>
defineProps({
  number: String,
  dateText: String,
  title: String,
  image: String
})
</script>

<style scoped>
.class-card {
  display: grid;
  grid-template-columns: 1fr 1fr;
  background: var(--bg-offset);
  border-radius: 1.5rem;
  overflow: hidden;
  gap: 2rem;
}

.card-image {
  position: relative;
  height: 400px;
  padding: 1.25rem; /* Spacing for the image */
}

.card-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 1rem; /* Rounded image corners */
}

.card-content {
  padding: 2.5rem 2.5rem 2.5rem 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.class-meta {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin-bottom: 0.5rem;
}

.calendar-icon {
  font-size: 1.25rem;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--primary);
}

.date-text {
  font-weight: 800;
  font-size: 0.875rem;
}

.date-full {
  font-size: 0.875rem;
  color: var(--text-light);
  margin-bottom: 1.5rem;
}

.class-title {
  font-size: 1.75rem;
  margin-bottom: 1rem;
  color: var(--text);
}

@media (max-width: 992px) {
  .class-card {
    grid-template-columns: 1fr;
    text-align: left; /* Ensuring left alignment */
  }
  
  .card-content {
    padding: 1rem 1.5rem 2.5rem; /* Better balance */
  }
  
  .card-image {
    height: 300px;
    padding-bottom: 0; /* Tighten space between image and text */
  }

  .class-title {
    font-size: 1.5rem;
  }
}
</style>
