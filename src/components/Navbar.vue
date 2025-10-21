<template>
  <nav class="navbar">
    <div class="container">
      <a href="#hero">Meu Portfólio</a>
      <ul>
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
}
</script>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  width: 100%;
  background: white;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  z-index: 1000;
}

ul {
  display: flex;
  gap: 2rem;
  list-style: none;
}
</style>
