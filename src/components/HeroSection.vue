<template>
  <section class="hero section-padding">
    <div class="container hero-grid">
      <div class="hero-content">
        <div class="header-info">
          <div class="logo">
            <span class="desafio">Treinamento</span>
            <span class="bastidores">Buttercream</span>
            <span class="do-digital">sem segredo</span>
          </div>
          <div class="event-meta">
            <div class="meta-item">
              <span class="icon">
                <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="4" width="18" height="18" rx="2" ry="2"></rect><line x1="16" y1="2" x2="16" y2="6"></line><line x1="8" y1="2" x2="8" y2="6"></line><line x1="3" y1="10" x2="21" y2="10"></line></svg>
              </span>
              <span class="text">23, 24 e 25 de fevereiro</span>
            </div>
            <div class="meta-item">
              <span class="icon">
                <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M19.615 3.184c-3.604-.246-11.631-.245-15.23 0-3.897.266-4.356 2.62-4.385 8.816.029 6.185.484 8.549 4.385 8.816 3.6.245 11.626.246 15.23 0 3.897-.266 4.356-2.62 4.385-8.816-.029-6.185-.484-8.549-4.385-8.816zm-10.615 12.816v-8l8 3.993-8 4.007z"/></svg>
              </span>
              <span class="text">Ao vivo no YouTube</span>
            </div>
          </div>
        </div>

        <h1 class="hero-title">
          Domina o Buttercream em 3 dias, mesmo sendo <span class="highlight-marker">iniciante</span>
        </h1>
        
        <p class="hero-description">
          Aprende a trabalhar com segurança para ser bem paga e ocupar um novo lugar no mercado. 3 aulas gratuitas para aprenderes, passo a passo, como trabalhar com Buttercream estável, seguro e profissional, mesmo no calor de Angola.
        </p>

        <div id="hero-form" class="hero-form-wrapper">
          <LeadForm />
        </div>
      </div>

      <div class="hero-empty-space" />
    </div>
  </section>
</template>

<script setup>
import LeadForm from './LeadForm.vue'
</script>

<style scoped>
.hero {
  background-image: url('/hero.png');
  background-size: 100% auto;
  background-position: center -30px;
  background-repeat: no-repeat;
  padding: 6rem 0;
  color: var(--white);
  min-height: 95vh;
  display: flex;
  align-items: center;
  position: relative;
}

.hero::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(to right, rgba(0,0,0,0.8) 0%, rgba(0,0,0,0.2) 100%);
  z-index: 0;
}

.hero-grid {
  position: relative;
  z-index: 1;
  display: grid;
  grid-template-columns: 1.2fr 0.8fr; /* More space for the content + form */
  align-items: center;
  gap: 4rem;
}

.hero-form-wrapper {
  margin-top: 2.5rem;
  max-width: 480px; /* Wider as requested */
}

.logo {
  display: flex;
  flex-direction: column;
  line-height: 0.9;
  margin-bottom: 2rem;
}

.desafio { font-size: 1.125rem; font-weight: 400; color: rgba(255, 255, 255, 0.7); }
.bastidores { font-size: 2.25rem; font-weight: 900; color: var(--white); }
.do-digital { font-size: 1.25rem; font-weight: 700; color: var(--white); }

.event-meta {
  display: flex;
  gap: 2rem;
  margin-bottom: 3rem;
}

.meta-item {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-size: 0.875rem;
  font-weight: 700;
}

.icon {
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--primary);
}

.hero-title {
  font-size: 2.75rem;
  margin-bottom: 1.5rem;
  color: var(--white);
  line-height: 1.2;
}

.highlight-marker {
  position: relative;
  z-index: 1;
  display: inline-block;
  padding: 0 4px;
}

.highlight-marker::after {
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
  animation-delay: 1s;
  border-radius: 2px;
}

@keyframes highlight-draw {
  to {
    transform: scaleX(1);
  }
}

.hero-description {
  font-size: 1.1rem;
  color: rgba(255, 255, 255, 0.9);
  max-width: 550px;
  line-height: 1.6;
}

@media (max-width: 994px) {
  .hero {
    min-height: 100vh; /* Restore full height impact */
    text-align: left;
    background-size: cover;
    background-position: 75% center; /* Precisely frame mentora */
    padding: 6rem 0 4rem;
    display: flex;
    align-items: flex-end; /* Text and form at the bottom/center */
  }

  .hero::before {
    background: linear-gradient(to top, rgba(0,0,0,0.95) 0%, rgba(0,0,0,0.4) 100%);
  }

  .hero-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
    transform: translateY(0);
    width: 100%;
  }
  
  .logo, .event-meta {
    justify-content: flex-start;
  }

  .hero-form-wrapper {
    margin-top: 1.5rem;
    max-width: 100%;
  }

  .bastidores { font-size: 1.85rem; }
  .do-digital { font-size: 1.15rem; }

  .hero-title {
    font-size: 2.15rem;
    line-height: 1.1;
    margin-bottom: 1rem;
  }

  .hero-description {
    font-size: 1rem;
    line-height: 1.4;
  }
}
</style>
