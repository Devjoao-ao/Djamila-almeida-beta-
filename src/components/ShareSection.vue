<template>
  <section class="share section-padding">
    <div class="container text-center">
      <h2 class="section-title">Conhecimento bom é <span class="highlight">conhecimento compartilhado!</span></h2>
      <div class="share-box">
        <p>O Treinamento Domina o Buttercream será um verdadeiro passo a passo para quem deseja aprender como trabalhar com segurança e ser bem paga no mercado de confeitaria.</p>
        <p>Por isso, se você conhece alguém que já atua (ou deseja atuar) com bolos e quer profissionalizar sua atuação para obter resultados melhores, faça um convite copiando o link abaixo. Você estará fazendo a essa pessoa um grande favor.</p>
        <button class="btn-primary share-btn" @click="copyLink">
          <span class="icon">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg>
          </span>
          Copiar link da página
        </button>
      </div>
    </div>
  </section>
</template>

<script setup>
const copyLink = () => {
  navigator.clipboard.writeText(window.location.href)
  alert('Link copiado!')
}
</script>

<style scoped>
.share {
  background-color: var(--white);
}

.text-center {
  text-align: center;
}

.section-title {
  font-size: 2.5rem;
  margin-bottom: 2rem;
}

.highlight {
  color: var(--primary);
}

.share-box {
  max-width: 800px;
  margin: 0 auto;
}

.share-box p {
  font-size: 1.125rem;
  color: var(--text-light);
  margin-bottom: 1.5rem;
}

.share-btn {
  margin-top: 1.5rem;
  padding: 1.25rem 3rem;
  border-radius: 100px;
}
@media (max-width: 992px) {
  .share {
    text-align: left;
  }

  .text-center {
    text-align: left;
  }

  .section-title {
    font-size: 1.85rem;
    line-height: 1.1;
  }

  .share-box p {
    font-size: 1rem;
  }

  .share-btn {
    width: 100%;
    padding: 1.25rem 1.5rem;
  }
}
</style>
