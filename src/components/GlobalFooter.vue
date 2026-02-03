<template>
  <footer class="footer">
    <div class="container footer-content">
      <p class="copyright">© 2026 Djamila Almeida | Todos os direitos reservados.</p>
      <div class="footer-links">
        <a href="#">Política de Privacidade e Termos de Uso</a>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background-color: var(--secondary);
  color: var(--white);
  padding: 1.5rem 0;
  margin-top: auto;
}

.footer-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 0.75rem;
  opacity: 0.6;
}

.footer-links a {
  text-decoration: underline;
}

@media (max-width: 992px) {
  .footer-content {
    flex-direction: column;
    gap: 1rem;
    align-items: flex-start;
    text-align: left;
  }
}
</style>
