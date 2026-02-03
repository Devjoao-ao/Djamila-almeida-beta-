<template>
  <section class="advantages section-padding">
    <div class="container">
      <h2 class="section-title">Como <span class="highlight">aproveitar 100%</span> do treinamento Domina o Buttercream</h2>
      <p class="section-subtitle">O Domina o Buttercream será a sua porta de entrada para o sucesso na confeitaria, por isso, aqui vão algumas dicas para que você possa aproveitar 100% do conteúdo.</p>
      
      <div class="advantages-grid">
        <div class="adv-card" v-for="(adv, index) in advantages" :key="index">
          <span class="adv-number">{{ index + 1 }}.</span>
          <h3 class="adv-title" v-html="adv.title"></h3>
          <p class="adv-desc" v-html="adv.desc"></p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const advantages = [
  {
    title: 'Mantenha a sua agenda livre para o evento',
    desc: 'De 23 a 25 de fevereiro, às 20h (horário de Brasília), você tem um compromisso comigo. Dedique a eles toda a sua atenção.'
  },
  {
    title: 'Assista em um lugar confortável e faça o seu tempo valer',
    desc: 'Prepare-se para aulas intensas e de alto nível. Cada aula deve durar, em média, <strong>duas horas</strong>. O treinamento não é para ouvir enquanto você faz outras coisas. Por isso, <strong>evite distrações</strong> e assista pelo computador para aproveitar melhor.'
  },
  {
    title: 'Revise os conteúdos com os materiais de apoio',
    desc: 'Ao final das aulas, liberamos materiais de apoio em PDF. Neles, você encontrará um <strong>material exclusivo</strong> para fixar o conteúdo. Para <strong>abrir</strong> o PDF, será necessário inserir uma senha divulgada ao vivo durante a aula.'
  }
]
</script>

<style scoped>
.advantages {
  background-color: var(--bg-offset);
  text-align: center;
}

.section-title {
  font-size: 2.25rem;
  margin-bottom: 1rem;
}

.highlight {
  color: var(--primary);
}

.section-subtitle {
  color: var(--text-light);
  max-width: 800px;
  margin: 0 auto 4rem;
}

.advantages-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  text-align: left;
}

.adv-card {
  background: var(--white);
  padding: 2.5rem;
  border-radius: 1.5rem;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.adv-number {
  color: var(--primary);
  font-size: 1.5rem;
  font-weight: 800;
}

.adv-title {
  font-size: 1.25rem;
  line-height: 1.2;
}

.adv-desc {
  font-size: 0.9375rem;
  color: var(--text-light);
  line-height: 1.6;
}

@media (max-width: 992px) {
  .advantages {
    text-align: left;
  }

  .section-title {
    font-size: 1.85rem;
    line-height: 1.1;
  }

  .section-subtitle {
    margin: 0 0 2rem 0;
  }

  .advantages-grid {
    grid-template-columns: 1fr;
  }

  .adv-card {
    padding: 2rem 1.5rem;
  }
}
</style>
