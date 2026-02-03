<template>
  <div class="lead-form-container">
    <form @submit.prevent="handleSubmit" class="lead-form">
      <div class="form-group">
        <label for="name">Seu nome</label>
        <input ref="nameInput" type="text" id="name" v-model="form.name" placeholder="Digite seu nome completo" required />
      </div>
      <div class="form-group">
        <label for="email">Seu melhor e-mail</label>
        <input type="email" id="email" v-model="form.email" placeholder="Digite seu e-mail" required />
      </div>
      <div class="form-group">
        <label for="whatsapp">Seu WhatsApp</label>
        <input type="tel" id="whatsapp" v-model="form.whatsapp" placeholder="+244 9XX XXX XXX" required />
      </div>
      <button type="submit" class="btn-primary form-submit">
        Quero me inscrever
      </button>
      <p class="form-footer">Sem spam. Apenas conteúdo de valor.</p>
    </form>
  </div>
</template>

<script setup>
import { reactive, ref } from 'vue'

const form = reactive({
  name: '',
  email: '',
  whatsapp: ''
})

const nameInput = ref(null)

const focusForm = () => {
  if (nameInput.value) {
    nameInput.value.focus()
  }
}

defineExpose({ focusForm })

const handleSubmit = () => {
  console.log('Lead capture:', form)
  // Redirecionamento para o grupo de WhatsApp
  window.location.href = 'https://chat.whatsapp.com/LAD4TQQ61u0LM1Uzay69fu'
}
</script>

<style scoped>
.lead-form-container {
  background: rgba(255, 255, 255, 0.1); /* Slightly more visible */
  backdrop-filter: blur(20px); /* Stronger blur for better contrast */
  padding: 1rem 1.75rem; /* Reduced from 1.5rem 2rem */
  border-radius: 1.5rem;
  border: 1px solid rgba(255, 255, 255, 0.1);
  width: 100%;
}

.lead-form {
  display: flex;
  flex-direction: column;
  gap: 0.75rem; /* Reduced from 1rem */
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 0.35rem; /* Reduced from 0.5rem */
}

.form-group label {
  font-size: 0.8125rem;
  font-weight: 600;
  color: rgba(255, 255, 255, 0.8); /* Soft white label */
  letter-spacing: 0.02em;
}

.form-group input {
  background: rgba(255, 255, 255, 0.08);
  padding: 0.65rem 1rem; /* Reduced from 0.8rem */
  border: 1px solid rgba(255, 255, 255, 0.15);
  border-radius: 0.75rem;
  font-family: inherit;
  font-size: 0.9375rem; /* Reduced from 1rem */
  color: var(--white);
  outline: none;
  transition: all 0.3s ease;
}

.form-group input::placeholder {
  color: rgba(255, 255, 255, 0.4);
}

.form-group input:focus {
  background: rgba(255, 255, 255, 0.12);
  border-color: var(--primary);
  box-shadow: 0 0 15px rgba(162, 27, 96, 0.2);
}

.form-submit {
  padding: 0.9rem; /* Reduced from 1.15rem */
  font-size: 0.9375rem; /* Reduced from 1rem */
  margin-top: 0.25rem; /* Reduced from 0.5rem */
  box-shadow: 0 10px 20px rgba(162, 27, 96, 0.3);
}

.form-footer {
  text-align: center;
  font-size: 0.75rem;
  color: rgba(255, 255, 255, 0.5);
  margin-top: 0.25rem;
}

@media (max-width: 992px) {
  .lead-form-container {
    padding: 1.25rem 1.5rem;
  }
}
</style>
