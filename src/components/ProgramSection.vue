<template>
  <section class="program section-padding">
    <div class="container text-center">
      <h2 class="section-title">O que vais aprender nos <span class="highlight">3 dias</span></h2>
      <div class="cards-stack">
        <ClassCard 
          v-for="classItem in classes" 
          :key="classItem.number"
          v-bind="classItem"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
import ClassCard from './ClassCard.vue'

const classes = [
  {
    number: '1',
    dateText: 'Segunda-feira, 23 de fevereiro, às 20h',
    title: 'Por que alguns bolos em Buttercream parecem profissionais e outros não',
    image: '/image00018.jpg'
  },
  {
    number: '2',
    dateText: 'Terça-feira, 24 de fevereiro, às 20h',
    title: 'Como trabalhar com Buttercream com mais segurança, mesmo no calor',
    image: '/image00031.jpg'
  },
  {
    number: '3',
    dateText: 'Quarta-feira, 25 de fevereiro, às 20h',
    title: 'Bolo em Buttercream ao vivo: do zero ao acabamento profissional',
    image: '/image00026.jpg'
  }
]
</script>

<style scoped>
.text-center {
  text-align: center;
}

.section-title {
  font-size: 2.5rem;
  margin-bottom: 3rem;
}

.highlight {
  color: var(--primary);
}

.cards-stack {
  display: flex;
  flex-direction: column;
  gap: 3rem;
}

@media (max-width: 992px) {
  .program {
    text-align: left;
  }
  
  .section-title {
    font-size: 1.85rem;
    line-height: 1.1;
    margin-bottom: 2rem;
  }
}
</style>
