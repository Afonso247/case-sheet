<template>
  <section id="contact" class="contact">
    <div class="container">
      <div class="contact-content">
        <!-- Header -->
        <div class="contact-header">
          <h2 class="text-gradient fade-in">Entre em Contato</h2>
          <div class="underline"></div>
          <p class="contact-subtitle">
            Tem um projeto em mente ou quer apenas trocar uma ideia? Ficarei feliz em conversar com
            você!
          </p>
        </div>

        <!-- Grid: Formulário + Info -->
        <div class="contact-grid">
          <!-- Informações de Contato -->
          <div class="contact-info slide-in-left">
            <div class="info-card card">
              <h3>Converse comigo</h3>
              <p>Estou sempre aberto a discutir novos projetos, ideias ou oportunidades!</p>

              <div class="contact-methods">
                <!-- Email -->
                <button
                  @click="copyToClipboard('afonsoh.dev@gmail.com', 'email')"
                  class="contact-item"
                >
                  <div class="contact-icon">
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      width="24"
                      height="24"
                      viewBox="0 0 24 24"
                      fill="none"
                      stroke="currentColor"
                      stroke-width="2"
                    >
                      <rect x="2" y="4" width="20" height="16" rx="2" />
                      <path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7" />
                    </svg>
                  </div>
                  <div class="contact-text">
                    <h4>Email {{ copiedField === 'email' ? '(Copiado!)' : '' }}</h4>
                    <p>afonsoh.dev@gmail.com</p>
                  </div>
                </button>

                <!-- Telefone -->
                <button @click="copyToClipboard('+5581982926061', 'phone')" class="contact-item">
                  <div class="contact-icon">
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      width="24"
                      height="24"
                      viewBox="0 0 24 24"
                      fill="none"
                      stroke="currentColor"
                      stroke-width="2"
                    >
                      <path
                        d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"
                      />
                    </svg>
                  </div>
                  <div class="contact-text">
                    <h4>Telefone {{ copiedField === 'phone' ? '(Copiado!)' : '' }}</h4>
                    <p>+55 (81) 98292-6061</p>
                  </div>
                </button>

                <!-- Localização -->
                <div class="contact-item contact-item-static">
                  <div class="contact-icon">
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      width="24"
                      height="24"
                      viewBox="0 0 24 24"
                      fill="none"
                      stroke="currentColor"
                      stroke-width="2"
                    >
                      <path d="M20 10c0 6-8 12-8 12s-8-6-8-12a8 8 0 0 1 16 0Z" />
                      <circle cx="12" cy="10" r="3" />
                    </svg>
                  </div>
                  <div class="contact-text">
                    <h4>Localização</h4>
                    <p>Recife, Pernambuco, Brasil</p>
                  </div>
                </div>
              </div>

              <!-- Redes Sociais -->
              <div class="social-links">
                <h4>Me Encontre Aqui</h4>
                <div class="social-icons">
                  <a
                    href="https://github.com/Afonso247"
                    target="_blank"
                    rel="noopener"
                    class="social-icon"
                  >
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      width="24"
                      height="24"
                      viewBox="0 0 24 24"
                      fill="currentColor"
                    >
                      <path
                        d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"
                      />
                    </svg>
                  </a>
                  <a
                    href="https://linkedin.com/in/afonso-h"
                    target="_blank"
                    rel="noopener"
                    class="social-icon"
                  >
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      width="24"
                      height="24"
                      viewBox="0 0 24 24"
                      fill="currentColor"
                    >
                      <path
                        d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"
                      />
                    </svg>
                  </a>
                </div>
              </div>
            </div>
          </div>

          <!-- Formulário -->
          <div class="contact-form-wrapper slide-in-right">
            <form @submit.prevent="handleSubmit" class="contact-form card">
              <div class="form-group">
                <label for="name">Nome Completo</label>
                <input
                  type="text"
                  id="name"
                  v-model="formData.name"
                  placeholder="João Silva"
                  required
                />
              </div>

              <div class="form-group">
                <label for="email">E-mail</label>
                <input
                  type="email"
                  id="email"
                  v-model="formData.email"
                  placeholder="joao@exemplo.com"
                  required
                />
              </div>

              <div class="form-group">
                <label for="subject">Assunto</label>
                <input
                  type="text"
                  id="subject"
                  v-model="formData.subject"
                  placeholder="Proposta de Projeto"
                  required
                />
              </div>

              <div class="form-group">
                <label for="message">Mensagem</label>
                <textarea
                  id="message"
                  v-model="formData.message"
                  rows="6"
                  placeholder="Conte-me sobre seu projeto ou ideia..."
                  required
                ></textarea>
              </div>

              <button type="submit" class="btn btn-accent submit-btn">
                <span v-if="!isSubmitting">Enviar Mensagem</span>
                <span v-else>Enviando...</span>
              </button>

              <p v-if="submitMessage" :class="['submit-message', submitStatus]">
                {{ submitMessage }}
              </p>
            </form>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Contact',
  data() {
    return {
      formData: {
        name: '',
        email: '',
        subject: '',
        message: '',
      },
      isSubmitting: false,
      submitMessage: '',
      submitStatus: '',
      copiedField: null,
    }
  },
  methods: {
    async copyToClipboard(text, field) {
      try {
        await navigator.clipboard.writeText(text)
        this.copiedField = field

        // Remove a indicação após 2 segundos
        setTimeout(() => {
          this.copiedField = null
        }, 2000)
      } catch (err) {
        console.error('Erro ao copiar:', err)
        // Fallback para navegadores antigos
        const textArea = document.createElement('textarea')
        textArea.value = text
        document.body.appendChild(textArea)
        textArea.select()
        try {
          document.execCommand('copy')
          this.copiedField = field
          setTimeout(() => {
            this.copiedField = null
          }, 2000)
        } catch (err) {
          console.error('Fallback: Erro ao copiar', err)
        }
        document.body.removeChild(textArea)
      }
    },
    async handleSubmit() {
      this.isSubmitting = true
      this.submitMessage = ''

      // Simula envio (substitua pela sua lógica de envio real)
      setTimeout(() => {
        this.isSubmitting = false
        this.submitStatus = 'success'
        this.submitMessage = 'Mensagem enviada com sucesso! Entrarei em contato em breve.'

        // Limpa o formulário
        this.formData = {
          name: '',
          email: '',
          subject: '',
          message: '',
        }

        // Limpa a mensagem após 5 segundos
        setTimeout(() => {
          this.submitMessage = ''
        }, 5000)
      }, 2000)
    },
  },
}
</script>

