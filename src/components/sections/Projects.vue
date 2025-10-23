<template>
  <section id="projects" class="projects">
    <div class="container">
      <div class="section-header">
        <h2 class="text-gradient">Meus Projetos</h2>
        <p class="section-subtitle">Confira alguns dos meus trabalhos mais recentes</p>
      </div>

      <div class="projects-grid grid grid-3">
        <div v-for="project in projects" :key="project.id" class="project-card card">
          <div class="project-image">
            <img :src="project.image" :alt="project.title" />
            <div class="project-overlay" v-if="project.liveUrl || project.githubUrl">
              <a
                v-if="project.liveUrl"
                :href="project.liveUrl"
                target="_blank"
                rel="noopener noreferrer"
                class="btn btn-primary btn-sm"
              >
                Ver Demo
              </a>
              <a
                v-if="project.githubUrl"
                :href="project.githubUrl"
                target="_blank"
                rel="noopener noreferrer"
                class="btn btn-secondary btn-sm"
              >
                GitHub
              </a>
            </div>
          </div>

          <div class="project-content">
            <h3 class="card-title">{{ project.title }}</h3>
            <p class="card-description">{{ project.description }}</p>

            <div class="project-tags">
              <span v-for="tech in project.technologies" :key="tech" class="tag">
                {{ tech }}
              </span>
            </div>
          </div>
        </div>
      </div>

      <div class="projects-cta">
        <p>Quer ver mais?</p>
        <a href="https://github.com/seu-usuario" target="_blank" class="btn btn-accent">
          Visite meu GitHub
        </a>
      </div>
    </div>
  </section>
</template>

<script>
import piPuzzle from '@/assets/images/pi_puzzle.gif'
import reactWordle from '@/assets/images/wordle.gif'

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Projects',
  data() {
    return {
      projects: [
        {
          id: 1,
          title: 'ProjetoPI Puzzle',
          description:
            'Meu primeiro projeto acadêmico, feito em Svelte. O app é um minigame de quebra-cabeça, com sistema de menu, seleção de dificuldade, e lógica de jogo baseada em espelhamento de listas.',
          image: piPuzzle,
          technologies: ['Svelte', 'Javascript'],
          liveUrl: 'https://projeto-pi-puzzle.vercel.app/',
          githubUrl: 'https://github.com/Afonso247/ProjetoPI-Puzzle',
        },
        {
          id: 2,
          title: 'React Wordle',
          description:
            'Clone do Wordle, trabalhando com a lógica do jogo via State Management e JSON Server local para armazenamento de dados.',
          image: reactWordle,
          technologies: ['React', 'Javascript'],
          githubUrl: 'https://github.com/Afonso247/React-Wordle',
        },
        {
          id: 3,
          title: 'App de Tarefas',
          description:
            'Aplicativo de gerenciamento de tarefas com funcionalidades de drag-and-drop e sincronização em nuvem.',
          image: 'https://via.placeholder.com/400x250/1C1C22/FFD966?text=Todo+App',
          technologies: ['Vue.js', 'Vuex', 'Firebase', 'PWA'],
          liveUrl: 'https://exemplo.com',
          githubUrl: 'https://github.com/seu-usuario/projeto3',
        },
        {
          id: 4,
          title: 'Rede Social',
          description:
            'Plataforma social com feed de posts, sistema de likes, comentários e chat em tempo real.',
          image: 'https://via.placeholder.com/400x250/1C1C22/6D9EEB?text=Social+Network',
          technologies: ['React', 'Socket.io', 'PostgreSQL', 'Redis'],
          liveUrl: 'https://exemplo.com',
          githubUrl: 'https://github.com/seu-usuario/projeto4',
        },
        {
          id: 5,
          title: 'API RESTful',
          description:
            'API completa com autenticação JWT, documentação Swagger e testes automatizados.',
          image: 'https://via.placeholder.com/400x250/1C1C22/C27BA0?text=REST+API',
          technologies: ['Node.js', 'Express', 'JWT', 'Swagger'],
          liveUrl: null,
          githubUrl: 'https://github.com/seu-usuario/projeto5',
        },
        {
          id: 6,
          title: 'Landing Page',
          description:
            'Landing page responsiva e animada para produto SaaS com otimização SEO e performance.',
          image: 'https://via.placeholder.com/400x250/1C1C22/FFD966?text=Landing+Page',
          technologies: ['HTML', 'CSS', 'JavaScript', 'GSAP'],
          liveUrl: 'https://exemplo.com',
          githubUrl: 'https://github.com/seu-usuario/projeto6',
        },
      ],
    }
  },
}
</script>

<style scoped>
.projects {
  background-color: var(--color-bg-base);
}

.section-header {
  text-align: center;
  margin-bottom: var(--spacing-lg);
}

.section-subtitle {
  font-size: var(--text-lg);
  color: var(--color-text-secondary);
  margin-top: var(--spacing-sm);
}

.projects-grid {
  margin-bottom: var(--spacing-lg);
}

.project-card {
  overflow: hidden;
  padding: 0;
  display: flex;
  flex-direction: column;
  height: 100%;
}

.project-image {
  position: relative;
  width: 100%;
  height: 250px;
  overflow: hidden;
  background-color: var(--color-bg-base);
}

.project-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform var(--transition-slow);
}

.project-card:hover .project-image img {
  transform: scale(1.1);
}

.project-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(13, 13, 13, 0.9);
  display: flex;
  align-items: center;
  justify-content: center;
  gap: var(--spacing-sm);
  opacity: 0;
  transition: opacity var(--transition-base);
}

.project-card:hover .project-overlay {
  opacity: 1;
}

.btn-sm {
  padding: 0.5rem 1rem;
  font-size: var(--text-sm);
}

.project-content {
  padding: var(--spacing-md);
  flex: 1;
  display: flex;
  flex-direction: column;
}

.project-content .card-title {
  margin-bottom: var(--spacing-sm);
  font-size: var(--text-xl);
}

.project-content .card-description {
  flex: 1;
  margin-bottom: var(--spacing-md);
  line-height: 1.6;
}

.project-tags {
  display: flex;
  flex-wrap: wrap;
  gap: var(--spacing-xs);
  margin-top: auto;
}

.tag {
  display: inline-block;
  padding: 0.25rem 0.75rem;
  background: linear-gradient(135deg, rgba(109, 158, 235, 0.2), rgba(194, 123, 160, 0.2));
  border: 1px solid var(--color-primary);
  border-radius: var(--radius-full);
  font-size: var(--text-xs);
  color: var(--color-primary);
  font-weight: 500;
  transition: all var(--transition-fast);
}

.tag:hover {
  background: var(--color-primary);
  color: var(--color-bg-base);
  transform: translateY(-2px);
}

.projects-cta {
  text-align: center;
  margin-top: var(--spacing-xl);
}

.projects-cta p {
  font-size: var(--text-lg);
  margin-bottom: var(--spacing-sm);
  color: var(--color-text-primary);
}

/* Responsividade */
@media (max-width: 768px) {
  .section-header h2 {
    font-size: var(--text-3xl);
  }

  .section-subtitle {
    font-size: var(--text-base);
  }

  .project-image {
    height: 200px;
  }

  .project-overlay {
    opacity: 1;
    background: rgba(13, 13, 13, 0.7);
  }

  .projects-cta {
    margin-top: var(--spacing-md);
  }
}

@media (max-width: 480px) {
  .project-content {
    padding: var(--spacing-sm);
  }

  .btn-sm {
    font-size: var(--text-xs);
    padding: 0.4rem 0.8rem;
  }
}
</style>
