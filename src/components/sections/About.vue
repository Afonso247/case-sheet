<template>
  <section id="about" class="about">
    <div class="container">
      <div class="about-content">
        <div class="about-text">
          <h2 class="fade-in">Sobre <span class="text-gradient">Mim</span></h2>
          <p class="lead">
            Olá! Sou um desenvolvedor apaixonado por criar soluções digitais incríveis.
          </p>
          <p>
            Meu primeiro contato com o mundo da tecnologia foi por volta de 2018, quando comecei a
            estudar programação. Possuo experiência profissional desde 2023, e desde então, minha
            jornada tem sido uma de aprendizado e crescimento, buscando sempre trazer o meu melhor
            em cada projeto.
          </p>
          <p>
            Atualmente, foco em criar aplicações modernas e responsivas utilizando as tecnologias
            atuais do mercado. Adoro trazer ideias do papel e transforma-las em soluções funcionais
            e elegantes.
          </p>
          <p>
            Quando não estou codando, gosto de jogar games, ouvir música e me exercitar. Acredito
            que um bom equilíbrio entre vida pessoal e profissional é fundamental para viver uma
            vida produtiva e satisfatoria.
          </p>

          <div class="about-stats">
            <div class="stat-item">
              <h3 class="text-primary">2+</h3>
              <p>Anos de Experiência</p>
            </div>
            <div class="stat-item">
              <h3 class="text-secondary">10+</h3>
              <p>Projetos Concluídos</p>
            </div>
            <div class="stat-item">
              <h3 class="text-accent">25+</h3>
              <p>Xícaras de Café</p>
            </div>
          </div>
        </div>

        <div class="about-image">
          <div class="image-wrapper">
            <!-- Substitua o src pela sua foto -->
            <img
              src="https://via.placeholder.com/400x500/1C1C22/6D9EEB?text=Sua+Foto"
              alt="Seu Nome"
            />
            <div class="image-overlay"></div>
          </div>

          <div class="tech-stack">
            <div class="tech-item" title="JavaScript">
              <img
                src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg"
                alt="JavaScript"
              />
            </div>
            <div class="tech-item" title="Vue.js">
              <img
                src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg"
                alt="Vue.js"
              />
            </div>
            <div class="tech-item" title="Node.js">
              <img
                src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg"
                alt="Node.js"
              />
            </div>
            <div class="tech-item" title="MongoDB">
              <img
                src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mongodb/mongodb-original.svg"
                alt="MongoDB"
              />
            </div>
            <div class="tech-item" title="Flutter">
              <img
                src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/flutter/flutter-original.svg"
                alt="Flutter"
              />
            </div>
            <div class="tech-item" title="Git">
              <img
                src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg"
                alt="Git"
              />
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'About',
}
</script>

<style scoped>
.about {
  background-color: var(--color-bg-secondary);
}

.about-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: var(--spacing-lg);
  align-items: center;
}

.about-text h2 {
  font-size: var(--text-4xl);
  margin-bottom: var(--spacing-md);
}

.lead {
  font-size: var(--text-xl);
  color: var(--color-text-primary);
  font-weight: 500;
  margin-bottom: var(--spacing-md);
}

.about-text p {
  margin-bottom: var(--spacing-sm);
  line-height: 1.8;
}

.about-stats {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--spacing-md);
  margin-top: var(--spacing-lg);
  padding-top: var(--spacing-lg);
  border-top: 2px solid rgba(109, 158, 235, 0.2);
}

.stat-item {
  text-align: center;
}

.stat-item h3 {
  font-size: var(--text-3xl);
  margin-bottom: var(--spacing-xs);
}

.stat-item p {
  color: var(--color-text-secondary);
  font-size: var(--text-sm);
  margin: 0;
}

.about-image {
  position: relative;
}

.image-wrapper {
  position: relative;
  border-radius: var(--radius-lg);
  overflow: hidden;
  box-shadow: var(--shadow-lg);
  text-align: center;
}

.image-wrapper img {
  width: 100%;
  height: auto;
  display: block;
  transition: transform var(--transition-slow);
}

.image-wrapper:hover img {
  transform: scale(1.05);
}

.image-overlay {
  position: absolute;
  inset: 0;
  background: var(--gradient-primary);
  opacity: 0.2;
  transition: opacity var(--transition-base);
}

.image-wrapper:hover .image-overlay {
  opacity: 0.1;
}

.tech-stack {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--spacing-md);
  margin-top: var(--spacing-md);
}

.tech-item {
  background-color: var(--color-bg-base);
  padding: var(--spacing-md);
  border-radius: var(--radius-lg);
  display: flex;
  align-items: center;
  justify-content: center;
  border: 2px solid rgba(109, 158, 235, 0.1);
  transition: all var(--transition-base);
  cursor: pointer;
}

.tech-item:hover {
  border-color: var(--color-primary);
  transform: translateY(-5px);
  box-shadow: var(--shadow-glow);
}

.tech-item img {
  width: 60px;
  height: 60px;
  object-fit: contain;
  filter: grayscale(100%);
  transition: filter var(--transition-base);
}

.tech-item:hover img {
  filter: grayscale(0%);
}

/* Responsividade */
@media (max-width: 968px) {
  .about-content {
    grid-template-columns: 1fr;
    gap: var(--spacing-md);
  }

  .about-image {
    order: -1;
  }

  .about-stats {
    grid-template-columns: repeat(3, 1fr);
    gap: var(--spacing-sm);
  }

  .stat-item h3 {
    font-size: var(--text-2xl);
  }
}

@media (max-width: 480px) {
  .about-stats {
    grid-template-columns: 1fr;
  }

  .tech-stack {
    grid-template-columns: repeat(2, 1fr);
    gap: var(--spacing-sm);
  }

  .tech-item img {
    width: 50px;
    height: 50px;
  }
}
</style>
