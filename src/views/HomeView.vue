<template>
  <div class="home h-100 with-dots">
    <span class="dot" v-for="(p, index) in Array(amountDots)" :key="index">
    </span>

    <div class="container h-100">
      <div class="profile-card" ref="card">
        <h2>
          WEB<br />
          DEV
        </h2>
        <p>
          Hola, <br />
          Soy <b>Patricio Rojas</b> <br />
          Desarrollador Web Fullstack, especializado en Frontend
          <br />
          Temuco, Chile
        </p>

        <p class="icons">
          <span
            ><a href="https://github.com/brujo-rojas" target="_blank"
              ><i class="fa fa-github"></i></a
          ></span>
          <span
            ><a href="https://codepen.io/brujo696" target="_blank"
              ><i class="fa fa-codepen"></i></a
          ></span>
          <span
            ><a
              href="https://www.linkedin.com/in/patriciorojasr/"
              target="_blank"
              ><i class="fa fa-linkedin"></i></a
          ></span>
        </p>
      </div>
    </div>
  </div>
</template>
<script lang="ts">
export default {
  setup() {
    let amountDots = 20;

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

  .profile-card {
    background: red;
    flex: 1 0 100%;
    padding: 4em;
    text-align: left;
    border-radius: 9px;

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
      &:after {
        content: "";
        display: block;
        position: absolute;
        background: rgba(57, 73, 171, 0.8);
        width: 0.2em;
        left: 0;
        top: 0;
        height: calc(100% - 24px);
      }
    }
    p {
      font-size: 2em;
      line-height: 1.5em;
      font-weight: normal;
      margin-top: 2.5em;
    }
    p.icons {
      a {
        color: white;
        margin-right: 1em;
      }
    }
  }
}
</style>
