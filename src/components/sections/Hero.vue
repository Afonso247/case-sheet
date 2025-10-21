<template>
  <section id="hero" class="hero">
    <div class="container">
      <h1>Olá, eu sou [Seu Nome]</h1>
      <p>Desenvolvedor Web</p>
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
</style>
