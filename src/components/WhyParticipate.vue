<template>
  <section class="mentor section-padding">
    <div class="container grid">
      <div class="content">
        <h2 class="section-title">Quem será a tua <span class="highlight">mentora?</span></h2>
        <div class="text-block">
          <p>Especialista em Buttercream e apaixonada por ensinar, eu vou levar-te pela mão durante estes 3 dias para que possas dominar esta técnica, mesmo que estejas a começar do zero.</p>
          <p>O meu objetivo é que aprendas a trabalhar com <strong>segurança e profissionalismo</strong>, garantindo que os teus bolos sejam estáveis e deliciosos, mesmo nos climas mais desafiadores como o de Angola.</p>
          <p>Prepara-te para uma transformação na tua carreira na confeitaria. Vemo-nos nas aulas!</p>
        </div>
        <button @click="scrollToForm" class="btn-primary whatsapp-btn">
          Quero me inscrever
        </button>
      </div>
      <div class="image-container">
        <img src="/image00032.jpg" alt="Mentora" class="person-image" />
      </div>
    </div>
  </section>
</template>

<script setup>
const scrollToForm = () => {
  const element = document.getElementById('hero-form')
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
    
    // Attempt to focus the form after a short delay for the scroll to finish
    setTimeout(() => {
      const input = element.querySelector('input')
      if (input) input.focus()
    }, 800)
  }
}
</script>

<style scoped>
.mentor {
  background-color: var(--white);
}

.grid {
  display: grid;
  grid-template-columns: 1.2fr 0.8fr;
  align-items: center;
  gap: 4rem;
}

.section-title {
  font-size: 2.5rem;
  margin-bottom: 2rem;
  color: var(--text);
}

.highlight {
  color: var(--primary);
}

.text-block p {
  font-size: 1.125rem;
  color: var(--text-light);
  margin-bottom: 1.5rem;
}

.whatsapp-btn {
  margin-top: 1rem;
  padding: 1.25rem 2.5rem;
}

.person-image {
  width: 100%;
  border-radius: 2rem;
}

@media (max-width: 992px) {
  .mentor {
    text-align: left;
  }

  .grid {
    grid-template-columns: 1fr;
    gap: 2.5rem;
  }

  .section-title {
    font-size: 1.85rem;
    line-height: 1.1;
  }
  
  .image-container {
    order: -1;
  }

  .whatsapp-btn {
    width: 100%;
  }
}
</style>
