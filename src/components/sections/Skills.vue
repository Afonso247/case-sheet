<template>
  <section id="skills" class="skills">
    <div class="container">
      <div class="skills-header">
        <h2 class="text-gradient">Minhas Habilidades</h2>
        <p class="skills-subtitle">
          Tecnologias e ferramentas que domino para criar soluções incríveis
        </p>
      </div>

      <div class="skills-grid">
        <!-- Frontend -->
        <div class="skill-category">
          <div class="category-icon">💻</div>
          <h3>Frontend</h3>
          <div class="skills-list">
            <div class="skill-item" v-for="skill in frontendSkills" :key="skill.name">
              <div class="skill-info">
                <span class="skill-name">{{ skill.name }}</span>
                <span class="skill-level">{{ skill.level }}%</span>
              </div>
              <div class="skill-bar">
                <div class="skill-progress" :style="{ width: skill.level + '%' }"></div>
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
              <div class="skill-info">
                <span class="skill-name">{{ skill.name }}</span>
                <span class="skill-level">{{ skill.level }}%</span>
              </div>
              <div class="skill-bar">
                <div class="skill-progress" :style="{ width: skill.level + '%' }"></div>
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
              <div class="skill-info">
                <span class="skill-name">{{ skill.name }}</span>
                <span class="skill-level">{{ skill.level }}%</span>
              </div>
              <div class="skill-bar">
                <div class="skill-progress" :style="{ width: skill.level + '%' }"></div>
              </div>
            </div>
          </div>
        </div>

        <!-- Soft Skills -->
        <div class="skill-category">
          <div class="category-icon">🎯</div>
          <h3>Soft Skills</h3>
          <div class="skills-list">
            <div class="skill-item" v-for="skill in softSkills" :key="skill.name">
              <div class="skill-info">
                <span class="skill-name">{{ skill.name }}</span>
                <span class="skill-level">{{ skill.level }}%</span>
              </div>
              <div class="skill-bar">
                <div class="skill-progress" :style="{ width: skill.level + '%' }"></div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Badges de certificações (opcional) -->
      <div class="certifications">
        <h3 class="certifications-title">Certificações</h3>
        <div class="badges-grid">
          <div class="badge-item" v-for="cert in certifications" :key="cert.name">
            <div class="badge-icon">🏆</div>
            <span class="badge-name">{{ cert.name }}</span>
            <span class="badge-year">{{ cert.year }}</span>
          </div>
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
        { name: 'HTML/CSS', level: 90 },
        { name: 'JavaScript', level: 80 },
        { name: 'Vue.js', level: 75 },
        { name: 'React', level: 50 },
      ],
      backendSkills: [
        { name: 'Node.js', level: 85 },
        { name: 'MongoDB', level: 70 },
        { name: 'C#', level: 50 },
        { name: 'PHP', level: 50 },
        { name: 'SQL', level: 50 },
      ],
      toolsSkills: [
        { name: 'VS Code', level: 95 },
        { name: 'Git/GitHub', level: 90 },
        { name: 'Docker', level: 50 },
        { name: 'Figma', level: 50 },
      ],
      softSkills: [
        { name: 'Comunicação', level: 95 },
        { name: 'Resolução de Problemas', level: 95 },
        { name: 'Trabalho em Equipe', level: 90 },
        { name: 'Adaptabilidade', level: 85 },
        { name: 'Gestão de Tempo', level: 85 },
      ],
      certifications: [
        { name: 'AWS Certified Developer', year: '2024' },
        { name: 'Vue.js Certification', year: '2023' },
        { name: 'Scrum Master', year: '2023' },
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
  margin-bottom: var(--spacing-xs);
}

.skill-info {
  display: flex;
  justify-content: space-between;
  margin-bottom: 0.5rem;
}

.skill-name {
  color: var(--color-text-primary);
  font-weight: 500;
  font-size: var(--text-sm);
}

.skill-level {
  color: var(--color-accent);
  font-weight: 600;
  font-size: var(--text-sm);
}

.skill-bar {
  height: 8px;
  background-color: var(--color-bg-base);
  border-radius: var(--radius-full);
  overflow: hidden;
  position: relative;
}

.skill-progress {
  height: 100%;
  background: var(--gradient-primary);
  border-radius: var(--radius-full);
  transition: width 1s ease-out;
  position: relative;
}

.skill-progress::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
  animation: shimmer 2s infinite;
}

@keyframes shimmer {
  0% {
    transform: translateX(-100%);
  }
  100% {
    transform: translateX(100%);
  }
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
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: var(--spacing-md);
  max-width: 800px;
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
}

.badge-item:hover {
  transform: scale(1.05);
  box-shadow: 0 0 20px rgba(255, 217, 102, 0.3);
}

.badge-icon {
  font-size: 2rem;
}

.badge-name {
  color: var(--color-text-primary);
  font-weight: 600;
  text-align: center;
  font-size: var(--text-sm);
}

.badge-year {
  color: var(--color-accent);
  font-size: var(--text-xs);
  font-weight: 500;
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
}
</style>
