<template>
  <section id="hero" class="hero">
    <div class="container">
      <h1>Olá, meu nome é Afonso!</h1>
      <p>Desenvolvedor Web</p>
      <a
        href="https://drive.google.com/file/d/1l7pkpYEIEc3H98Si0-g1oTY4CeofC52e/view?usp=sharing"
        target="_blank"
        class="btn btn-secondary"
        download
        >Obter Currículo</a
      >
    </div>
  </section>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Hero',
}
</script>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.hero p {
  margin-bottom: var(--spacing-md);
}
</style>
