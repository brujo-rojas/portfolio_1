<template>
  <div class="skills-container">
    <div class="inset-container">
      <h1>Habilidades</h1>
      <div class="skills-groups">
        <div
          v-for="group in skillGroups"
          :key="group.category"
          class="skill-group"
        >
          <h2 class="group-title">{{ group.category }}</h2>
          <div class="skills-grid">
            <div
              v-for="skill in group.skills"
              :key="skill.name"
              class="skill-item"
            >
              <div class="skill-icon">
                <img :src="`${skill.icon}`" :alt="skill.name" />
              </div>
              <span class="skill-name">{{ skill.name }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { ref } from "vue";

export default {
  setup() {
    const skillGroups = ref([
      {
        category: "Frontend Frameworks & Libraries",
        skills: [
          {
            name: "Vue 3",
            icon: "https://icon.icepanel.io/Technology/svg/Vue.js.svg",
          },
          {
            name: "React",
            icon: "https://icon.icepanel.io/Technology/svg/React.svg",
          },
          {
            name: "Angular",
            icon: "https://icon.icepanel.io/Technology/svg/Angular.svg",
          },
          {
            name: "Svelte",
            icon: "https://icon.icepanel.io/Technology/svg/Svelte.svg",
          },
          {
            name: "Nuxt 4",
            icon: "https://icon.icepanel.io/Technology/svg/Nuxt-JS.svg",
          },
          {
            name: "Astro",
            icon: "https://icon.icepanel.io/Technology/png-shadow-512/Astro.png",
          },
          {
            name: "React Native",
            icon: "https://icon.icepanel.io/Technology/svg/React.svg",
          },
        ],
      },
      {
        category: "UI Frameworks & Styling",
        skills: [
          {
            name: "Vuetify",
            icon: "https://icon.icepanel.io/Technology/svg/Veutify.svg",
          },
          {
            name: "Tailwind CSS",
            icon: "https://icon.icepanel.io/Technology/svg/Tailwind-CSS.svg",
          },
          {
            name: "Bootstrap",
            icon: "https://icon.icepanel.io/Technology/svg/Bootstrap.svg",
          },
        ],
      },
      {
        category: "Backend & Runtime",
        skills: [
          {
            name: "Node.js",
            icon: "https://icon.icepanel.io/Technology/svg/Node.js.svg",
          },
          {
            name: "Express.js",
            icon: "https://icon.icepanel.io/Technology/svg/Express.svg",
          },
          {
            name: "Laravel",
            icon: "https://icon.icepanel.io/Technology/svg/Laravel.svg",
          },
          {
            name: "Bun",
            icon: "https://icon.icepanel.io/Technology/svg/Bun.svg",
          },
        ],
      },
      {
        category: "Databases & Storage",
        skills: [
          {
            name: "MySQL",
            icon: "https://icon.icepanel.io/Technology/svg/MySQL.svg",
          },
          {
            name: "MongoDB",
            icon: "https://icon.icepanel.io/Technology/svg/MongoDB.svg",
          },
          {
            name: "Firebase",
            icon: "https://icon.icepanel.io/Technology/svg/Firebase.svg",
          },
        ],
      },
      {
        category: "Development Tools & Editors",
        skills: [
          {
            name: "VS Code",
            icon: "https://icon.icepanel.io/Technology/svg/Visual-Studio-Code-%28VS-Code%29.svg",
          },
          {
            name: "Vim",
            icon: "https://icon.icepanel.io/Technology/svg/Vim.svg",
          },
          {
            name: "Vite",
            icon: "https://icon.icepanel.io/Technology/svg/Vite.js.svg",
          },
          {
            name: "NPM",
            icon: "https://icon.icepanel.io/Technology/svg/NPM.svg",
          },
          {
            name: "Postman",
            icon: "https://icon.icepanel.io/Technology/svg/Postman.svg",
          },
          {
            name: "Figma",
            icon: "https://icon.icepanel.io/Technology/svg/Figma.svg",
          },
        ],
      },
      {
        category: "Version Control & Collaboration",
        skills: [
          {
            name: "Git",
            icon: "https://icon.icepanel.io/Technology/svg/Git.svg",
          },
          {
            name: "GitHub",
            icon: "https://icon.icepanel.io/Technology/svg/GitHub.svg",
          },
          {
            name: "GitLab",
            icon: "https://icon.icepanel.io/Technology/svg/GitLab.svg",
          },
          {
            name: "Bitbucket",
            icon: "https://icon.icepanel.io/Technology/svg/BitBucket.svg",
          },
        ],
      },
      {
        category: "Project Management & Communication",
        skills: [
          {
            name: "Jira",
            icon: "https://icon.icepanel.io/Technology/svg/Jira.svg",
          },
          {
            name: "Trello",
            icon: "https://icon.icepanel.io/Technology/svg/Trello.svg",
          },
          {
            name: "Notion",
            icon: "https://cdn.brandfetch.io/idPYUoikV7/w/400/h/400/theme/dark/icon.png?c=1bxid64Mup7aczewSAYMX&t=1721041449201",
          },
          {
            name: "Slack",
            icon: "https://icon.icepanel.io/Technology/svg/Slack.svg",
          },
        ],
      },
      {
        category: "Cloud & Deployment",
        skills: [
          {
            name: "AWS",
            icon: "https://icon.icepanel.io/Technology/svg/AWS.svg",
          },
          {
            name: "DigitalOcean",
            icon: "https://icon.icepanel.io/Technology/svg/Digital-Ocean.svg",
          },
          {
            name: "Netlify",
            icon: "https://cdn.brandfetch.io/idoW6GB9ca/theme/dark/symbol.svg?c=1bxid64Mup7aczewSAYMX&t=1746443990535",
          },
          {
            name: "Vercel",
            icon: "https://icon.icepanel.io/Technology/svg/Vercel.svg",
          },
        ],
      },
      {
        category: "Operating Systems & Terminal",
        skills: [
          {
            name: "Linux",
            icon: "https://icon.icepanel.io/Technology/svg/Linux.svg",
          },
          {
            name: "Ubuntu",
            icon: "https://icon.icepanel.io/Technology/svg/Ubuntu.svg",
          },
          {
            name: "Bash",
            icon: "https://icon.icepanel.io/Technology/svg/Bash.svg",
          },
        ],
      },
    ]);

    return {
      skillGroups,
    };
  },
};
</script>

<style lang="scss" scoped>
.skills-container {
  min-height: 100vh;
  background: rgba(26, 28, 32, 1);
  padding: 2rem;
  display: flex;
  align-items: center;

  .inset-container {
    max-width: 1000px;
    margin: 0 auto;
    width: 100%;

    h1 {
      color: white;
      text-align: center;
      font-size: 3rem;
      margin-bottom: 3rem;
      font-weight: 300;
    }

    .skills-groups {
      display: flex;
      flex-direction: column;
      gap: 3rem;

      .skill-group {
        .group-title {
          color: rgba(255, 255, 255, 0.9);
          font-size: 1.5rem;
          font-weight: 500;
          margin-bottom: 1.5rem;
          text-align: center;
          border-bottom: 2px solid rgba(255, 255, 255, 0.2);
          padding-bottom: 0.5rem;
        }
      }
    }

    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
      gap: 1rem;
      max-width: 100%;

      @media (min-width: 768px) {
        grid-template-columns: repeat(4, 1fr);
      }

      .skill-item {
        background: rgba(255, 255, 255, 0.2);
        border: 1px solid rgba(255, 255, 255, 0.3);
        border-radius: 12px;
        padding: 1.5rem;
        text-align: center;
        backdrop-filter: blur(20px);
        transition: all 0.3s ease;
        box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);

        &:hover {
          background: rgba(255, 255, 255, 0.3);
          border-color: rgba(255, 255, 255, 0.5);
          transform: translateY(-5px);
          box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
          .skill-icon img {
            opacity: 1;
          }
          .skill-name {
            color: rgba(211, 211, 211, 0.9);
          }
        }

        .skill-icon {
          margin-bottom: 1rem;
          height: 80px;
          display: flex;
          align-items: center;
          justify-content: center;

          img {
            width: inherit;
            height: inherit;
            object-fit: contain;
            opacity: 0.8;
            filter: drop-shadow(1px 0 0 rgba(255, 255, 255, 0.9))
              drop-shadow(-1px 0 0 rgba(255, 255, 255, 0.9))
              drop-shadow(0 1px 0 rgba(255, 255, 255, 0.9))
              drop-shadow(0 -1px 0 rgba(255, 255, 255, 0.9))
              drop-shadow(1px 1px 0 rgba(255, 255, 255, 0.9))
              drop-shadow(-1px -1px 0 rgba(255, 255, 255, 0.9))
              drop-shadow(1px -1px 0 rgba(255, 255, 255, 0.9))
              drop-shadow(-1px 1px 0 rgba(255, 255, 255, 0.9));
          }
        }

        .skill-name {
          color: rgba(148, 148, 148, 0.9);
          font-size: 1.25rem;
          font-weight: 600;
          transition: all 0.3s ease;
        }
      }
    }
  }
}

@media (max-width: 768px) {
  .skills-container {
    .container {
      h1 {
        font-size: 2rem;
      }

      .skills-grid {
        grid-template-columns: 1fr;
        gap: 0.8rem;

        .skill-item {
          padding: 1rem;
          display: flex;
          align-items: center;
          text-align: left;

          .skill-icon {
            height: 35px;
            margin-bottom: 0;
            margin-right: 1rem;
            flex-shrink: 0;

            img {
              width: 35px;
              height: 35px;
            }
          }

          .skill-name {
            font-size: 1rem;
            color: rgba(26, 28, 32, 0.9);
            font-weight: 600;
          }
        }
      }
    }
  }
}
</style>
