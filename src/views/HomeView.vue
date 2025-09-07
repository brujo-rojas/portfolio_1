<template>
  <div class="home h-100 with-dots">
    <span class="dot" v-for="(p, index) in Array(amountDots)" :key="index">
    </span>

    <div class="container h-100">
      <div class="profile-card" ref="card">
        <h2>
          FRONT<br />
          DEV
        </h2>
        <p>
          Hola, <br />
          Soy <b>Patricio Rojas</b> <br />
          Desarrollador Web Fullstack, especializado en Frontend
          <br />
          Temuco, Chile
        </p>

        <p class="social-links">
          <a href="https://github.com/brujo-rojas" target="_blank" class="chip">
            <i class="fa fa-github"></i>
            <span class="platform-name">GitHub</span>
          </a>
          <a href="https://codepen.io/brujo696" target="_blank" class="chip">
            <i class="fa fa-codepen"></i>
            <span class="platform-name">CodePen</span>
          </a>
          <a
            href="https://www.linkedin.com/in/patriciorojasr/"
            target="_blank"
            class="chip"
          >
            <i class="fa fa-linkedin"></i>
            <span class="platform-name">LinkedIn</span>
          </a>
        </p>
      </div>
    </div>
  </div>
</template>
<script lang="ts">
export default {
  setup() {
    const amountDots = 20;

    return {
      amountDots,
    };
  },
};
</script>

<style lang="scss">
@import "src/styles/style.scss";

.home {
  position: relative;
  background: rgba(26, 28, 32, 1);
  background-size: cover;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: start;
  height: 100% !important;
  min-height: 100% !important;
  flex: 1 0 auto;
  padding: 3em;
  transition: all 0.3s ease;

  @media (max-width: 768px) {
    padding: 0;
  }

  .profile-card {
    background: red;
    flex: 1 0 100%;
    padding: 4em;
    text-align: left;
    border-radius: 9px;
    
    // Animación de entrada
    animation: slideInUp 1s ease-out;
    opacity: 1;
    
    @keyframes slideInUp {
      0% {
        opacity: 0;
        transform: translateY(50px);
      }
      100% {
        opacity: 1;
        transform: translateY(0);
      }
    }

    display: flex;
    justify-content: space-between;
    align-items: start;
    flex-direction: column;
    box-shadow: 0 0 0 2px rgba(0, 0, 0, 0.4), 0 6px 6px -7px rgba(0, 0, 0, 0.7),
      0 11px 15px -7px rgba(0, 0, 0, 0.2), 0 24px 38px 3px rgba(0, 0, 0, 0.14),
      0 9px 46px 8px rgba(0, 0, 0, 0.12), inset 0px 0px 90px rgba(0, 0, 0, 0.9),
      inset 0px 0px 300px rgba(255, 255, 255, 0.2);

    color: #fff;
    background: rgba(0, 0, 0, 0.7);
    border: 1px solid rgba(255, 255, 255, 0.2) !important;
    backdrop-filter: blur(20px);

    h2 {
      font-size: 7em;
      padding: 0 0 0 0.4em;
      display: block;
      position: relative;
      transition: all 0.3s ease;
      &:after {
        content: "";
        display: block;
        position: absolute;
        background: rgba(57, 73, 171, 0.8);
        width: 0.2em;
        left: 0;
        top: 0;
        height: calc(100% - 24px);
        transition: all 0.3s ease;
      }
      @media (max-width: 768px) {
        font-size: 4em;
        &:after {
          height: calc(100% - 12px);
        }
      }
    }

    p {
      font-size: 2em;
      line-height: 1.5em;
      font-weight: normal;
      margin-top: 2.5em;
      
      @media (max-width: 768px) {
        font-size: 1.5em;
      }
    }

    p.social-links {
      display: flex;
      gap: 2em;
      flex-wrap: wrap;
      margin-top: 2.5em;

      .chip {
        display: inline-flex;
        align-items: center;
        gap: 1.5em;
        padding: 0.3em 1.2em;
        background: rgba(255, 255, 255, 0.1);
        border: 1px solid rgba(255, 255, 255, 0.3);
        border-radius: 25px;
        color: white;
        text-decoration: none;
        transition: all 0.3s ease;
        backdrop-filter: blur(10px);
        font-size: 0.85em;

        &:hover {
          background: rgba(255, 255, 255, 0.2);
          border-color: rgba(255, 255, 255, 0.5);
          transform: translateY(-2px);
          box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
        }

        i {
          font-size: 1.2em;
          width: 20px;
          text-align: center;
        }

        .platform-name {
          font-weight: 500;
          letter-spacing: 0.5px;
        }
      }
    }
  }
}
</style>
