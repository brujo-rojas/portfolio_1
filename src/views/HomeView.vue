<template>
  <div class="home h-100">
    <div class="container h-100">
      <div class="profile-card">
        <h2>Some text</h2>
        <h3>Some text</h3>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "HomeView",
});
</script>
<style lang="scss">
@import "src/styles/style.scss";

.home {
  position: relative;
  background: url("/public/img/back.jpg") no-repeat center center fixed;
  background-size: cover;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100% !important;
  min-height: 100% !important;
  flex: 1 0 auto;

  .profile-card {
    min-height: 300px;
    background: red;
    margin: 3em 0;
    flex: 1 1 auto;
    padding: 2em;

    display: flex;
    justify-content: center;
    align-items: start;
    flex-direction: column;
    box-shadow: 0 11px 15px -7px rgba(0, 0, 0, 0.2),
      0 24px 38px 3px rgba(0, 0, 0, 0.14), 0 9px 46px 8px rgba(0, 0, 0, 0.12) !important;

    color: #fff;
    background: rgba(0, 0, 0, 0.7) !important;
    border: 1px solid hsla(0, 0%, 100%, 0.4) !important;
    -webkit-backdrop-filter: blur(20px);
    backdrop-filter: blur(20px);

    h2 {
      font-size: 8em;
    }
    h3 {
      font-size: 4em;
    }
  }
}
</style>