<style scoped>
.contact {
  background-color: var(--color-bg-base);
}

.contact-content {
  width: 100%;
}

.contact-header {
  text-align: center;
  margin-bottom: var(--spacing-lg);
}

.underline {
  width: 80px;
  height: 4px;
  background: var(--gradient-primary);
  margin: var(--spacing-sm) auto;
  border-radius: var(--radius-full);
}

.contact-subtitle {
  max-width: 600px;
  margin: var(--spacing-md) auto 0;
  font-size: var(--text-lg);
  color: var(--color-text-secondary);
}

.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: var(--spacing-lg);
  align-items: start;
}

/* Informações de Contato */
.info-card {
  padding: var(--spacing-lg);
  height: 100%;
}

.info-card h3 {
  margin-bottom: var(--spacing-sm);
}

.info-card > p {
  margin-bottom: var(--spacing-md);
}

.contact-methods {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-md);
  margin-bottom: var(--spacing-lg);
}

.contact-item {
  display: flex;
  align-items: start;
  gap: var(--spacing-sm);
  padding: var(--spacing-sm);
  border-radius: var(--radius-md);
  transition: all var(--transition-base);
  text-decoration: none;
  color: inherit;
  background: none;
  border: none;
  width: 100%;
  text-align: left;
  cursor: pointer;
  font-family: var(--font-primary);
}

.contact-item-static {
  cursor: default;
}

.contact-item:not(.contact-item-static):hover {
  background-color: var(--color-bg-base);
  transform: translateX(5px);
}

.contact-item:not(.contact-item-static):active {
  transform: translateX(5px) scale(0.98);
}

.contact-icon {
  width: 48px;
  height: 48px;
  min-width: 48px;
  background: var(--gradient-primary);
  border-radius: var(--radius-md);
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--color-bg-base);
}

.contact-text h4 {
  font-size: var(--text-base);
  color: var(--color-text-primary);
  margin-bottom: 0.25rem;
  transition: color var(--transition-fast);
}

.contact-text p {
  font-size: var(--text-sm);
  color: var(--color-text-secondary);
  margin: 0;
}

/* Redes Sociais */
.social-links {
  padding-top: var(--spacing-md);
  border-top: 1px solid rgba(109, 158, 235, 0.2);
}

.social-links h4 {
  margin-bottom: var(--spacing-sm);
  font-size: var(--text-base);
}

.social-icons {
  display: flex;
  gap: var(--spacing-sm);
}

.social-icon {
  width: 48px;
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: var(--color-bg-base);
  border-radius: var(--radius-md);
  color: var(--color-primary);
  transition: all var(--transition-base);
  border: 2px solid transparent;
}

.social-icon:hover {
  background-color: var(--color-primary);
  color: var(--color-bg-base);
  border-color: var(--color-primary);
  transform: translateY(-3px);
}

/* Formulário */
.contact-form {
  padding: var(--spacing-lg);
}

.form-group {
  margin-bottom: var(--spacing-md);
}

.submit-btn {
  width: 100%;
  padding: 1rem;
  font-size: var(--text-lg);
  font-weight: 700;
  cursor: pointer;
}

.submit-btn:disabled {
  opacity: 0.6;
  cursor: not-allowed;
}

.submit-message {
  margin-top: var(--spacing-sm);
  padding: var(--spacing-sm);
  border-radius: var(--radius-md);
  text-align: center;
  font-size: var(--text-sm);
}

.submit-message.success {
  background-color: rgba(109, 158, 235, 0.1);
  color: var(--color-primary);
  border: 1px solid var(--color-primary);
}

.submit-message.error {
  background-color: rgba(255, 82, 82, 0.1);
  color: #ff5252;
  border: 1px solid #ff5252;
}

/* Responsividade */
@media (max-width: 968px) {
  .contact-grid {
    grid-template-columns: 1fr;
  }

  .contact-info {
    order: 2;
  }

  .contact-form-wrapper {
    order: 1;
  }
}

@media (max-width: 480px) {
  .social-icons {
    flex-wrap: wrap;
  }

  .contact-subtitle {
    font-size: var(--text-base);
  }
}
</style>
