<template>
  <nav class="navbar" :class="{ 'navbar-hidden': !showNavbar }">
    <div class="container">
      <a href="#hero" class="logo" @click="closeMobileMenu">Case Sheet</a>

      <!-- Botão Hamburger (visível apenas em mobile) -->
      <button
        class="hamburger"
        :class="{ active: mobileMenuOpen }"
        @click="toggleMobileMenu"
        aria-label="Menu"
      >
        <span></span>
        <span></span>
        <span></span>
      </button>

      <!-- Menu de navegação -->
      <ul class="nav-links" :class="{ 'mobile-open': mobileMenuOpen }">
        <li><a href="#about" @click="closeMobileMenu">Sobre</a></li>
        <li><a href="#projects" @click="closeMobileMenu">Projetos</a></li>
        <li><a href="#skills" @click="closeMobileMenu">Habilidades</a></li>
        <li><a href="#contact" @click="closeMobileMenu">Contato</a></li>
      </ul>
    </div>

    <!-- Overlay para fechar o menu ao clicar fora (mobile) -->
    <div v-if="mobileMenuOpen" class="overlay" @click="closeMobileMenu"></div>
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
      scrollThreshold: 50,
      touchStartY: 0,
      mobileMenuOpen: false,
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
    window.addEventListener('touchstart', this.handleTouchStart, { passive: true })
    window.addEventListener('touchmove', this.handleTouchMove, { passive: true })
    window.addEventListener('resize', this.handleResize)
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll)
    window.removeEventListener('touchstart', this.handleTouchStart)
    window.removeEventListener('touchmove', this.handleTouchMove)
    window.removeEventListener('resize', this.handleResize)
  },
  methods: {
    handleScroll() {
      const currentScrollPosition = window.pageYOffset || document.documentElement.scrollTop

      if (currentScrollPosition < 0) {
        return
      }

      if (currentScrollPosition < this.scrollThreshold) {
        this.showNavbar = true
        this.lastScrollPosition = currentScrollPosition
        return
      }

      if (currentScrollPosition > this.lastScrollPosition) {
        this.showNavbar = false
        this.closeMobileMenu() // Fecha o menu ao scrollar para baixo
      } else {
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

      if (currentScrollPosition < this.scrollThreshold) {
        this.showNavbar = true
        return
      }

      if (Math.abs(touchDiff) > 10) {
        if (touchDiff > 0) {
          this.showNavbar = false
          this.closeMobileMenu()
        } else {
          this.showNavbar = true
        }

        this.touchStartY = touchCurrentY
      }
    },

    handleResize() {
      // Fecha o menu mobile se a tela for redimensionada para desktop
      if (window.innerWidth > 768 && this.mobileMenuOpen) {
        this.closeMobileMenu()
      }
    },

    toggleMobileMenu() {
      this.mobileMenuOpen = !this.mobileMenuOpen

      // Previne scroll quando o menu está aberto
      if (this.mobileMenuOpen) {
        document.body.style.overflow = 'hidden'
      } else {
        document.body.style.overflow = ''
      }
    },

    closeMobileMenu() {
      this.mobileMenuOpen = false
      document.body.style.overflow = ''
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
  position: relative;
}

.logo {
  font-size: var(--text-xl);
  font-weight: 700;
  color: var(--color-text-primary);
  text-decoration: none;
  transition: color var(--transition-base);
  z-index: 1001;
}

.logo:hover {
  color: var(--color-primary);
}

/* Botão Hamburger */
.hamburger {
  display: none;
  flex-direction: column;
  justify-content: space-between;
  width: 28px;
  height: 21px;
  background: transparent;
  border: none;
  cursor: pointer;
  padding: 0;
  z-index: 1001;
  transition: transform var(--transition-base);
}

.hamburger span {
  width: 100%;
  height: 3px;
  background-color: var(--color-text-primary);
  border-radius: 2px;
  transition: all var(--transition-base);
  transform-origin: center;
}

.hamburger.active span:nth-child(1) {
  transform: translateY(9px) rotate(45deg);
}

.hamburger.active span:nth-child(2) {
  opacity: 0;
  transform: translateX(-20px);
}

.hamburger.active span:nth-child(3) {
  transform: translateY(-9px) rotate(-45deg);
}

.hamburger:hover span {
  background-color: var(--color-primary);
}

/* Menu de navegação */
.nav-links {
  display: flex;
  gap: 2rem;
  list-style: none;
  align-items: center;
  margin: 0;
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

/* Overlay */
.overlay {
  display: none;
}

/* Responsividade - Tablet */
@media (max-width: 768px) {
  .hamburger {
    display: flex;
  }

  .nav-links {
    position: fixed;
    top: 0;
    right: 0;
    width: 70%;
    max-width: 300px;
    height: 100vh;
    background-color: var(--color-bg-secondary);
    flex-direction: column;
    gap: 0;
    align-items: flex-start;
    padding: 5rem 2rem 2rem;
    transform: translateX(100%);
    transition: transform var(--transition-base);
    box-shadow: -5px 0 15px rgba(0, 0, 0, 0.3);
    overflow-y: auto;
    z-index: 1001;
  }

  .nav-links.mobile-open {
    transform: translateX(0);
  }

  .nav-links li {
    width: 100%;
    border-bottom: 1px solid rgba(109, 158, 235, 0.1);
  }

  .nav-links a {
    display: block;
    width: 100%;
    padding: 1.25rem 0;
    font-size: var(--text-lg);
    color: var(--color-text-primary);
  }

  .nav-links a::after {
    display: none;
  }

  .nav-links a:hover {
    padding-left: 0.5rem;
    color: var(--color-primary);
  }

  .overlay {
    display: block;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    background-color: rgba(0, 0, 0, 0.7);
    z-index: 999;
    animation: fadeIn 0.3s ease;
  }

  @keyframes fadeIn {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }
}

/* Mobile pequeno */
@media (max-width: 480px) {
  .navbar .container {
    padding: 1rem;
  }

  .logo {
    font-size: var(--text-lg);
  }

  .nav-links {
    width: 80%;
  }
}
</style>
