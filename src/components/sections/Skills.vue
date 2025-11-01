<template>
  <section id="skills" class="skills">
    <div class="container">
      <div class="skills-header">
        <h2 class="text-primary">Minhas Habilidades</h2>
        <p class="skills-subtitle">
          Abaixo você encontrará algumas das ferramentas e tecnologias com as quais trabalho
          profissionalmente.
        </p>
      </div>

      <div class="skills-grid">
        <!-- Frontend -->
        <div class="skill-category">
          <div class="category-icon">💻</div>
          <h3>Frontend</h3>
          <div class="skills-list">
            <div class="skill-item" v-for="skill in frontendSkills" :key="skill.name">
              <div class="skill-content">
                <span class="skill-name">{{ skill.name }}</span>
                <span class="skill-experience">{{ skill.experience }}</span>
              </div>
            </div>
          </div>
        </div>

        <!-- Backend -->
        <div class="skill-category">
          <div class="category-icon">⚙️</div>
          <h3>Backend</h3>
          <div class="skills-list">
            <div class="skill-item" v-for="skill in backendSkills" :key="skill.name">
              <div class="skill-content">
                <span class="skill-name">{{ skill.name }}</span>
                <span class="skill-experience">{{ skill.experience }}</span>
              </div>
            </div>
          </div>
        </div>

        <!-- Ferramentas -->
        <div class="skill-category">
          <div class="category-icon">🛠️</div>
          <h3>Ferramentas</h3>
          <div class="skills-list">
            <div class="skill-item" v-for="skill in toolsSkills" :key="skill.name">
              <div class="skill-content">
                <span class="skill-name">{{ skill.name }}</span>
                <span class="skill-experience">{{ skill.experience }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Badges de certificações -->
      <div class="certifications">
        <h3 class="certifications-title">Certificações</h3>
        <div class="badges-grid">
          <a
            v-for="cert in certifications"
            :key="cert.name"
            :href="cert.link"
            target="_blank"
            rel="noopener noreferrer"
            class="badge-item"
          >
            <div class="badge-icon">🏆</div>
            <span class="badge-name">{{ cert.name }}</span>
            <span class="badge-year">{{ cert.year }}</span>
            <span class="badge-view">Ver certificado →</span>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Skills',
  data() {
    return {
      frontendSkills: [
        { name: 'JavaScript', experience: '2 anos' },
        { name: 'Vue.js', experience: '2 anos' },
        { name: 'Flutter', experience: 'Acadêmico' },
        { name: 'React', experience: 'Acadêmico' },
        { name: 'Svelte', experience: 'Acadêmico' },
      ],
      backendSkills: [
        { name: 'Node.js', experience: '2 anos' },
        { name: 'MongoDB', experience: '2 anos' },
        { name: 'SQL', experience: '8 meses' },
        { name: 'C#', experience: '6 meses' },
        { name: 'PHP', experience: 'Acadêmico' },
      ],
      toolsSkills: [
        { name: 'Git/GitHub', experience: '2 anos' },
        { name: 'Figma', experience: '6 meses' },
        { name: 'Docker', experience: 'Acadêmico' },
        { name: 'English', experience: 'Intermediário' },
      ],
      certifications: [
        {
          name: 'Certificado de Monitoria',
          year: '2022',
          link: 'https://drive.google.com/file/d/118kd5dRY7Vukq_srwZbHBBWuXvz2818x/view',
        },
        {
          name: 'Certificate of Completion - Flutter & Dart',
          year: '2025',
          link: 'https://drive.google.com/file/d/1Qg8KRmUxRtROgL1dtuaaxp3X3sBan3rC/view?usp=sharing',
        },
      ],
    }
  },
}
</script>

<style scoped>
.skills {
  background-color: var(--color-bg-base);
}

.skills-header {
  text-align: center;
  margin-bottom: var(--spacing-lg);
}

.skills-subtitle {
  font-size: var(--text-lg);
  color: var(--color-text-secondary);
  max-width: 600px;
  margin: 0 auto;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: var(--spacing-md);
  margin-bottom: var(--spacing-lg);
}

.skill-category {
  background-color: var(--color-bg-secondary);
  padding: var(--spacing-md);
  border-radius: var(--radius-lg);
  border: 1px solid rgba(109, 158, 235, 0.1);
  transition: all var(--transition-base);
}

.skill-category:hover {
  transform: translateY(-5px);
  border-color: var(--color-primary);
  box-shadow: var(--shadow-glow);
}

.category-icon {
  font-size: 2.5rem;
  margin-bottom: var(--spacing-sm);
  text-align: center;
}

.skill-category h3 {
  text-align: center;
  color: var(--color-primary);
  margin-bottom: var(--spacing-md);
  font-size: var(--text-xl);
}

.skills-list {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-sm);
}

.skill-item {
  background-color: rgba(109, 158, 235, 0.05);
  padding: var(--spacing-sm);
  border-radius: var(--radius-md);
  border: 1px solid rgba(109, 158, 235, 0.1);
  transition: all var(--transition-base);
}

.skill-item:hover {
  background-color: rgba(109, 158, 235, 0.1);
  border-color: var(--color-primary);
  transform: translateX(5px);
}

.skill-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.skill-name {
  color: var(--color-text-primary);
  font-weight: 600;
  font-size: var(--text-base);
}

.skill-experience {
  color: var(--color-accent);
  font-weight: 600;
  font-size: var(--text-sm);
  padding: 0.25rem 0.75rem;
  background-color: rgba(255, 217, 102, 0.1);
  border-radius: var(--radius-full);
  white-space: nowrap;
}

/* Certificações */
.certifications {
  margin-top: var(--spacing-xl);
  text-align: center;
}

.certifications-title {
  color: var(--color-secondary);
  margin-bottom: var(--spacing-md);
}

.badges-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: var(--spacing-md);
  max-width: 900px;
  margin: 0 auto;
}

.badge-item {
  background-color: var(--color-bg-secondary);
  padding: var(--spacing-md);
  border-radius: var(--radius-md);
  border: 2px solid var(--color-accent);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
  transition: all var(--transition-base);
  text-decoration: none;
}

.badge-item:hover {
  transform: scale(1.05);
  box-shadow: 0 0 20px rgba(255, 217, 102, 0.3);
  border-color: var(--color-secondary);
}

.badge-icon {
  font-size: 2rem;
}

.badge-name {
  color: var(--color-text-primary);
  font-weight: 600;
  text-align: center;
  font-size: var(--text-sm);
  line-height: 1.4;
}

.badge-year {
  color: var(--color-accent);
  font-size: var(--text-xs);
  font-weight: 500;
}

.badge-view {
  color: var(--color-primary);
  font-size: var(--text-xs);
  margin-top: 0.25rem;
  opacity: 0;
  transition: opacity var(--transition-base);
}

.badge-item:hover .badge-view {
  opacity: 1;
}

/* Responsividade */
@media (max-width: 768px) {
  .skills-grid {
    grid-template-columns: 1fr;
  }

  .category-icon {
    font-size: 2rem;
  }

  .badges-grid {
    grid-template-columns: 1fr;
  }

  .skill-content {
    flex-direction: column;
    align-items: flex-start;
    gap: 0.5rem;
  }

  .skill-experience {
    align-self: flex-end;
  }
}
</style>
