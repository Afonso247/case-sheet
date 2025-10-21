<template>
  <nav class="navbar" :class="{ 'navbar-hidden': !showNavbar }">
    <div class="container">
      <a href="#hero" class="logo">Meu Portfólio</a>
      <ul class="nav-links">
        <li><a href="#about">Sobre</a></li>
        <li><a href="#projects">Projetos</a></li>
        <li><a href="#skills">Habilidades</a></li>
        <li><a href="#contact">Contato</a></li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Navbar',
  data() {
    return {
      showNavbar: true,
      lastScrollPosition: 0,
      scrollThreshold: 50, // Pixels necessários para disparar a ação
      touchStartY: 0,
    }
  },
  mounted() {
    // Listener para scroll
    window.addEventListener('scroll', this.handleScroll)

    // Listeners para touch (mobile)
    window.addEventListener('touchstart', this.handleTouchStart, { passive: true })
    window.addEventListener('touchmove', this.handleTouchMove, { passive: true })
  },
  beforeUnmount() {
    // Remove os listeners ao destruir o componente
    window.removeEventListener('scroll', this.handleScroll)
    window.removeEventListener('touchstart', this.handleTouchStart)
    window.removeEventListener('touchmove', this.handleTouchMove)
  },
  methods: {
    handleScroll() {
      const currentScrollPosition = window.pageYOffset || document.documentElement.scrollTop

      // Evita valores negativos
      if (currentScrollPosition < 0) {
        return
      }

      // Sempre mostra navbar no topo da página
      if (currentScrollPosition < this.scrollThreshold) {
        this.showNavbar = true
        this.lastScrollPosition = currentScrollPosition
        return
      }

      // Verifica a direção do scroll
      if (currentScrollPosition > this.lastScrollPosition) {
        // Scrollando para baixo - esconde navbar
        this.showNavbar = false
      } else {
        // Scrollando para cima - mostra navbar
        this.showNavbar = true
      }

      this.lastScrollPosition = currentScrollPosition
    },

    handleTouchStart(event) {
      this.touchStartY = event.touches[0].clientY
    },

    handleTouchMove(event) {
      const currentScrollPosition = window.pageYOffset || document.documentElement.scrollTop
      const touchCurrentY = event.touches[0].clientY
      const touchDiff = this.touchStartY - touchCurrentY

      // Sempre mostra navbar no topo da página
      if (currentScrollPosition < this.scrollThreshold) {
        this.showNavbar = true
        return
      }

      // Se o movimento for maior que um threshold (para evitar movimentos acidentais)
      if (Math.abs(touchDiff) > 10) {
        if (touchDiff > 0) {
          // Deslizando para cima (scrollando para baixo) - esconde navbar
          this.showNavbar = false
        } else {
          // Deslizando para baixo (scrollando para cima) - mostra navbar
          this.showNavbar = true
        }

        // Atualiza a posição inicial para o próximo movimento
        this.touchStartY = touchCurrentY
      }
    },
  },
}
</script>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  width: 100%;
  background-color: var(--color-bg-secondary);
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.5);
  z-index: 1000;
  transition: transform 0.3s ease-in-out;
  transform: translateY(0);
}

.navbar-hidden {
  transform: translateY(-100%);
}

.navbar .container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1rem 2rem;
}

.logo {
  font-size: var(--text-xl);
  font-weight: 700;
  color: var(--color-text-primary);
  text-decoration: none;
  transition: color var(--transition-base);
}

.logo:hover {
  color: var(--color-primary);
}

.nav-links {
  display: flex;
  gap: 2rem;
  list-style: none;
  align-items: center;
}

.nav-links a {
  color: var(--color-text-secondary);
  text-decoration: none;
  font-weight: 500;
  font-size: var(--text-base);
  position: relative;
  transition: color var(--transition-base);
}

.nav-links a::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 0;
  height: 2px;
  background: var(--gradient-primary);
  transition: width var(--transition-base);
}

.nav-links a:hover {
  color: var(--color-primary);
}

.nav-links a:hover::after {
  width: 100%;
}

/* Responsividade */
@media (max-width: 768px) {
  .navbar .container {
    padding: 1rem;
  }

  .nav-links {
    gap: 1rem;
  }

  .nav-links a {
    font-size: var(--text-sm);
  }
}

@media (max-width: 480px) {
  .nav-links {
    gap: 0.75rem;
  }

  .nav-links a {
    font-size: var(--text-xs);
  }

  .logo {
    font-size: var(--text-lg);
  }
}
</style>
